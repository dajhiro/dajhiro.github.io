### Previous
[[CSS Styling]]

### In this chaper...
- How to add custom fonts with `next/font`.
- How to add images with `next/image`.
- How fonts and images are optimized in Next.js.

### Why optimize fonts?
Cumulative Layout Shift is
a **metric** used by Google to evaluate the performance and user experience of a website.

initially renders text in a fallback or system font
and then swaps it out for a **custom font** once it loaded.

Next.js automatically **optimizes** fonts
when you use **`next/font` module**

### Adding a primary font

Define: `app/ui/fonts.ts`

```ts
import { Inter } from 'next/font/google';

export const inter = Inter({ subsets: ['latin'] });
```

Call: `app/layout.tsx`

```tsx
import { inter } from '@/app/ui/fonts';

export default function RootLayout({
  children,
}: {
  children: React.ReactNode;
}) {
  return (
    <html lang="en">
      <body className={`${inter.className} antialiased`}>{children}</body>
    </html>
  );
}
```

### Practice: Adding a secondary font
Define: `app/ui/fonts.ts`

```ts
import { Lusitana } from 'next/font/google';

export const lusitana = Lusitana({
  weight: ['400', '700'],
  subsets: ['latin'],
});
```

Call: `app/pages.tsx`

```tsx
import { lusitana } from '@/app/ui/fonts';

export default function Page() {
  return (
    <p
      className={`${lusitana.className} ...`}
    >
      ...
    </p>
  );
}
```

### Why optimize images?
`public` folder

```html
<img
  src="/hero.png"
  alt="Screenshots of the dashboard project showing desktop version"
/>
```

However, this means you have to **manually**:
- Ensure your image is **responsive on** different screen sizes.
- **Specify image sizes** for different devices.
- Prevent layout shift as the images load.
- Lazy load images that are outside the user's viewport.

### The *Image* Component
The `<Image>` Component is an extension of the HTML `<img>` tag
comes with automatic image optimization, such as:
- **Preventing layout shift** automatically when images are loading.
- Resizing images to **avoid shipping large images** to devices with a smaller viewport.
- **Lazy loading** images by default (images load as they enter the viewport).
- Serving images in modern formats, like [WebP](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types#webp) and [AVIF](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types#avif_image), when the browser supports it.

### Adding the desktop hero image
sources:
- `public/hero-desktop.png`
- `public/hero-mobile.png`

`app/page.tsx`

```tsx
import Image from 'next/image';

export default function Page() {
  return (
    <Image
      src="/hero-desktop.png"
      width={1000}
      height={760}
      className="hidden md:block"
      alt="Screenshots of the dashboard project showing desktop version"
    />
  );
}
```

### Next
[[Creating Layouts and Pages]]












