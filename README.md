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

Using [gh-pages](https://github.com/tschaub/gh-pages), we will create a parallel branch with the files that Github pages need

### 1. Update vite.config.js
   
Set base to the repo name: `vite-tailwind`
```ts
import { defineConfig } from 'vite'
import tailwindcss from '@tailwindcss/vite'
export default defineConfig({
  ...,
  base: "/vite-tailwind/"
})
```

### 2. Install gh-pages
```sh
npm install gh-pages --save-dev
```

### 3. Update package.json
Update package.json with the following predeploy, deploy scripts and the homepage

```json
{
  "name": "vite-tailwind",
  ...
  "homepage": "https://pablorotten.github.io/vite-tailwind/",
  "scripts": {
    "predeploy" : "npm run build",
    "deploy" : "gh-pages -d dist",
    ...
  },
  ...
}
```
### 4. Run Deploy
Create the branch `gh-pages` with the github page
```sh
npm run deploy
```

### 5. Setup github pages in Github

* Go to https://github.com/pablorotten/vite-tailwind/settings/pages
* In Build and deployment select the branch `gh-pages` and save
* Go to https://pablorotten.github.io/vite-tailwind/

### 6. Update the page
Everytime you need to update the page, just
```sh
npm run deploy
```
