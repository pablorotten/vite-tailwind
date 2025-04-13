# Vite tailwind

## Installation

Install vite and tailwind

```shell
npm create vite@latest vite-tailwind
cd vite-tailwind
volta pin node@20
volta pin npm@bundled
npm install
npm install tailwindcss @tailwindcss/vite
```

Create a vite.config.ts file and add tailwindcss to the plugins array:

```ts
import { defineConfig } from 'vite'
import tailwindcss from '@tailwindcss/vite'
export default defineConfig({
  plugins: [
    tailwindcss(),
  ],
})
```

Add tailwindcss to the css file:

```css
@import "tailwindcss";
```

Run the app

```shell
npm run dev
```

### Hints

- Mark `node_modules` as **excluded** in IntelliJ

## Deploy in github pages
