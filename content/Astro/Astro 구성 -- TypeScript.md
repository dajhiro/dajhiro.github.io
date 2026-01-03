## [[Astro]]: TypeScript
`.tsx`를 가져오거나,
`.astro`에 TypeScript 코드를 작성
Astro 개발 서버에서 별도의 스크립트를 사용하여

사용 예: 컴포넌트의 props에 **타입 지정**

### 설정
`tsconfig.json`

```json
{
  "extends": "astro/tsconfigs/base",
  "include": [".astro/types.d.ts", "**/*"],
  "exclude": ["dist"],
}
```

템플릿
- `base`
- `strict`
- `strictest`

### Astro TypeScript 플러그인
VS Code를 사용하지 않을 때
편집기에서만 실행된다? 
`tsc` 명령은 `.astro`를 지원하지 않는다.
`astro check` 명령을 사용하여 `.astro`, `.ts` 파일을 모두 검사한다.
```sh
npm install @astrojs/ts-plugin
```

옵션 추가: `tsconfig`
```json
"compilerOptions": {
  "plugins": [
    {
      "name": "@astrojs/ts-plugin"
    },
  ],
}
```

### UI 프레임워크
Recat...

### 타입 가져오기
```ts
import type { SomeType } from "./script";
```
이렇게 하면 Astro 번들러가 가져온 타입을
JavaScript인 것처럼 잘못 번들링하려고 시도하는 엣지 케이스 방지

`tsconfig.json`에서 타입 가져오기를 적용
```json
{
  "compilerOptions": {
    "verbatimModuleSyntax": true
  }
}
```

### 별칭 가져오기
Astro는 `tsconfig.json` `paths` 구성에서 정의하는 [[별칭]] 가져오기를 지원
`src/pages/about/nate.astro`
```tsx
---
import HelloWorld from "@components/HelloWorld.astro";
import Layout from "@layouts/Layout.astro";
---
```

`tsconfig.json`
```json
{
  "compilerOptions": {
    "paths": {
      "@components/*": ["./src/components/*"],
      "@layouts/*": ["./src/layouts/*"]
    }
  }
}
```

### 전역 타입 확장하기
`src/env.d.ts`를 생성하여 사용자 정의 타입 선언을 추가하거나
`tsconfig.json` 없이 Astro의 타입을 활용할 수 있음

```ts
// 사용자 정의 타입 선언
declare var myString: string;

// Astro의 타입: tsconfig.json이 이미 있을 경우에는 필요하지 않음
/// <refrence path="../.astro/types.d.ts" />
```

### `window` 및 `globalThis` 확장
전역 객체에 속성을 추가하려는 경우
`src/env.d.ts` 파일에 `declare` 키워드를 사용하여 최상위 선언을 추가
```ts
declare var myString: string;
declare function myFunction(): boolean;
```
이렇게 하면
`window.myString`, `...`,  `globalThis.myFunction`까지 타입이 제공

`window`는 클라이언트 측 코드에서만
`globalThis`는 서버 측도 가능. 그러나 공유되지 않는다.

### 비표준 속성 추가
사용자 정의 속성 또는
CSS 속성에 대한 타입

`.d.ts` 파일에서 `astroHTML.JSX` 네임스페이스를 재선언하여 JSX 정의를 확장하면
비표준 속성 추가 가능
```ts
declare namespace astroHTML.JSX {
  interface HTMLAttributes {
    "data-count"?: number;
    "data-label"?: string;
  }
  
  // 스타일 객체에 사용자 정의 CSS 속성을 추가
  interface CSSProperties {
    "--theme-color"?: "black" | "white";
  }
}

```

`.astro`가 아닌 TypeScript 파일에서 사용하려면
삼중 슬래시 지시어를 사용

```ts
/// <reference types="astro/astro-jsx" /> 

type MyAttributes = astroHTML.JSX.ImgHTMLAttributes;
```

### 가져오기 사용하기
동적 가져오기를 사용하면
프로젝트 또는 외부 라이브러리에서 선언된 타입을 재사용하여
전역 타입을 확장할 수 있다.
`env.d.ts`
```ts
type Product = {
  id: string;
  name: string;
  price: number;
};

declare namespace App {
  interface Locals {
    orders: Map<string, Product[]>
    session: import("./lib/server/session").Session | null;
    user: import("my-external-liberary").User;
  }
}
```

`.d.ts`는 앰비언트 모듈 선언 파일
구문은 ES 모듈과 유사하지만
최상위 수준에서 가져오기/내보내기를 허용하지 않는다.
TypeScript가 이를 감지하면
모듈 확장 파일로 간주하여 전역 타입 정의가 깨질 수 있다.

### 컴포넌트 Props
Astro는 TypeScript를 통해 컴포넌트 props의 타입을 지원
활성화: 컴포넌트 **프런트매터**에 TypeScript `Props` 인터페이스 추가
`export` 구문을 사용할 수 있지만 필수는 아님

`src/components/HelloProps.astro`
```tsx
---
interface Props {
  name: string;
  greeting?: string;
}
const { greeting = "Hello", name } = Astro.props;
---
<h2>{greeting}, {name}!</h2>
```

컴포넌트의 일반적인 prop 타입 패턴
- props 또는 **슬롯 컨텐츠**를 사용하지 않는 경우
    - `type Props = Record<string, never>`를 사용
- 기본 슬롯에 자식을 전달해야 하는 경우
    - `type Props = { children: any; };`를 사용

### 타입 유틸리티
`astro@1.6.0`
- 일반적인 prop 타입 패턴을 위한 몇 가지 내장 유틸리티 타입 제공
- 이러한 타입은 `astro/types` 진입점에서 사용 가능

내장 HTML 속성
- Astro는 `HTMLAttributes` 타입을 제공
- 이 타입을 이용해 컴포넌트 props를 빌드할 수 있음

예: `<Link>` 컴포넌트 빌드 시 prop 타입에서 `<a>` 태그에 대한
기본 HTML 속성을 미러링하기 위해 다음을 수행

`src/components/Link.astro`
```tsx
---
import type { HTMLAttributes } from "astro/types";

// `type`를 사용
type Props = HTMLAttributes<"a">;

// 또는 `interface`를 사용
interface Props extends HTMLAttributes<"a"> {
  myProp?: boolean;
}

const { href, ...attrs } = Astro.props;
---
<a href={href} {...attrs}>
  <slot />
</a>
```

### `ComponentProp` 타입
`astro@4.3.0`
- 이 **타입 내보내기**를 사용하면
- 다른 컴포넌트가 `Props` 타입을 직접 내보내지 않아도
- 해당 컴포넌트에서 허용하는 `Props`를 참조할 수 있음

예제: `<Button />` 컴포넌트의 `Props` 타입을 참조하기
`src/pages/index.astro`
```tsx
---
import type { ComponentProps } from "astro/types";
import Button from "./Button.astro";

type ButtonProps = ComponentProps<typeof Button>;
---

```

### 다형적 타입
`astro@2.5.0`
다양한 **HTML 요소**로 렌더링할 수 있는 컴포넌트
타입 안정성을 갖춰 더 쉽게 빌드할 수 있도록 도와주는
`<Link>`와 같은 컴포넌트에 유용:
- 전달된 props에 따라
- `<a>` 또는 `<button>`으로 렌더링할 수 있는

예제: 모든 HTML 요소로 렌더링할 수 있는 완전한 타입의 다형적 컴포넌트 구현
`as` prop이 유효한 HTML 요소인지 확인하기 위해 `HTMLTag` 타입이 사용

```tsx
---
import type { HTMLTag, Polymorphic } from "astro/types";

type Props<Tag extends HTMLTag> = Polymorphic<{ as: Tag }>;

const { as: Tag, ...props } = Astro.props;
---
<Tag {...props} />
```

### `getStaticPaths()` 타입 추론
`astro@2.1.0`
Astro는 **동적 라우트**를 위한 `getStaticPaths()`함수에서
반환된 타입을 처리하는 도우미를 포함: 
- `InferGetStaticParamsType`으로 `Astro.params`의 타입
- `InferGetStaticPropsType`으로 `Astro.props`의 타입
- `GetStaticPaths`로 두 타입 모두

`src/pages/posts/[...id].astro`
```jsx
---
import type {
  InferGetStaticParamsType,
  InferGetStaticPropsType,
  GetStaticPaths,
} from "astro";

export const getStaticPaths = (async () => {
  const posts = await getCollection("blog");
  return posts.map((post) => {
    return {
      params: { id: post.id },
      props: { draft: post.data.draft, tilte: post.data.title },
    };
  });
}) satisfies GetStaticPaths;

type Params = InferGetStaticParamsType<typeof getStaticPaths>;
type Props = InferGetStaticPropsType<typeof getStaticPaths>;

const { id } = Astro.params as Params;
//                   ^? { id: string; }

const { title } = Astro.props;
//                      ^? { draft: boolean; title: string; }
---
```

### 타입 검사
`astro start` 및 `astro build` 명령은
- esbuild로 코드를 트랜스파일하지만
- 타입검사를 실행하지는 않습니다

코드에 TypeScript 오류가 포함된 경우 빌드되지 않도록 하려면
`package.json`의 "build" 스크립트를 다음과 같이 변경하세요.

```json
{
  "scripts": {
    "build": "astro check && astro build",
  },
}

```

### 문제 해결
동시에 여러 JSX 프레임워크의 타입 지정 시 오류 발생
해결: 사용하는 프레임워크에 맞게 `jsxImportSource` 설정을
- `react`(기본값)로 설정합니다.
- 그 후 충돌하는 파일에서 pragma 주석을 사용하세요

`jsxImportSource: react`의 경우 다음을 사용
```jsx
// Preact
/** @jsxImportSource preact */
```


