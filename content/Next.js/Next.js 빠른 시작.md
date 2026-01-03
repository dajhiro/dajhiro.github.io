## [[Next.js]] Start
빠른 시작
```sh
npx create-next-app@latest my-app --yes
cd my-app
npm run dev
```

수동 시작
```sh
npm i next@latest react@latest react-dom@latest
```

package.json 스크립트 추가
```json
"scripts": {
  "dev": "next dev",
  "build": "next build",
  "start": "next start",
  "lint": "eslint",
  "lint:fix": "eslint --fix"
}
```
- `next dev`: Turbopack(기본 번들러)을 사용하여 개발 서버를 시작합니다.
- `next build`: 생산을 위한 응용 프로그램을 빌드합니다.
- `next start`: 프로덕션 서버를 시작합니다.
- `eslint`: ESLint를 실행합니다.

### app 폴더 구성
레이아웃 구성
```tsx
// layout.tsx
export default function RootLayout({
  children,
}: {
  children: React.ReactNode
}) {
  return (
    <html lang="en">
      <body>{children}</body>
    </html>
  );
}

```

홈페이지 구성
```tsx
export default function Page() {
  return <h1>Hello, Next.js!</h1>
}
```

### 서버 시작
```sh
npm run dev
```
