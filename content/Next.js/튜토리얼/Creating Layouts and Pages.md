Create more routes with **layouts** and **pages**.
### Previous
[[Optimizing Fonts and Images]]

### In this chapter
- Create the `dashboard` routes using file-system routing
- Understand the role of folders and files when creating new route segments
- Create a nested layout that can be shared between multiple dashboard pages
- Understand what
    - **colocation**
    - **partial rendering**
    - **the root layout** are

### Nested routing
by **Folder**
Each folder represents a **route segment** that maps to a **URL segment**.

Create seperate UIs for each route using `layout.tsx` and `page.tsx` files.
`page.tsx` is a special Next.js file that exports a React component,
and it's required for the route to be accessible.

`app/dashboard`

```tsx
export default function Page() {
  return <p>Dashboard Page</p> 
}
```

### Create the dashboard layout

```tsx
import SideNav from '@/app/ui/dashboard/sidenav';

export default function Layout({ children }: { children: React.ReactNode }) {
  return (
    <div className="flex h-screen flex-col md:flex-row md:overflow-hidden">
      <div className="w-full flex-none md:w-64">
        <SideNav />
      </div>
      <div className="grow p-6 md:overflow-y-auto md:p-12">{children}</div>
    </div>
  );
}
```

the pages inside `/dashboard` will automatically be nested inside a `<Layout />` like so:
![[../../../Pasted image 20251225153928.png]]

[Partial rendering](https://nextjs.org/docs/app/building-your-application/routing/linking-and-navigating#4-partial-rendering): preserves client-side React state in the layout when transitioning between pages.

`app/layout.tsx` is a **Root layout**

### Next
[[Navigating Between Pages]]





















