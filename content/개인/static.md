```c
void counter() {
	static int count = 0;
	count++;
	printf("%d\n", count);
}

counter(); // 1
counter(); // 2
counter(); // 3
```

`static int count`
- 스코프(접근 가능성)는 함수 안(지역)인데
- 생명주기(생존 가능성)는 프로그램 전체

따라서 다음 세가지는 stateful하다고 정의할 수 있겠다.
- 전역변수
- static 지역변수
- static 멤버

---
절차 지향에서 state 사용으로 인한 side effect
함수가 "리턴값 계산" 외의 외부 세계에 영향을 주는 모든 것.

### 1. 외부 상태 변경 (State Mutation)

```js
let total = 0;

function addToTotal(x) {
  total += x;
  return total;
}
```

### 2. 인자(객체)를 직접 수정 (Mutation of arguments)

```js
function addItem(arr, item) {
  arr.push(item);
  return arr;
}

const myArr = [1, 2];
addItem(myArr, 3);
console.log(myArr); // [1, 2, 3] 예측 불가능성
```


- I/O 작업 (입출력)
	- [[콘솔]] 출력: 터미널 등
	- 파일 입출력: 파일 읽기/쓰기
	- 네트워크 요청: API 호출, DB 쿼리
- 예외 발생: 입력 → 출력 흐름 벗어남
- 환경 변수 변경

### 왜 이게 중요한가 (실무 관점)
- **테스트 용이성**: 순수 함수는 입력만 주면 테스트 끝. side effect 있는 함수는 mock, stub이 필요해서 테스트가 복잡해짐
- **디버깅**: side effect가 많으면 "어디서 이 값이 바뀌었는지" 추적하기 어려움
- **동시성/병렬처리**: 순수 함수는 여러 스레드에서 동시에 호출해도 안전(thread-safe). side effect 있으면 race condition 위험
- **NestJS 같은 백엔드에서**: 비즈니스 로직(계산)은 순수 함수로 분리하고, side effect(DB 접근, 외부 API 호출)는 Repository/Service 레이어로 격리하는 게 좋은 설계 패턴












