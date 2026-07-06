E2E 테스트
- Cypress
- => Playwright

Headless 모드, 1개 워커
순수 문법
요소 찾을 때 엄격한 

사용법
```ts
const config = defineConfig({
  workers: process.env.CI ? 2 : '50%',
});
```

API response를 intercept 하기
```ts
const getPizza = async (page: Page) => {
  await page.route(`/api/pizza/22`, async (route) => {
    const body = JSON.stringify(myPizza);
	await route.fulfill({ body });
  });
};
```

`page.route(url, func);`

