# Tailwind
### 핵심 마인드셋
Tailwind는 클래스를 조합하는 방식
- CSS를 작성하는 것이 아니다.
- 빠르고 일관성있는 UI가 목표

```jsx
<!-- margin: 1rem → m-4 (1rem = 4 단위) -→
<!—- padding: 0.5rm → p-2 -->
<!-- font-size 1.25rem → text-xl -->
<!-- color: blue-500 → text-blue-500 / bg-blue-500 -->

<div class="mt-4 px-6 py-3 text-xl font-bold text-white bg-blue-500 rounded-lg">
버튼
</div>
```

### 특징
- 기본 패턴: `[attr]-[value]`
	- `[attr]-[[attr]-[value]]`
- 반응형은 접두사로: `md:flex-row`
- 상태 변형 (hover, focus, active): `hover:bg-blue-600`
- 재사용 — 컴포넌트 추출 (같은 클래스 조합이 반복될 때)
- 커스터마이징: `tailwind.config.js`
- 다크모드: `module.exports = {darkMode: 'class'}`
	- `<div class="bg-white dark:bg-gray-900">`


- [[shadcn]]
