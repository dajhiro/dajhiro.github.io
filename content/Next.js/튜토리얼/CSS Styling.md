### Previous
[[Getting Started]]

### In this chapter...
- How to add a global CSS file to your application.
- Two different ways of styling: Tailwind and CSS modules.
- How to conditionally add class names with the `clsx` utility package.

`/app/ui`
### Global styles
top-level component. this is the root layout.
`global.css`

Add: `/app/layout.tsx`

```tsx
import '@/app/ui/global.css';

export default function RootLayout({
  children,
}: {
  children: React.ReactNode;
}) {
  return (
    <html lang="en">
      <body>{children}</body>
    </html>
  );
}
```

### Tailwind
CSS framework
allowing to quickly write utility classes directly in the React code

```tsx
<h1 className="text-blue-500">I'm blue!</h1>
```

`/app/page.tsx`

```tsx
import AcmeLogo from '@/app/ui/acme-logo';
import { ArrowRightIcon } from '@heroicons/react/24/outline';
import Link from 'next/link';

export default function Page() {
  return (
    <main className="flex min-h-screen flex-col p-6">
      <div className="flex h-20 shrink-0 items-end rounded-lg bg-blue-500 p-4 md:h-52">
  )
}
```

Add a black triangle
```tsx
<div
  className="relative w-0 h-0 border-l-[15px] border-r-[15px] border-b-[26px] border-l-transparent border-r-transparent border-b-black"
/>
```

### CSS Modules
`app/ui/home.module.css`

```css
.shape {
  height: 0;
  width: 0;
  border-bottom: 30px solid black;
  border-left: 20px solid transparent;
  border-right: 20px solid transparent;
}
```

`app/page.tsx`

```tsx
import styles from '@/app/ui/home.module.css';

export default function Page() {
  return (
    <main>
      <div className={styles.shape} />
    </main>
  )
}
```

### Using *clsx* library to toggle class names
style element conditionally based on **state** or some other condition
here's the basic usage:
- Suppose that you want to create an `InvoiceStatus` component which accepts `status`. The status can be `'pending'` or `'paid'`.
- If it's `'paid'`, you want the color to be green. If it's `'pending'`, you want the color to be gray.

`app/ui/invoices/status.tsx`

```tsx
import clsx from 'clsx';

export default function InvoiceStatus({ status }: { status: string }) {
  return (
    <span
      className={clsx(
        'inline-flex items-center rounded-full px-2 py-1 text-sm',
        {
          'bg-gray-100 text-gray-5000': status === 'pending',
          'bg-green-500 text-white': status === 'paid',
        }
      )}
    >
  );
}

```

### Other styling solutions
with: 
- Sass which allows you to import `.css` and `.scss` files..
- CSS-in-JS libraries such as styled-jsx.

### Next
[[Optimizing Fonts and Images]]















