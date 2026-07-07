[[Astro Start]]
[[Astro Project]]
- Astro Configuration
    - [[Astro 구성 -- AI 도구]]
    - [[Astro 구성 -- 환경변수 사용]]
    - [[Astro 구성 -- TypeScript]]

## [[Astro]] -- *hybrid system*
How to extend CSS's limit along using Astro?
### CSS preprocessors -- Sass, Less
PostCSS pipeline

### *TailwindCSS* solves many inherent CSS limitations:
- no naming required
- perfect responsive system
- consistent spacing, sizing, typography
- dark mode toggling
 - design tokens baked-in
 - plugin ecosystem

### *SASS* for variable, loops, maxins
loop, create functions, mixin

### *PostCSS* for next-level features
You can add plugins to unlock features CSS doesn't have:
nested rules
custom media queries
autoprefixer
CSS variables transformer
utility generators

### Use *Design Tokens* (CSS variables) globally
```css
:root {
  --space: 1rem;
  --radius: 8px;
  --brand-color: #ff4757;
}
```
Then all components inherit the same "design language"
This removes CSS's limitation of being too free and inconsistent.























