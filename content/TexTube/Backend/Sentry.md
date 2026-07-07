### 프로덕션 환경에서만 설정하기
```ts
// main.ts
import * as Sentry from '@sentry/nestjs'

async function bootstrap() {
  const isProduction = process.env.NODE_ENV === 'production';
  
  Sentry.init({
    dsn: process.env.SENTRY_DSN,
    enabled: isProduction,
    environment: process.env.NODE_ENV,
    tracesSampleRate: 1.0,
  });
}
```

### 무료인가? => 무료 플랜 (Developer)
에러 수집량: 월 최대 5000건
데이터 보관: 에러 기록 30일 유지
사용자 수 제한: 1명
기타: 성능 모니터링, 업타임 모니터링, 크론 모니터링

### 간단 사용법
- Sentry 가입 및 프로젝트 생성: DSN(Data Source Name) 주소를 받는다
- SDK를 설치한다: `npm install @sentry/nestjs @sentry/profiling-node`
- Interceptor/Logger 적용: NestJS의 `Catch` 데코레이터로 데이터 전송
- 슬랙/이메일 연동: Alerts 메뉴

