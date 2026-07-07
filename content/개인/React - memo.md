`memo`

Component의 Props가 변경되지 않은 경우
리렌더링을 건너 뛴다.

```jsx
const MemoizedComponent = memo(SomeComponent, arePropsEqual?)
```

React Complier는
모든 컴포넌트에 `memo`와 동일한 최적화를 자동으로 적용
따라서 수동으로 메모이제이션을 할 필요가 없음

=> Context

[[예시]]