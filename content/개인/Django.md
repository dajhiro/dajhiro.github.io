# NestJS로 Django급 프레임워크 구축하기 — 아키텍처 설계 문서

## 1. 목표와 범위

Django가 기본 제공하는 "batteries included" 기능들을 NestJS 기반으로 재현한다. 핵심 커버리지:

- ORM & 마이그레이션
- 인증/인가 (세션, JWT, 권한, 그룹)
- 자동 검증 및 직렬화 (Forms/Serializers)
- 관리자 패널 (Django Admin)
- 시그널 / 이벤트 시스템
- 백그라운드 작업 큐 (Celery)
- 설정 관리 (settings.py)
- 관리 커맨드 (manage.py)
- 캐싱
- 정적/미디어 파일 서빙
- 국제화(i18n)
- 테스트 클라이언트
- API 문서 자동화 (DRF의 부가 기능이지만 사실상 표준)

---

## 2. 기술 스택 매핑

| 계층        | Django                           | NestJS 선택                                            | 비고                             |
| --------- | -------------------------------- | ---------------------------------------------------- | ------------------------------ |
| 웹 프레임워크   | Django                           | NestJS (Express 어댑터)                                 | Fastify 어댑터로 교체 시 성능 이점        |
| ORM       | Django ORM                       | **Prisma**                                           | TypeORM보다 타입 안정성, 마이그레이션 DX 우수 |
| DB 마이그레이션 | `makemigrations`/`migrate`       | `prisma migrate`                                     | 자동 diff 생성                     |
| 인증        | `django.contrib.auth`            | `@nestjs/passport` + `passport-jwt`/`passport-local` |                                |
| 인가/권한     | Permissions, Groups              | Guards + **CASL**                                    | 속성 기반 권한(ABAC) 지원              |
| 검증        | Django Forms/ModelForms          | `class-validator` + DTO                              |                                |
| 직렬화       | DRF Serializers                  | `class-transformer`                                  | `@Exclude`, `@Expose` 데코레이터    |
| Admin 패널  | Django Admin                     | **AdminJS** (`@adminjs/nestjs`)                      | Prisma 어댑터 지원                  |
| 시그널       | Django Signals                   | `@nestjs/event-emitter`                              |                                |
| 비동기 작업    | Celery + Redis/RabbitMQ          | `@nestjs/bull` + Redis                               |                                |
| 설정 관리     | `settings.py` + `django-environ` | `@nestjs/config` + `joi` 스키마 검증                      |                                |
| 관리 커맨드    | `manage.py <command>`            | `nest-commander`                                     |                                |
| 캐싱        | Django cache framework           | `@nestjs/cache-manager` (+ Redis store)              |                                |
| 정적/미디어    | `STATIC_ROOT`/`MEDIA_ROOT`       | `@nestjs/serve-static` + `multer` (+ S3 어댑터)         |                                |
| i18n      | Django i18n                      | `nestjs-i18n`                                        |                                |
| 테스트 클라이언트 | Django TestClient                | `@nestjs/testing` + `supertest`                      |                                |
| API 문서    | DRF `drf-spectacular`            | `@nestjs/swagger`                                    | OpenAPI 자동 생성                  |
| 스케줄링      | `django-crontab`/Celery beat     | `@nestjs/schedule`                                   |                                |

---

## 3. 프로젝트 구조

Django의 "app" 단위 구조를 Nest의 "module" 단위로 1:1 대응시킨다.

```
src/
├── main.ts                      # ASGI/WSGI 진입점에 해당
├── app.module.ts                # settings.py의 INSTALLED_APPS 등록부
├── config/
│   ├── configuration.ts         # settings.py 대응
│   └── validation.schema.ts     # env 검증 (joi)
├── common/
│   ├── decorators/               # 커스텀 데코레이터 (@CurrentUser 등)
│   ├── filters/                  # 예외 처리 (Django의 커스텀 에러 핸들러)
│   ├── guards/                   # 인증/인가 가드
│   ├── interceptors/             # 응답 변환, 로깅
│   ├── pipes/                    # 검증 파이프
│   └── middleware/
├── prisma/
│   ├── schema.prisma             # models.py 대응
│   ├── migrations/               # migrations/ 디렉토리 대응
│   └── prisma.service.ts
├── modules/
│   ├── users/                    # Django의 accounts app
│   │   ├── users.module.ts
│   │   ├── users.controller.ts   # views.py
│   │   ├── users.service.ts      # models.py의 매니저/쿼리셋 로직
│   │   ├── dto/                  # forms.py / serializers.py
│   │   └── entities/
│   ├── auth/
│   ├── posts/
│   └── ...
├── admin/                        # Django Admin 대응 (AdminJS 설정)
├── jobs/                         # Celery tasks 대응 (Bull processors)
├── commands/                     # management/commands/ 대응
└── i18n/                         # locale/ 대응
```

---

## 4. 핵심 모듈 설계

### 4.1 ORM 계층 (Prisma)

- `schema.prisma`에 모델 정의 → Django의 `models.py` 역할
- `PrismaService`를 전역 모듈로 등록해 DI로 어디서든 주입
- Django의 `Model.objects.filter()` 같은 커스텀 쿼리 로직은 Repository 패턴으로 서비스 레이어에 캡슐화
- Soft delete, `created_at`/`updated_at` 자동화는 Prisma 미들웨어(`$use`)로 구현

### 4.2 인증/인가

- **인증**: `passport-local`(세션 기반, Django 기본과 동일) + `passport-jwt`(API 토큰 기반, DRF TokenAuth와 동일) 병행 지원
- **인가**: Django의 Permission/Group 모델을 Prisma 스키마에 재현하고, `CaslAbilityFactory`로 리소스별 권한 규칙 정의
- `RolesGuard`, `PoliciesGuard`를 컨트롤러 레벨 데코레이터로 적용

### 4.3 검증 & 직렬화

- 요청 DTO에 `class-validator` 데코레이터 (`@IsEmail()`, `@MinLength()` 등) → Django Forms의 필드 검증과 동일한 선언적 스타일
- 전역 `ValidationPipe(whitelist: true, forbidNonWhitelisted: true)` 설정으로 Django Form의 `clean_*` 검증 흐름 재현
- 응답 직렬화는 `ClassSerializerInterceptor` + `@Exclude()`로 DRF Serializer의 필드 제어 대응

### 4.4 관리자 패널 (Admin)

- `@adminjs/nestjs` + `@adminjs/prisma` 어댑터로 자동 CRUD 관리 UI 생성
- Django Admin의 `list_display`, `search_fields`, `list_filter`에 대응하는 AdminJS `resources` 옵션 설정
- 커스텀 액션은 AdminJS의 `actions` 필드로 구현 (Django Admin actions와 동일 개념)

### 4.5 시그널 / 이벤트

- `@nestjs/event-emitter`의 `EventEmitter2`로 `post_save`, `pre_delete` 같은 Django 시그널 대응
- 예: `UserCreatedEvent` 발행 → `SendWelcomeEmailListener`가 구독 (Django의 `post_save` + `@receiver`와 동일 패턴)

### 4.6 백그라운드 작업 (Celery → Bull)

- Redis 기반 `@nestjs/bull` 큐 사용
- Django Celery의 `@shared_task`는 Bull의 `@Processor()` + `@Process()`로 대응
- 주기적 작업(Celery beat)은 `@nestjs/schedule`의 `@Cron()`으로 대체

### 4.7 설정 관리

- `@nestjs/config`로 `.env` 로드, `joi` 스키마로 환경변수 검증 (Django의 `django-environ` + 커스텀 검증과 동일)
- 환경별 설정 파일 분리: `configuration.dev.ts`, `configuration.prod.ts` (Django의 `settings/base.py`, `settings/production.py` 분리 패턴과 동일)

### 4.8 관리 커맨드

- `nest-commander`로 `manage.py createsuperuser`, `manage.py loaddata` 같은 CLI 커맨드 구현
- 예: `npm run cli -- create-admin --email=admin@test.com`

### 4.9 캐싱

- `@nestjs/cache-manager` + `cache-manager-redis-store`로 Django의 `cache.set()`/`cache.get()` API 대응
- `@CacheKey()`, `@CacheTTL()` 데코레이터로 컨트롤러 레벨 캐싱

### 4.10 국제화

- `nestjs-i18n`으로 `locale/*.json` 관리, Django의 `gettext`/`{% trans %}` 대응
- `Accept-Language` 헤더 기반 자동 언어 감지

---

## 5. 요청 처리 흐름 비교

```
Django:                          NestJS:
Middleware                       Middleware
  → URL Resolver                   → Guard (인증/인가)
  → View                             → Pipe (검증/변환)
    → Form 검증                        → Interceptor (전/후처리)
    → Model 쿼리                         → Controller
    → Serializer                           → Service
  → Middleware (응답)                       → Repository (Prisma)
  → Response                             → Interceptor (직렬화)
                                        → Exception Filter (에러 처리)
                                      → Response
```

---

## 6. 테스트 전략

|Django|NestJS|
|---|---|
|`TestCase` + `Client`|`@nestjs/testing`의 `Test.createTestingModule()`|
|`pytest-django` fixtures|Jest `beforeEach`/팩토리 함수|
|Factory Boy|`@ngneat/falso` 또는 직접 팩토리 함수|
|Django `override_settings`|테스트 모듈에서 provider 오버라이드|

- 단위 테스트: 서비스 레이어 (Prisma는 mock 또는 in-memory sqlite)
- e2e 테스트: `supertest`로 실제 HTTP 요청 검증 (Django TestClient와 동일 목적)

---

## 7. 단계별 구현 로드맵

1. **Phase 1 — 기반**: Nest 프로젝트 초기화, Prisma 연결, `@nestjs/config` 설정
2. **Phase 2 — 인증**: User 모델, JWT/세션 인증, Guard 구성
3. **Phase 3 — CRUD 도메인 모듈**: DTO 검증 + 직렬화 패턴 확립 (템플릿화하여 반복 사용)
4. **Phase 4 — 인가**: CASL 기반 권한/그룹 시스템
5. **Phase 5 — Admin 패널**: AdminJS 연동
6. **Phase 6 — 비동기/시그널**: EventEmitter, Bull 큐
7. **Phase 7 — 부가 기능**: 캐싱, i18n, 관리 커맨드, 스케줄링
8. **Phase 8 — 문서화/테스트**: Swagger 자동화, e2e 테스트 커버리지 확보

---

## 8. 주요 트레이드오프

- **Prisma vs TypeORM**: Prisma는 타입 안정성과 마이그레이션 DX가 뛰어나지만, TypeORM보다 복잡한 다형성 관계(polymorphic relations)나 Django의 `GenericForeignKey` 같은 패턴 구현이 번거로움 → 필요 시 raw SQL 또는 별도 조인 테이블로 우회
- **AdminJS vs 자체 구현**: AdminJS는 빠르지만 Django Admin만큼의 세밀한 커스터마이징(inline formset 등)은 제한적 → 고급 요구사항이면 별도 관리자 프론트엔드(React 등) 고려
- **Bull vs Celery**: Bull은 Redis 전용, Celery는 브로커 선택 폭이 넓음 → 현재 스택이 Redis 중심이면 문제 없음

---

## 9. 다음 단계 제안

이 문서를 기반으로 실제 코드를 스캐폴딩할 때는 아래 순서를 권장합니다.

1. `nest new` 프로젝트 생성 + Prisma 초기화
2. `User`/`Auth` 모듈부터 구현 (다른 모든 모듈의 의존성)
3. 하나의 도메인 모듈(예: `Posts`)을 "레퍼런스 구현"으로 완성 → 이후 모듈은 이를 복제

준비되면 Phase 1부터 실제 파일 생성을 시작할 수 있습니다.