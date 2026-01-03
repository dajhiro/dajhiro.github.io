## 목록
https://astro.build/integrations/
### 공식
renderer: frontend framework
- `@astrojs/alpinejs`
- **`@astrojs/react`**

adaptor
- `@astrojs/cloudflare`
- `@astrojs/node`
- `@astrojs/vercel`

etc.
- **`@astrojs/mdx`**
- `@astrojs/db`
- `@astrojs/sitemap`
- `@astrojs/markdoc`
- `@astrojs/partydown`

## 추가
### 자동
https://docs.astro.build/ko/guides/integrations-guide/
```sh
npx astro add [react] [...]
```

### 수동
astro.config.mjs
```js
import { defineConfig } from 'astro/config';
import installedIntegration from '@astrojs/vue';
import localIntegration from './my-integration.js';

export default defineConfig({
  integrations: [
    // 1. 설치된 npm 패키지에서 가져온다.
    installedIntegration(),
    // 2. 로컬 .js 파일에서 가져온다.
    localIntegration(),
    // 3. 인라인 객체를 작성한다.
    { name: 'namespace:id', hooks: { /* ... */ }}
  ]
});
```

### 절차
설치
```sh
npm install @astrojs/sitemap
```

설정
```js
import { defineConfig } from 'astro/config';
import sitemap from '@astrojs/sitemap';

export default defineConfig({
  // ...
  integrations: [sitemap()],
  // ...
});
```

맞춤 옵션
실제 **통합 객체**를 반환하는 **[[팩토리 함수]]**
인수와 옵션을 전달
```js
integrations:  [
  // 예: 인수를 사용하여 통합 사용자 정의
  sitemap({ filter: true })
]
```

통합 켜고 끄기
```js
integrations:  [
  // 예: Windows에서 사이트맵 작성 건너뛰기
  process.platform !== 'win32' && sitemap()
]
```

## 업데이트
자동
```sh
npx @astrojs/upgrade
```

수동
```sh
npm install @astrojs/react@latest
```

## 제거
```sh
npm uninstall @astrojs/react
```

astro.config.*
```js
integrations: [
  // react()
]
```
