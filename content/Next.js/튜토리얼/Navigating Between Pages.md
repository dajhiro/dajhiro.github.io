Let's add some Links to allow users to navigate between the dashboard routes.
### Previous
[[Creating Layouts and Pages]]

### In this chapter
- How to use the `next/link` **component**
- How to show an active link with the **`usePathname()`** hook
- How navigation works in Next.js

### Why optimize navigation?
`<a>`
There's a full page refresh on each page navigation!

### The *Link* component
`<Link />` Component to link between pages in a application.
it allows you to do [client-side navigation](https://nextjs.org/docs/app/building-your-application/routing/linking-and-navigating#how-routing-and-navigation-works) with JavaScript.

`app/ui/dashboard/nav-links.tsx`

```tsx
import {
  UserGroupIcon,
  HomeIcon,
  DocumentDuplicateIcon,
} from '@heroicons/react/24/outline';
import Link from 'next/link';

const links = [
  { name: 'Home', href: '/dashboard', icon: HomeIcon },
  {
    name: 'Invoices',
    href: '/dashboard/invoices',
    icon: DocumentDuplicateIcon,
  },
  { name: 'Customers', href: '/dashboard/customers', icon: UserGroupIcon },
]

export default function NavLinks() {
  return (
    <>
      {links.map((link) => {
        const LinkIcon = link.icon;
        return (
          <Link
            key={link.name}
            href={link.href}
            className="flex h-[48px] grow items-center justify-center gap-2 rounded-md bg-gray-50 p-3 text-sm font-medium hover:text-blue-600 md:flex-none md:justify-start md:p-2 md:px-3"
          >
            <LinkIcon className="w-6" />
            <p className="hidden md:block">{link.name}</p>
          </Link>
        );
      })}
    </>
  );
}

```
`<a>` ⇒ `<Link />`
now be able to navigate between the pages without seeing a full refresh.

### Automatic code-splitting and prefetching
- Next.js automatically code splits the application by route segments.
- Splitting code by routes means that pages become isolated.
- `<Link>` automatically **prefetches** the code for the linked route in the background.

### Pattern: Showing active links
`usePathname()`: using client path

`app/ui/dashboard/nav-links.tsx`

```tsx
'use client';

import { usePathname } from 'next/navigation'
```

```tsx
export default function NavLinks() {
  const pathname = usePathname();
}
```

```tsx
// ...
import clsx from 'clsx';

export default function NavLinks() {
  const pathname = usePathname();
  
  return (
    <>
      {links.map((link) => {
        const LinkIcon = link.icon;
        return (
          <Link
            key={link.name}
            href={link.href}
            className={clsx(
              'flex h-[48px] grow items-center justify-center gap-2 rounded-md bg-gray-50 p-3 text-sm font-medium hover:bg-sky-100 hover:text-blue-600 md:flex=none md:justify-start md:p-2 md:px-3',
              {
                'bg-sky-100 text-blue-600': pathname === link.href,
              },
            )}
          >
            <LinkIcon className="w-6" />
            <p className="hidden md:block">{link.name}</p>
          </Link>
        );
      })}
    </>
  );
}
```

### Next
[[Setting Up Your Database]]














