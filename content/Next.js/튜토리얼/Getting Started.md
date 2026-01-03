```sh
npm install -g pnpm
```

```sh
npx create-next-app@latest nextjs-dashboard --example "https://github.com/vercel/next-learn/tree/main/dashboard/starter-example" --use-pnpm
```

```sh
cd nextjs-bashboard
```

```
$ tree -L 2 -I node_modules
>>  .
    ├── app
    │   ├── layout.tsx
    │   ├── lib
    │   ├── page.tsx
    │   ├── query
    │   ├── seed
    │   └── ui
    ├── next-env.d.ts
    ├── next.config.ts
    ├── package.json
    ├── pnpm-lock.yaml
    ├── postcss.config.js
    ├── public
    │   ├── customers
    │   ├── favicon.ico
    │   ├── hero-desktop.png
    │   ├── hero-mobile.png
    │   └── opengraph-image.png
    ├── README.md
    ├── tailwind.config.ts
    └── tsconfig.json
```

`/app`
Contains all routes, components, and logic for a application

`/app/ui`
Contains all the UI components for a application such as:
- cards
- tables
- forms

`/public`
Contains all the static assets for a application such as images

Config Files
- `next.config.ts`
- `...`

### Placeholder data
`app/lib/placeholder-data.ts`

```ts
const invoices = [
{
  customer_id: customers[0].id,
  amount: 15795,
  status: 'pending',
  date: '2022-11-14',
},
// ...
]
```

### TypeScript
TypeScript code snippets
`app/lib/definitions.ts`

```ts
export type Invoice = {
  id: string;
  customer_id: string;
  amount: number;
  date: string;
  // union type: "status" property can only be one of two strings.
  status: 'pending' | 'paid';
}
```

- [i] Recommended: Prisma, Drizzle
Next.js detects if a project use TypeScript and automatically installs necessary packages and configuration.

### Run
Install packages
```sh
pnpm i
```

Start the development server
```
pnpm dev
```

It starts server on port `3000`

### Next
[[CSS Styling]]

















