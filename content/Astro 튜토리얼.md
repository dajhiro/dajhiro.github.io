목표
1. 개발 환경 설정
2. [[#페이지 및 블로그 게시물 생성]]
3. Astro 컴포넌트를 사용하여 빌드
4. 로컬 파일 쿼리 및 작업
5. 사이트에 상호 작용 추가
6. 사이트를 웹에 배포

### Astro 프로젝트 만들기
create astro
```sh
npm create astro@lastest
```

```
 astro   Launch sequence initiated.

   dir   Where should we create your new project?
         ./tutorial

  tmpl   How would you like to start your new project?
         Use minimal (empty) template

  deps   Install dependencies?
         Yes

   git   Initialize a new git repository?
         Yes
```

### 개발 모드로 Astro 실행하기
개발하는 동안 파일이 바로 반영되게끔
```sh
npm run dev
```

### 홈페이지 수정하기
src/pages/index.astro
```jsx
---
---

<html lang="en">
  <head>
    <meta charset="utf-8" />
    <link rel="icon" type="image/svg+xml" href="/favicon.svg" />
    <meta name="viewport" content="width=device-width" />
    <meta name="generator" content="{Astro.generator}" />
    <title>Astro</title>
  </head>
  <body>
    <h1>Astro</h1>
  </body>
</html>

```

### 아니 netlify 이거 호스팅 공짜야?
https://claude.ai/chat/706bf89c-af63-4caf-ba19-ef1c551015a0
내 웹앱을 공짜로 호스팅할 수 있어?

내 웹앱에 백엔드 서버가 있고
REST 방식으로 소통할건데

- Vercel Next.js

## 페이지 및 블로그 게시물 생성
### Astro 페이지 만들기
`.astro` 구문을 사용하여 
`.md` 파일의 블로그 게시물 추가

`about.astro`
`blog.astro`

```jsx
<a href="/">Home</a>
<a href="/about/">About</a>
<a href="/blog/">About</a>
```

`src/pages/`
⇔ `"/"`

### Markdown 블로그 게시글 작성
- `src/pages/posts`
- `post-1.md` 작성하기
- https://localhost:4321/posts/page-1 확인

```jsx
<ul>
  <li><a href="/posts/post-1/">Post 1</a></li>
</ul>
```

### 동적 콘텐츠 추가
- 프런트매터에 페이지 제목을 정의하고 HTML에서 사용
- HTML 요소를 조건부로 표시
- 여러분에 관한 콘텐츠를 추가

```jsx
---
const pageTitle = "About Me";
---

<head>
  <title>{pageTitle}</title>
</head>
<body>
  <h1>{pageTitle}</h1>
</body>
```

### JavaScript 표현식 작성
```jsx
---
const pageTitle = "About Me";

const identity = {
  firstName: "Sarah",
  country: "Canada",
  occupation: "Technical Writer",
  hobbies: ["photography", "birdwatching", "baseball"],
};

const skills = ["HTML", "CSS", "JavaScript", "React", "Astro", "Writing Docs"];
---
```

```jsx
<p>Here are a few facts about me:</p>
<ul>
  <li>My name is {identity.firstName}.</li>
  <li>I live in {identity.country} and I work as a {identity.occupation}.</li>
  {identity.hobbies.length >= 2 &&
    <li>Two of my hobbies are: {identity.hobbies[0]} and {identity.hobbies[1]}</li>
  }
</ul>
<p>My skills are:</p>
<ul>
  {skills.map((skill) => <li>{skill}</li>)}
</ul>
```

`.astro` 파일의 어느 섹션에서나 모든 최신 JavaScript **논리 연산자**, **표현식**, **함수**를 사용할 수 있습니다. 그러나 HTML 템플릿 본문에는 중괄호만 필요합니다.

```jsx
const happy = true;
const finished = false;
const goal = 3;
```

### 조건부 렌더링
```jsx
{happy && <p>I am happy to be learning Astro!</p>}

{finished && <p>I finished this tutorial!</p>}

{goal === 3 ? <p>My goal is to finish in 3 days.</p> : <p>My goal is not 3 days.</p>}
```

### about 페이지 스타일 지정
`about.astro`
```jsx
<style>
  h1 {
    color: purple;
    font-size: 4rem;
  }
</style>
```

`<li>`
```jsx
<ul>
  {skills.map((skill) => <li class="skill">{skill}</li>)}
</ul>
```

```jsx
<style>
  .skill {
    color: green;
    font-weight: bold;
  }
</style>
```

### CSS 변수 사용
```jsx
---
// 변수 추가
const skillColor = "crimson";
const fontWeight = "bold";
const textCase = "uppercase";
---

// 변수 사용
<style define:vars={{skillColor, fontWeight, textCase}}>
  .skill {
    color: var(--skillColor);
    font-weight: var(--fontWeight);
    text-transform: var(--textCase);
  }
</style>

```

### 전역 스타일 추가
`stc/styles/global.css`

작성
```css
html {
  background-color: #f1f5f9;
  font-family: sans-serif;
}

body {
  margin: 0 auto;
  width: 100%;
  max-width: 80ch;
  padding: 1rem;
  line-height: 1.5;
}

* {
  box-sizing: border-box;
}

h1 {
  margin: 1rem 0;
  font-size: 2.5rem;
}
```

적용
```jsx
---
import '../styles/global.css';
---
```

### Astro 컴포넌트 생성
- Navigation
- Footer
- Social
- Menu

재사용 가능한 Nav 컴포넌트 만들기
`src/components/`

작성: `Navigation.astro`
```jsx
---
---
<a href="/">Home</a>
<a href="/about/">About</a>
<a href="/blog/">Blog</a>
```

적용: `index.astro`
```jsx
---
import Navigation from '../components/Navigation.astro';
---
<Navigation />
```

코드를 재구성하지만 페이지가 브라우저에 표시되는 방식이 변경되지 않는 것을 **리팩터링**이라고 합니다. 페이지 HTML의 일부를 컴포넌트로 대체하며 이 단계에서 여러 번 **리팩터링**하게 됩니다.

- [i] Astro의 페이지는 `src/pages/*.astro`만? YES
- [x] 왜 `src/posts/*.md`도 인식하는거지? 아 `/pages/` 안에 있었구나

### Footer 만들기
`src/components/Footer.astro`
```jsx
// ---
const platform = "github";
const username = "withastro";
// ---

<footer>
  <p>Learn more about my projects on <a href={`https://www.${platform}.com/${username}`}>{platform}</a>!</p>
</footer>
```

### Props 받아보기
작성: `src/components/Social.astro`
```jsx
// ---
const { platform, username } = Astro.props;
// ---
<a href={`https://www.${platform}.com/${username}`}>{platform}</a>
```

불러오기: `src/components/Footer.astro`
```jsx
// ---
import Social from './Social.astro';
// --- 

<footer>
  <p>Learn more about my projects on <a href={`https://www.${platform}.com/${username}`}>{platform}</a>!</p>
  <Social platform="twitter" username="astrodotbuild" />
  <Social platform="github" username="withastro" />
  <Social platform="youtube" username="astrodotbuild" />
</footer>
```

컴포넌트 스타일 지정
`Social.astro`
```jsx
<a href={`https://www.${platform}.com/${username}`}>{platform}</a>

<style>
  a {
    padding: 0.5rem 1rem;
    color: white;
    background-color: #4c1d95;
    text-decoration: none;
  }
</style>
```

레이아웃 개선
`Footer.astro`
```jsx
<style>
  footer {
    display: flex;
    gap: 1rem;
    margin-top: 2rem;
  }
</style>

<footer>
  <Social platform="twitter" username="astrodotbuild" />
  <Social platform="github" username="withastro" />
  <Social platform="youtube" username="astrodotbuild" />
</footer>
```


헤더 만들어보기
`src/components/Header.astro`
```jsx
---
import Navigation from './Navigation.astro'
---
<header>
  <nav>
    <Navigation />
  </nav>
</header>
```

반응형 스타일 추가
`Navigation.astro`
```jsx
---
---
<div id="main-menu" class="nav-links">
  <a href="/">Home</a>
  <a href="/about/">About</a>
  <a href="/blog/">Blog</a>
</div>
```

반응형은 global.css에 
`@media` 적용
`global.css`
```css
/* nav 스타일 */

.nav-links {
  width: 100%;
  display: none;
  margin: 0;
}

.nav-links a {
  display: block;
  text-align: center;
  padding: 10px 0;
  text-decoration: none;
  font-size: 1.2rem;
  font-weight: bold;
  text-transform: uppercase;
  color: #0d0950;
}

.nav-links a:hover,
.nav-links a:focus {
  background-color: #ff9776;
}

@media screen and (min-width: 636px) {
  .nav-links {
    margin-left: 5em;
    display: block;
    position: static;
    width: auto;
    background: none;
  }

  .nav-links a {
    display: inline-block;
    padding: 15px 20px;
  }
}
```

## 첫 번째 스크립트를 브라우저로 보내기
- 메뉴 컴포넌트 만들기
- 탐색 메뉴 토글 버튼 `<script>`
- JavaScript를 `.js`로 이동

### 메뉴 컴포넌트 구축
작성: `src/components/Menu.astro`
```
---
---
<button aria-expanded="false" aria-controls="main-menu" class="menu">
  Menu
</button>
```

배치: `src/components/Header.astro`
```
---
import Menu from './Menu.astro';
---
<header>
  <nav>
    <Menu />
    <Navigation />
  </nav>
</header>
```

글로벌 스타일 추가
```css
.menu {
  background-color: #0d0950;
  border: none;
  color: #fff;
  font-size: 1.2rem;
  font-weight: bold;
  padding: 5px 10px;
}

/* ... */

:has(.menu[aria-expanded="true"]) .nav-links {
  display: unset;
}

@media screen and (min-width: 638px) {
  .menu {
    display: none;
  }
}
```

스크립트 태그 작성
`index.astro`

```html
<body>
</body>
<script>
  const menu = document.querySelector('.menu');
  
  menu?.addEventListener('click', () => {
    const isExpanded = menu.getAttribute('aria-expanded') === 'true';
    menu.setAttribute('aria-expanded', `${!isExpanded}`)
  });
</script>
```

리팩터링: `.js` 파일 가져오기
`src/scripts/menu.js`

```js
const menu = document.querySelector('.menu');

menu?.addEventListener('click', () => {
  const isExpanded = menu.getAttribute('aria-expanded') === 'true';
  menu.setAttribute('aria-expanded', `${!isExpanded}`);
});
```

```
<body>
</body>
<script>
  import "../scripts/menu.js";
</script>
```

## 레이아웃
### 페이지 레이아웃
- **Refactor** common elements into a page layout
- Use an Astro `<slot />` element
    - to place page contents within a layout
- Pass page-specific values as props to its layout

`src/layouts/BaseLayout.astro`
⇐ `index.astro`

use `<slot />`

`<BaseLayout pageTitle={pageTitle}`

to receive a page title
`const { pageTitle } = Astro.props;`

### 마크다운 레이아웃
- Create a blog post for `.md` files
- Pass YAML **frontmatter values** as props 

`src/layouts/MarkdownPostLayout.astro`

```js
const { frontmatter } = Astro.props;
```

```jsx
<meta charset="utf-8" />
<h1>{frontmatter.title}</h1>
<p>Author: {fontmatter.author}</p>
<p>Published: {fontmatter.author}</p>
<slot />
```

`src/pages/posts/post-1.md`

```
---
layout: ../../layouts/MarkdownPostLayout.astro
---
```

Nesting 하기
```jsx
<BaseLayout pageTitle={frontmatter.title}>
  <p>Published on: {frontmatter.pubDate.toString().slice(0,10)}</p>
  <p><em>{frontmatter.description}</em></p>
  <p>Written by {frontmatter.author}</p>
  <img src={frontmatter.image.url} width="300" alt={frontmatter.image.alt} />
  <slot />
</BaseLayout>
```

## Astro API
You'll supercharge your blog with:
- index page
- tag pages
- RSS feed

- `import.meta.glob()` to access data from files in your project
- `getStaticPaths()` to create multiple pages (routes) at once
- The Astro RSS package to create an RSS feed

### Display a list of posts
`blog.astro`

```jsx
const allPosts = Object.values(import.meta.glob('./posts/*.md', { eager: true }));
```

```tsx
{allposts.map((post: any) => <l1><a href={post.url}>{post.frontmatter.title}</a></li>)}
```

### Generate tag pages
- Create a page to generate multiple pages
- Specify which page routes to build
    - and pass each page its own props

create entire sets of pages dynamically
export `getStaticPaths()` at `.astro`

`src/pages/tags/[tag].astro`

```jsx
---
import BaseLayout from '../../layouts/BaseLayout.astro';

export async function getStaticPaths() {
  return [
    { params: { tag: "astro" } },
    { params: { tag: "successes" } },
    { params: { tag: "community" } },
    { params: { tag: "blogging" } },
    { params: { tag: "setbacks" } },
    { params: { tag: "learning in public" } },
  ];
}

const { tag } = Astro.params;
---
<BaseLayout pageTitle={tag}>
  <p>Posts tagged with {tag}</p>
  <ul>
  </ul>
</BaseLayout>
```

`getStaticPaths()`
same template

### Use props in dynamic routes

```jsx
export async function getStaticPaths() {
  const allPosts = Object.values(import.meta.glob('../posts/*.md', { eager: true });
  return [
    { params: { tag: "astro" }, props: {posts: allPosts}},
  ];
}

const { tag } = Astro.params;
const { posts } = Astro.props;
const filteredPosts = posts.filter((post: any) => post.frontmatter.tags?.includes(tag))
```

```
{filteredPosts.map((post: any) => <BlogPost url={post.url} title={})}
```

Takeaway
- If you need information to construct the page routes, write it **inside**`getStaticPaths()`.
- To receive information in the HTML template of a page route, write it **outside**`getStaticPaths()`.






















