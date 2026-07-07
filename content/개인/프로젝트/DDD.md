[[DDD 예시 코드]]
## 안티 패턴
도메인 객체가 단순 getter/setter만 가진 데이터 덩어리,
모든 로직이 별도의 서비스 계층에 절차적으로 작성되어있느 ㄴ상태
빈약한 도메인 모델(Anemic Domain Model) 이라고 정의

## DDD: 실용
- Entity
- Value Object
- Aggregate
- Repository
- Domain Service
- Domain Event

객체
- Entity: 식별자가 존재, 상태가 바뀌어도 같은 것
- Value Object: [[불변]], 식별자가 없음, 속성 값 자체가 동일하면 같은 것

Aggregate Root를 통해서만
- method를 통해서만
	- 변수: `private`
	- 규칙(불변식, Invariant)은 여기서 미리 만든다
- 규칙을 지켜야 할 책임은 Order(Aggregate Root)에 있다.
- 한 트랜잭션에서는 원칙적으로 하나의 Aggrregate만 수정 권장

Domain Service는 Entity나 Value Object에 속하지 않을 때,
여러 도메인 객체를 조합해서 처리하는 무상태(stateless) 객체
- 예: "두 계좌 간 이체"

Repository는 Aggregate를 영속화하고, 가져오는 책임을 추상화
도메인 계층은 인터페이스만 두고
실제 DB 접근 코드(인프라 계층)는 인터페이스를 **구현**하는 형태로 분리
Repository는  컬렉션(Collection)처럼 보이게 설계하라.
- `findById`, `save` 등의 메모리 안의 컬렉션을 다루는 것처럼

==Domain Event==는 도메인 안에서 일어난, 
다른 부분이 알아야 할 의미있는 사건: 즉, 정보 전달이 목적

Factory
복잡한 Aggregate를 생성할 때, 생성 로직을 캡슐화하는 패턴
생성자 하나로 표현하기 어려운 복잡한 초기화 규칙이 있을 때,
별도의 Factory 객체나 정적 메서드로 분리한다.

## DDD: 개념
도메인이란, 소프트웨어가 다루고자 하는 업무 영역 그 자체
- Domain: commerce
	- Subdomain: 주문, 결제, 배송, 재고, 추천

Subdomain의 구분
- Core Domain 핵심 도메인
- Supporting Domain 지원 도메인
- Generic Domain 일반 도메인

Bounded Context
하나의 개념을 부서별로 다르게 받아들이는 것
부서 내의 그 역할만 집중하는 개념
개발자 - 기획자(또는 현업) 언어 일치

Context Mapping
다른 바운디드 컨텍스트끼리 관계 정립
관계의 종류:
- Conformist: 한 팀이 다른 팀을 따름
- Shared Kernel: 두 팀이 공유 모델을 함께 운영
- Open Host Service: 상류 팀이 하류 팀에게 번역 계층을 제공
- Anti-Corruption Layer: 자기 컨텍스트에 맞춰 번역해서 격리

---