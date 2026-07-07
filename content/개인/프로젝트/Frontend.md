자주 마주치는 버그

### 비동기 / 상태관리
경쟁 조건(Race condition)
- API 요청이 순서 보장 없이 응답할 때

언마운트 후 setState
- React 내의 memory leak

stale closure
- 이벤트 핸들러나 `setInterval` 내에서 오래된 변수 참조
- `useEffect` 의존성 배열 누락

### DOM / 렌더링
hydration mismatch
SSR에서 서버가 렌더링한 HTML과 클라이언트가 렌더링한 결과가 다를 때.
`Date.now()`, `Math.random()`, 브라우저 전용 API(`window`, `localStorage`)를 서버에서 쓰면 발생.


z-index 지옥
쌓임 맥락(stacking context)을 이해 못 해서 숫자를 계속 올리는 것.
새 stacking context를 만든다는 걸 놓칠 때
- `transform`
- `opacity`
- `filter`

### 이벤트 / 입력
이벤트 핸들러 중복 등록
`addEventListener`를 컴포넌트 재렌더링마다 등록하면서, 정리cleanup를 안할 때















