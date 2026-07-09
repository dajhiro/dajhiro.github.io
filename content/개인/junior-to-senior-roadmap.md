# 주니어에서 시니어 개발자로 성장하는 로드맵

> **목표**: novov 같은 시니어 개발자 수준에 도달하기  
> **예상 시간**: 3-5년 (꾸준한 실천 기준)

---

## 📚 **Phase 1: 기초 다지기 (1년)**

### 1.1 **방어적 프로그래밍 (Defensive Programming)**

#### 목표
- null/undefined 체크 기본화
- 타입 안정성 이해

#### 학습 항목
- [ ] TypeScript `strict` mode 완벽 이해
- [ ] null coalescing (`??`), optional chaining (`?.`) 활용
- [ ] non-null assertion (`!`) vs type casting (`as`) 구분
- [ ] try-catch와 명시적 에러 처리

#### 실전 연습
```typescript
// ❌ 피해야 할 패턴
const value = someArray[0]!;
const user = getUser()!;

// ✅ 권장 패턴
const firstItem = someArray[0];
if (!firstItem) {
    console.error("Array is empty");
    return;
}

const user = getUser();
if (!user) {
    throw new Error("User not found");
}
```

#### 체크리스트
- [ ] 3개 프로젝트에서 타입 에러 0개 달성
- [ ] PR에서 non-null assertion 없이 코드 제출
- [ ] 에러 처리 5가지 패턴 숙달

---

### 1.2 **메모리 관리 이해**

#### 목표
- 메모리 누수 원인 파악
- GC(Garbage Collection) 기본 개념

#### 학습 항목
- [ ] JavaScript 메모리 모델 이해
- [ ] WeakRef, WeakMap, WeakSet 활용
- [ ] 순환 참조 문제 인식
- [ ] 개발자 도구 - Memory 탭 분석법

#### 실전 연습
```typescript
// ❌ 메모리 누수 위험
class EventManager {
    listeners: Listener[] = []; // 등록만 하고 제거 안 함
}

// ✅ 메모리 안전
class EventManager {
    private listeners = new WeakSet<Listener>();
    
    addListener(listener: Listener) {
        this.listeners.add(listener);
    }
}
```

#### 체크리스트
- [ ] 프로젝트에서 10시간 연속 사용 후 메모리 안정적
- [ ] WeakMap/WeakSet 1개 이상 실제 적용
- [ ] Chrome DevTools로 메모리 누수 감지 가능

---

### 1.3 **함수형 설계**

#### 목표
- 순수 함수 개념
- 사이드 이펙트 최소화

#### 학습 항목
- [ ] 순수 함수 (Pure Function) 개념
- [ ] 불변성 (Immutability)
- [ ] 함수 조합 (Function Composition)
- [ ] 고차 함수 (Higher-Order Function)

#### 실전 연습
```typescript
// ❌ 비순수 함수
let counter = 0;
function processData(items) {
    counter++; // 외부 상태 변경
    return items.map(i => i * 2);
}

// ✅ 순수 함수
function processData(items: number[]): number[] {
    return items.map(i => i * 2);
}
```

#### 체크리스트
- [ ] 작성한 함수의 50% 이상 순수 함수
- [ ] 1개 프로젝트에서 사이드 이펙트 명시 주석
- [ ] 함수형 라이브러리 (lodash/fp, ramda) 활용

---

## 🎯 **Phase 2: 실력 다지기 (1-2년)**

### 2.1 **에러 처리 체계**

#### 목표
- 체계적인 에러 처리
- 로깅과 모니터링 기본

#### 학습 항목
- [ ] 커스텀 에러 클래스 설계
- [ ] 에러 경계 (Error Boundary) 이해
- [ ] 로깅 전략 수립
- [ ] 에러 추적 도구 (Sentry 등) 경험

#### 실전 연습
```typescript
// 커스텀 에러 클래스
class HomepageError extends Error {
    constructor(
        message: string,
        public readonly code: string,
        public readonly context?: Record<string, unknown>
    ) {
        super(message);
    }
}

// 체계적 에러 처리
try {
    await openNote(path);
} catch (error) {
    if (error instanceof HomepageError) {
        logger.error("Homepage operation failed", {
            code: error.code,
            message: error.message,
            context: error.context
        });
    }
}
```

#### 체크리스트
- [ ] 프로젝트에서 커스텀 에러 3가지 정의
- [ ] 모든 catch 블록에서 로깅 구현
- [ ] Sentry/LogRocket 같은 도구 1개 이상 경험

---

### 2.2 **복잡한 로직 단순화**

#### 목표
- 큰 함수를 작은 단위로 분해
- 코드 가독성 극대화

#### 학습 항목
- [ ] 함수 추출 (Extract Function)
- [ ] 메서드 추출 (Extract Method)
- [ ] 조건 단순화 (Simplify Conditionals)
- [ ] 루프 단순화

#### 실전 연습
```typescript
// ❌ 복잡한 함수 (novov 개선 전)
async launchLeaf(mode: Mode): Promise<void> {
    if (mode !== Mode.ReplaceAll) {
        const alreadyOpened = this.getOpened();
        if (alreadyOpened.length > 0) {
            // ... 복잡한 로직 ...
        } else if (mode == Mode.Retain && emptyActiveView(this.app)) {
            mode = Mode.ReplaceLast;
        }
    }
    // ... 더 많은 로직 ...
}

// ✅ 단순화된 함수 (novov 개선 후)
async launchLeaf(mode: Mode): Promise<void> {
    if (await this.activateIfAlreadyOpen(mode)) return;
    await this.clearExistingLeaves(mode);
    await this.createAndConfigureLeaf();
}

private async activateIfAlreadyOpen(mode: Mode): Promise<boolean> {
    // 한 가지 일만 함
}
```

#### 체크리스트
- [ ] 30줄 이상 함수 모두 20줄 이하로 리팩토링
- [ ] 코드 복잡도(cyclomatic complexity) 5 이하
- [ ] 함수명 읽기만 해도 역할이 명확

---

### 2.3 **테스트 작성 습관**

#### 목표
- 테스트 주도 개발 (TDD) 이해
- 80% 이상 테스트 커버리지

#### 학습 항목
- [ ] Unit Test 작성
- [ ] Integration Test 작성
- [ ] Mock과 Stub 활용
- [ ] 테스트 틀 (Jest, Vitest 등)

#### 실전 연습
```typescript
describe("Homepage", () => {
    it("should gracefully handle null activeFile", async () => {
        // Arrange
        const plugin = createMockPlugin({
            getActiveFile: () => null
        });
        
        // Act
        await plugin.setToActiveFile();
        
        // Assert
        expect(plugin.data.value).toBe(undefined);
    });
    
    it("should return early when activeFile doesn't exist", () => {
        // 메서드가 조용히 실패해야 함
    });
});
```

#### 체크리스트
- [ ] 모든 프로젝트에서 최소 테스트 작성
- [ ] 커버리지 80% 이상 달성 1회
- [ ] Jest/Vitest 기본 숙달

---

### 2.4 **기술 부채 관리**

#### 목표
- 정기적인 코드 정리
- 업그레이드 문화 형성

#### 학습 항목
- [ ] ESLint, Prettier 설정 및 자동화
- [ ] 정기적인 의존성 업데이트
- [ ] 리팩토링 스케줄링
- [ ] 기술 부채 추적

#### 실전 연습
```bash
# 매월 1회 정기 점검
npm audit
npm update
npm run lint -- --fix
npm run format

# 기술 부채 기록
git commit -m "chore: Update ESLint and fix violations"
```

#### 체크리스트
- [ ] 1개 프로젝트에서 모든 lint 에러 0개
- [ ] 의존성 최신 유지 (최대 2버전 뒤)
- [ ] 월 1회 이상 리팩토링 커밋

---

## 💪 **Phase 3: 깊이 더하기 (1-2년)**

### 3.1 **성능 최적화**

#### 목표
- 알고리즘 복잡도 이해
- 프로파일링과 최적화

#### 학습 항목
- [ ] 시간 복잡도/공간 복잡도 (Big O)
- [ ] 메모화(Memoization)
- [ ] 성능 프로파일링
- [ ] 번들 크기 최적화

#### 실전 연습
```typescript
// ❌ O(n²) - 비효율
function findDuplicates(arr: number[]): number[] {
    const duplicates = [];
    for (let i = 0; i < arr.length; i++) {
        for (let j = i + 1; j < arr.length; j++) {
            if (arr[i] === arr[j]) duplicates.push(arr[i]);
        }
    }
    return duplicates;
}

// ✅ O(n) - 효율적
function findDuplicates(arr: number[]): number[] {
    const seen = new Set<number>();
    const duplicates = new Set<number>();
    for (const num of arr) {
        if (seen.has(num)) duplicates.add(num);
        seen.add(num);
    }
    return Array.from(duplicates);
}
```

#### 체크리스트
- [ ] 모든 알고리즘 복잡도 명시 (주석)
- [ ] 1개 프로젝트에서 성능 30% 이상 개선
- [ ] Chrome DevTools Performance 탭 분석 가능

---

### 3.2 **시스템 설계**

#### 목표
- 확장 가능한 아키텍처
- 디자인 패턴 이해

#### 학습 항목
- [ ] 디자인 패턴 (Singleton, Factory, Observer 등)
- [ ] SOLID 원칙
- [ ] 마이크로아키텍처
- [ ] 플러그인 시스템 설계

#### 실전 연습
```typescript
// 플러그인 시스템 (확장성 높음)
interface Plugin {
    initialize(): void;
    execute(): Promise<void>;
}

class PluginManager {
    private plugins = new Map<string, Plugin>();
    
    register(name: string, plugin: Plugin): void {
        this.plugins.set(name, plugin);
    }
    
    async run(): Promise<void> {
        for (const plugin of this.plugins.values()) {
            await plugin.execute();
        }
    }
}
```

#### 체크리스트
- [ ] SOLID 원칙 5가지 설명 가능
- [ ] 3개 이상 디자인 패턴 프로젝트에 적용
- [ ] 새 기능을 기존 코드 수정 없이 추가 가능

---

### 3.3 **타입 시스템 마스터**

#### 목표
- 고급 TypeScript 기법
- 런타임 안정성 극대화

#### 학습 항목
- [ ] 조건부 타입 (Conditional Types)
- [ ] 제네릭 고급 활용
- [ ] 유틸리티 타입
- [ ] 타입 가드 (Type Guard)

#### 실전 연습
```typescript
// 고급 타입 활용 (novov 코드와 유사)
type HomepageKey<T> = {
    [K in keyof HomepageData]: HomepageData[K] extends T ? K : never
}[keyof HomepageData];

// 타입 가드
function isFileView(view: View): view is FileView {
    return view.getViewType() === "file";
}

// 활용
if (isFileView(currentView)) {
    // 이제 currentView.file은 존재함을 보장
    const file = currentView.file;
}
```

#### 체크리스트
- [ ] 고급 타입 5가지 이상 프로젝트에 적용
- [ ] 타입 에러 0개 달성 지속
- [ ] 동료에게 고급 타입 설명 가능

---

### 3.4 **문서화와 커뮤니케이션**

#### 목표
- 명확한 코드 문서화
- 효과적인 PR 리뷰

#### 학습 항목
- [ ] 코드 주석 작성 (좋은 주석)
- [ ] README 작성
- [ ] ADR (Architecture Decision Record)
- [ ] 커밋 메시지 규칙

#### 실전 연습
```typescript
/**
 * 활성 파일을 홈페이지로 설정
 * 
 * @remarks
 * - 활성 파일이 없으면 조용히 종료
 * - 설정은 자동 저장됨
 * - 사용자에게 성공 알림 표시
 * 
 * @throws {Error} 설정 저장 실패 시
 * 
 * @example
 * ```typescript
 * await plugin.setToActiveFile();
 * ```
 */
async setToActiveFile(): Promise<void> {
    const activeFile = this.app.workspace.getActiveFile();
    if (!activeFile) return;
    // ...
}
```

#### 체크리스트
- [ ] 모든 공개 함수에 JSDoc 주석
- [ ] 커밋 메시지 5줄 이상 (왜, 무엇, 결과)
- [ ] README 3개 프로젝트에서 100줄 이상

---

## 🏆 **Phase 4: 시니어 단계 (진행 중)**

### 4.1 **팀 리더십**

#### 목표
- 코드 리뷰 리더
- 기술 결정 리더

#### 학습 항목
- [ ] 효과적인 코드 리뷰
- [ ] 기술 제안 (RFC)
- [ ] 멘토링 (주니어 가르치기)
- [ ] 팀 표준 수립

#### 실전 활동
```
매주:
- 팀원 코드 리뷰 (2-3명)
- 기술 논의 회의 (1회)

매달:
- 기술 블로그/발표 (1회)
- 새로운 기술 검토 (1건)

매년:
- 프로젝트 아키텍처 설계 (2-3개)
```

---

### 4.2 **오픈소스 기여**

#### 목표
- 커뮤니티에 기여
- 글로벌 표준 이해

#### 학습 항목
- [ ] 오픈소스 프로젝트 이해
- [ ] PR 작성 및 리뷰
- [ ] 이슈 해결
- [ ] 유지보수 경험

#### 체크리스트
- [ ] 유명 프로젝트 PR 10개 이상 병합
- [ ] 개인 오픈소스 프로젝트 운영
- [ ] 스타 100개 이상인 프로젝트 기여

---

### 4.3 **지속적 성장**

#### 목표
- 시니어 수준 유지
- 새로운 기술 습득

#### 학습 항목
- [ ] 새로운 언어/프레임워크 1년마다
- [ ] 학술 논문/알고리즘 연구
- [ ] 컨퍼런스 발표
- [ ] 책 집필/공개 강의

#### 체크리스트
- [ ] 분기별 새로운 기술 학습
- [ ] 년 1회 이상 컨퍼런스/밋업 발표
- [ ] 블로그/유튜브 정기 발행 (월 1회 이상)

---

## 📊 **진행도 추적 표**

| Phase | 기간 | 주요 성과 | 완료도 |
|-------|------|---------|--------|
| **Phase 1** | 1년 | 방어적 코딩, 메모리 관리 기본화 | [ ] |
| **Phase 2** | 1-2년 | 에러 처리, 복잡도 관리, 테스트 80% | [ ] |
| **Phase 3** | 1-2년 | 성능 최적화, 시스템 설계, 타입 마스터 | [ ] |
| **Phase 4** | 진행 중 | 팀 리더십, 오픈소스, 글로벌 영향력 | [ ] |

---

## 🎯 **체크포인트별 자체 평가**

### 1년 후 (Phase 1 완료)
- [ ] PR에서 타입 에러 없음
- [ ] 메모리 누수 없는 코드 작성
- [ ] 함수 20줄 이하 유지
- [ ] 기본적인 테스트 작성 가능

### 2-3년 후 (Phase 2 완료)
- [ ] 커버리지 80% 이상
- [ ] 기술 부채 정기적 관리
- [ ] 복잡한 로직을 단순하게 설계
- [ ] 좋은 에러 처리 사례 다수

### 4-5년 후 (Phase 3 완료)
- [ ] 성능 최적화 경험 풍부
- [ ] 시스템 아키텍처 설계 능력
- [ ] 고급 TypeScript 자유롭게 사용
- [ ] novov 수준의 코드 퀄리티

### 5년+ (Phase 4 진행 중)
- [ ] 팀 기술 표준 수립
- [ ] 오픈소스 유지보수자
- [ ] 컨퍼런스 발표 경험
- [ ] 멘토로서 팀원 성장 주도

---

## 💡 **매일 실천 항목**

```
모든 날:
1. 코드 작성할 때 "이게 실패하면?" 생각하기
2. null/undefined 체크 습관화
3. 함수를 작은 단위로 분해 생각하기

매주:
1. 코드 리뷰 1건 이상 (동료 or 오픈소스)
2. 기술 문서 1개 읽기
3. 자신의 코드 리팩토링 (1시간)

매달:
1. 기술 블로그 글 1개 작성
2. 새로운 패턴 1개 학습 및 적용
3. 과거 코드 리뷰 (기술 부채 확인)

매년:
1. 개인 프로젝트 1개 완성
2. 오픈소스 기여 10개 이상
3. 기술 서적 3-5권 읽기
```

---

## 🚀 **성공 사례: novov**

**현재 상태**:
- ✅ Phase 3-4 단계 진행 중
- ✅ 272개 커밋으로 검증된 코딩 능력
- ✅ 방어적 프로그래밍 완벽 숙달
- ✅ 기술 부채 정기 관리
- ✅ 오픈소스 유지보수 중

**당신도 이 길을 따를 수 있습니다!** 🎯

---

## 📞 **마지막 조언**

> 시니어가 되는 것은 "더 많이 아는 것"이 아니라  
> **"더 안전하게 생각하는 것"**입니다.

- 버그를 빨리 고치는 것보다 버그를 **미리 방지**하는 능력
- 코드를 빠르게 짜는 것보다 **읽기 쉽게** 짜는 능력
- 기능을 많이 추가하는 것보다 **안정성을 유지**하는 능력

**꾸준함이 최고의 비결입니다.** 💪
