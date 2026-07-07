## 수동 설정 -- Scratch
```sh
# 디렉터리 생성 후 진입
npm init
npm install astro
```

### 스크립트 설정
```json
// package.json
{
  "scripts": {
    "dev": "astro dev",
    "build": "astro build",
    "preview": "astro preview"
  },
}
```

### `src/pages/index.astro` 페이지 만들기
```jsx
---
// Astro에 오신 것을 환영합니다!
// 이 삼중 대시(---) 코드 펜스 사이의 모든 것은 "컴포넌트 프런트매터"입니다.
// 브라우저에서 절대 실행되지 않습니다.
console.log('이것은 브라우저가 아닌 터미널에서 실행됩니다!')
---
<!-- 아래는 "컴포넌트 템플릿"입니다.
    HTML일 뿐이지만, 훌륭한 템플릿을 만드는 데 도움이 되는 몇 가지 마법이 뿌려져 있습니다 -->
<html>
  <body>
    <h1>Hello, World!</h1>
  </body>
</html> 
<style>
  h1 {
    color: orange;
  }
</style>
```

`public/robots.txt`: 첫번째 정적 자산(asset) 만들기
```txt
# 예시: 모든 봇이 사이트를 스캔하고 색인하도록 허용합니다
# 전체 구문: https://developers.google.com/search/docs/advanced/robots/create-robots-txt
User-agent: *
Allow: /
```

### `astro.config.mjs` 설정 파일 만들기
```js
import { defineConfig } from "astro/config";

// https://astro.build/config
export default defineConfig({});
```
React, Svelte 등 UI 프레임워크 컴포넌트를 포함하거나
프로젝트에서
MDX, Partytown 등의 다른 도구를 사용하려면

통합(Integration)을 수동으로 가져오고 구성합니다.

### `tsconfig.json` TypeScript 지원 추가하기
```json
{
  "extends": "astro/tsconfig/base"
}
```
템플릿 설정
`base`, `strict`, `stricttest`

### 최종 결과
```
node_modules/
public/
  robots.txt
src/
  pages/
  index.astro
astro.config.mjs
package-lock.json
package.json
tsconfig.json
```
