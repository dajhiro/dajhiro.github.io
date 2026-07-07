## Astro: 환경변수 사용
Astro는 Vite의 내장 환경 변수 지원에 대한 접근 권한을 제공
- 현재 프로젝트의 구성 값: `site`, `base` 등
- 프로젝트가 개발 또는 프로덕션 환경에서 실행 중인지 여부

### Vite의 내장 지원
빌드 시 정적으로 대체되는 환경 변수에 대한 Vite의 내장 지원을 사용
환경 변수를 다루기 위한 **모든 메서드** 사용 가능

서버 측 코드에서는 모두
클라 측 코드에서는 `PUBLIC_`이 붙은 환경 변수만
`.env`
```ini
SECRET_PASSWORD=password123
PUBLIC_ANYBODY=there
```
접근 방법: `import.meta.env.PUBLIC_ANYBODY`
- [!] `.env` 파일은 구성 파일에서 로드되지 않는다

### TypeScript를 위한 IntelliSense
`astro/client.d.ts`에서 `import.meta.env`에 대한 타입 정의를 제공
`.env.[mode]` 파일에서 더 많은 사용자 정의 환경 변수를 정의할 수 있지만
`PUBLIC_` 접두사가 붙은 사용자 저으이 환경 변수에 대해 TypeScript IntelliSense를 얻고 싶을 수 있다.
`src/`에 `env.d.ts` 파일을 생성하여 전역 타입을 확장
`ImportMetaEnv`를 다음과 같이 구성
`src/env.d.ts`
```ts
interface ImportMetaEnv {
  readonly DB_PASSWORD: string;
  readonly PUBLIC_POKEAPI: string;
  // ...
}

interface ImportMeta {
  readonly env: ImportMetaEnv;
}
```

## 기본 환경 변수
- `import.meta.env.MODE`: 사용자가 실행 중인 모드
    - `development`, `production`
- `import.meta.env.PROD`: 프로덕트 환경이면 true
- `import.meta.env.DEV`: 개발 환경이면 true
- `import.meta.env.BASE_URL`: 사이트가 제공되는 기본 URL. `base` 옵션
- `import.meta.env.SITE`: `astro.config`에 지정된 `site` 옵션
    - `import.meta.env.ASSETS_PREFIX`: `build.assetsPrefix` 옵션

```ts
const isProd = import.meta.env.PROD;
```

### 환경 변수 설정
프로젝트 디렉터리의 `.env` 파일
`.env`
```ini
DB_PASSWORD="foobar"
PUBLIC_POKEAPI="https://pokeapi.co/api/v2"
```

다른 환경 변수 집합을 사용하기
- 기본: `.env.production`, `.env.development`
- 사용자 정의: `.env.testing`, `.env.staging` 

`--mode` 플래그를 사용하여 다른 값 전달하기
```sh
# "staging" API에 연결된 개발 서버를 실행
npm run astro dev -- --mode staging

# 추가 디버그 정보와 함께 "production" API에 연결되는 사이트 빌드
npm run astro build -- --devOutput

# "testing" API에 연결되는 사이트를 빌드
npm run astro build -- --mode testing
```

### Astro 구성 파일
Astro는 다른 파일을 로드하기 전에 `astro.config.mjs`을 평가한다
- CLI의 환경변수에 접근: `process.env`
- `.env` 파일을 수동으로 로드: `.env`

`astro.config.mjs`
```js
import { loadEnv } from "vite";

const { SECRET_PASSWORD } = loadEnv(
  process.env.NODE_ENV,
  process.cwd(), ""
);
```

### CLI 사용
프로젝트를 실행할 때 환경변수를 추가할 수도 있다
```sh
PUBLIC_POKEAPI=https://pokeapi.co/api/v2 npm run dev
```

### 환경 변수 가져오기
Astro의 환경 변수는 `process.env` 대신
ES2020에 추가된 `import.meta` 기능을 사용하여
`import.meta.env`로 접근

```ts
// import.meta.env.SSR === true 일 경우 가져온다.
const data = await db(import.meta.env.DB_PASSWORD);

// import.meta.env.SSR === false 일 경우 가져온다.
const data = await(`${import.meta.env.PUBLIC_POKEAPI}/pokemon/squirtle`);

```

SSR을 사용하는 경우 사용중인 **SSR 어댑터**에 따라 런타임에 환경 변수에 접근할 수 있음. [[Cloudflare 어댑터]] 등. Astro는 먼저 서버 환경에서 변수를 확인하고, 존재하지 않으면 `.env` 파일에서 찾는다.

## 타입 안전 환경 변수
`astro:env` API를 사용하면
- 설정한 환경 변수에 대한
- 타입 안전 스키마를 구성

### 사용법
### 스키마 정의
스키마를 구성하려면 Astro 구성에 `env.schema` 옵션을 추가
그 후 `envField` 도우미를 사용하여 다음 타입으로 등록 가능
- `string`, `number`, `enum`, `bool`

```js
import { defineConfig, envField } from "astro/config";

export default defineConfig({
  env: {
    schema: {
      API_URL: envField.string({ context: "client", access: "public", optional: true }),
      PORT: envField.number({ context: "server", access: "public", default: 4321 }),
      API_SECRET: envFiled.string({ context: "server", access: "secret" }),
    }
  }
})
```
`astro sync`를 실행하여 타입만 생성할 수 있음

### 스키마 변수 사용
`/client` 또는 `/server` 모듈에서 정의된 변수를 가져와서 사용

```tsx
---
import { API_URL } from "astro:env/client";
import { API_SECRET_TOKEN } from "astro:env/server";

const data = await fetch(`${API_URL}/users`, {
  method: "GET",
  headers: {
    "Content-Type": "application/json",
    "Authorization": `Bearer ${API_SECRET_TOKEN}`
  },
})
---

<script>
  import { API_URL } from "astro:env/client";
  fetch(`${API_URL}/ping`)
</script>
```

### 변수 타입
스키마에 정의된 설정의 조합에 따라 세 가지 종류의 환경 변수를 사용할 수 있음
- `context` (`"client"` 또는 `"server"`)와
- `access` (`"secret"` 또는 `"public"`) 

공개 클라이언트 변수: 클라이언트/서버
```js
import { API_URL } from "astro:env/client";
```

공개 서버 변수: 서버, 최종 서버 번들에 포함
```js
import { PORT } from "astro:env/server";
```

비밀 서버 변수: 서버, 최종 번들의 일부가 아님
```js
import { API_SECRET } from "astro:env/server";
```

기본적으로, `astro:env/server` 모듈에서 무언가를 가져올 때마다
- 모든 비밀 변수가 검증됨
- 비밀 변수를 가져오지 않은 경우에도 검증될 수 있음
- 빌드 중에 이 검증을 통과하기 위해 더미 환경 변수를 전달해야 할 수도 있음

`validateSecrets: true`를 구성하여 시작 시 비밀 변수 유효성 검사를 활성화할 수도 있음

### 데이터 타입
`string`, `number`, `enum`, `bool`

```js
import { envField } from "astro/config";

envField.string({
  // context & access
  optional: true,
  default: "foo",
})

envField.enum({
  // context & access
  values: ["foo", "bar", "baz"],
  optional: true,
  default: "baz",
})
```

### 비밀 변수를 동적으로 검색
스키마를 정의했음에도 불구하고
- 특정 비밀 변수의 원시 값을 검색하거나
- 스키마에 정의되지 않은 비밀 변수를 검색

`astro:env/server`에서 내보낸 `getSecret()`을 사용
```js
import {
  FOO, // boolean
  getSecret
} from "astro:env/server";

getSecret("FOO"); // string | undefined
```

### 제한 사항
`astro:env`는 [[가상 모듈]]이므로 Astro 컨텍스트에서만 사용할 수 있습니다.
예를 들어 다음과 같은:
- 미들웨어
- Astro 라우트 및 엔드포인트
- Astro 컴포넌트
- 프레임워크 컴포넌트
- 모듈

다음과 같은 곳에서는 사용할 수 없으므로 `process.env`
- `astro.config.mjs`
- 스크립트

