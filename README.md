# Sass Utilities

Sass utility toolkit for managing

- **typography**
- **media queries** 

in modern front-end projects.

## ✨ Features

### 📐 **Typography** 

with custom font system, responsive scaling, and utility classes.

- **Font Variables** ([`_variables.scss`](assets/scss/typography/_variables.scss)).
- **Custom Properties**: [`_root.scss`](assets/scss/typography/_root.scss).
- **Font Faces**: ([`_fonts.scss`](assets/scss/typography/_fonts.scss)).
- **Headings**: `h1`, `h2`, `h3` ([`_headings.scss`](assets/scss/typography/_headings.scss)).
- **Text Utilities**: `.txt--sm`, `.txt--lg`, etc. ([`_text.scss`](assets/scss/typography/_text.scss)).
- **Paragraphs**: ([`_paragraph.scss`](assets/scss/typography/_paragraph.scss)).
 

### 📱 **Media Queries** 

with named breakpoints and simple mixin usage

- **Breakpoints**: `sm`, `md`, `lg`, etc. ([`_breakpoints.scss`](assets/scss/mediaquery/_breakpoints.scss)).
- **Mixin Media Query**: `min-width`, `max-width` ([`_media-query.scss`](assets/scss/mediaquery/_media-query.scss)).

## 📁 Project Structure
```
/assets
├── /scss
│   ├── layout/
│   │   ├── _index.scss
│   │   └── _root.scss // Root CSS variables (e.g., color palette)
│   │
│   ├── mediaquery/
│   │   ├── _breakpoints.scss // Breakpoint definitions
│   │   └── _media-query.scss // Mixin for media queries
│   │
│   ├── typography/
│   │   ├── _fonts.scss // Font imports
│   │   ├── _headings.scss // h1–h6 styles
│   │   ├── _helpers.scss // [TODO]
│   │   ├── _index.scss // Entry point for typography partials
│   │   ├── _links.scss // [TODO]
│   │   ├── _lists.scss // [TODO]
│   │   ├── _paragraph.scss // Base <p> styles
│   │   ├── _root.scss // CSS variables from typography maps
│   │   ├── _text.scss // Utility classes like .txt--sm, .txt--lg
│   │   └── _variables.scss // Maps for font sizes, weights, line heights
│   │
│   ├── _functions.scss // Utility functions (e.g., px to em)
│   └── main.scss // Master file to import all partials
│
└── /public
    └── fonts/
        └── kanchenjunga/
            └── *.ttf
```

## 🧠 Usage

- Import `main.scss` in project:
  ```scss
  @use './assets/scss/main.scss' as *;
  ```

- Nuxt project (in `nuxt.config.ts`):
  ```ts
  export default defineNuxtConfig({
    compatibilityDate: '2024-11-01',
    devtools: { enabled: true },
    css: ['@/assets/scss/main.scss'],
    vite: {
      css: {
        preprocessorOptions: {
          scss: {
            additionalData: `@use "@/assets/scss/mediaquery/media-query" as *;`
          }
        }
      }
    }
  })
  ```

### Media Query Example

```scss
@include media-query(md) {
  .example {
    color: 1.25rem;
  }
}
// @media only screen and (min-width: 48em)

@include media-query(md, max) {
  .example {
    color: 1.25rem;
  }
}
// @media only screen and (max-width: 48em)
```

### Typography utility Example

```html
<h1>Heading 1</h1>
<p>paragraph</p>
<div class="text text-sm">some text</div>
```

## 🛠️ TODO

### Typography
- helpers.scss — generic helpers (e.g., visually-hidden, truncate)

- links.scss — default styles and variants

- lists.scss — normalize and style lists

### Media Query
- Support for "between" breakpoints (e.g., md → lg)