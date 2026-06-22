State
시스템이 이전 상호작용/요청의 결과를 기억하는 것
시간이 지나도 유지되는 데이터를 가지고 있다.

Stateless
각 요청이 완전히 독립적
이전 요청에 대한 정보를 전혀 가지고 있지 않다.

### 비교

State
- 데이터 보관: 서버/시스템이 보관
- 요청 간 의존성: 있음(따라서 순서가 중요)
- 스케일링: 어려움(서버 고정 필요)
- 장애 복구: 복잡(상태 손실 위험)
- 대표 예시: DB 세션, 게임 서버, WebSocket

Stateless
- 데이터 보관: x
- 요청 간 의존성: x
- 스케일링: 쉬움
- 장애 복구: 단순(재시작해도 문제 없음)
- 대표 예시: REST API, HTTP 기본 동작

### 실무 예시
`GET /user/123`
로그인 상태를 유지하려면 세션(state)을 인위적으로 추가해야함.
- 쿠키 + 세션 ID (서버가 state 보관)
- JWT 토큰 (클라이언트가 state를 들고 다님, 서버는 stateless 유지)

이것이 stateless 프로토콜 위에서 state를 흉내내는 대표적 패턴

REST API
REST는 의도적으로 stateless 지향
서버가 클라이언트 상태를 기억하지 않음
매 요청에 필요한 정보(인증 토큰, 파라미터)를 전부 담아서 보냄.

왜냐?
- 서버 여러 대를 둬도 아무 서버나 처리 가능 (⇒ 로드밸런싱 쉬움)
- 한 서버 죽어도 다른 서버로 바로 대체 가능
- 캐싱하기 쉬움

마이크로서비스/분산 시스템
**상태를 어디에 두느냐**가 아키텍쳐의 핵심 결정 중 하나
Stateful 서비스
- 인메모리 캐시 서버 (Redis 자체는 stateful)
- WebSocket 연결 유지하는 채팅 서버
- 게임 서버 (플레이어 위치, 체력 등)

Stateless 서비스
- 단순 계산 API (입력 → 출력만)
- 이미지 리사이징 서비스
- 인증 토큰 검증 로직

### 프론트엔드 관점 (React 등)

```js
// Stateless 컴포넌트 - 같은 props면 항상 같은 결과
function Greeting({ name }) {
  return <div>안녕, {name}</div>;
}

// Stateful 컴포넌트 - 내부에 상태(state)를 가짐
function Counter() {
  const [count, setCount] = useState(0); // 이게 state
  return <button onClick={() => setCount(count + 1)}>{count}</button>;
}
```

"state"는 컴포넌트가 시간에 따라 변하는 자기만의 데이터를 가진다는 뜻.
같은 입력(props)이라도 내부 state 때문에 다른 출력이 나올 수 있다.

---
왜 stateless를 선호하는 경향이 있나?
1. 수평 확장(scale-out)이 쉬움: 서버 인스턴스를 그냥 늘리면 됨
2. 장애 격리: 한 인스턴스가 죽어도 상태 손실 없음
3. 테스트/디버깅 용이: 입력만 보면 동작을 예측 가능 (함수형 프로그래밍과 철학이 비슷함)
4. 캐싱 최적화: 같은 요청이면 같은 응답이 보장됨

하지만... 모든 걸 stateless로 만들 수는 없다.
로그인, 장바구니, 실시간 협업 같은 건 본질적으로 "기억"이 필요하므로.
따라서 실무에서는:
> "서버 자체는 stateless하게 만들고, state는 외부(DB, Redis, 클라이언트 토큰)에 위임한다."

라는 패턴이 정석

---
그러니까 변수는 props 같은 것이지, 함수는 기본적으로 stateless고,
전역변수가 state라는 거네. 그러면 static이라는 용어도 비슷한 역할로 나오는 걸까?

- 순수 함수, pure function ⇒ stateless 함수

[[static]]은 생명주기(lifetime)와 스코프(scope)에 관한 용어
state와는 본질이 다르다.

static은 "메모리에 한 번만 할당되고 프로그램 종료까지 유지"


나는 프론트엔드(아마 React) 내의 복잡한 설계에서,
state라는 것이 어떻게 실제로 사용되고 있는 건지 그 패턴이 궁금하다.













