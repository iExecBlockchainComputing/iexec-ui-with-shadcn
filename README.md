# iexec-ui-with-shadcn

This repo **is not** a frontend app.

This repo **is not** a starter template.

This repo is **a guide** to integrate **shadcn/ui** and give it **an iExec look** :art:

## Some assumptions

We assume you have **a working React + Vite + TypeScript project**

Otherwise you can create one with:

```
npm create vite@latest my-new-app -- --template react-swc-ts
```

We assume you have already worked with **shadcn/ui** and **Tailwind CSS**.

It currently only supports dark mode.

Bear in mind that this is **work in progress**.

## Useful resources

Tailwind -> https://tailwindcss.com/docs/utility-first

Shadcn UI -> https://ui.shadcn.com/docs

Radix Primitives -> https://www.radix-ui.com/primitives/docs/overview/getting-started

## Installation

### 1- Install `shadcn/ui`

https://ui.shadcn.com/docs/installation/vite

When running the shadcn-ui `init` command, when reaching the following question:

> Where is your global CSS file?

You can answer `src/index.css`

At the end of the process you should have a `components.json` file similar to this one:

```json
{
  "$schema": "https://ui.shadcn.com/schema.json",
  "style": "default",
  "rsc": false,
  "tsx": true,
  "tailwind": {
    "config": "tailwind.config.js",
    "css": "src/index.css",
    "baseColor": "slate",
    "cssVariables": true
  },
  "aliases": {
    "components": "@/components",
    "utils": "@/utils"
  }
}
```

### 2- Copy `index.css` file

In this file we define all the design tokens related to iExec design (mainly colors).

You can replace the generated shadcn/ui `index.css` file with the one provided in this repository.

### 3- Copy `tailwind.config.js` file

In this file we use all the design tokens to extend Tailwind utility classes.

It is a starting point, you'll probably need to add more classes to fit your needs.

### 4- Install fonts

Base font: _Mulish_

Title font: _Anybody_ with spacial `fontVariationSettings` (See `tailwind.config.js`)

NavBar app title font: _Space Mono_

```sh
npm i @fontsource/mulish \
  @fontsource-variable/anybody \
  @fontsource/space-mono
```

Import them where you need them.

For example in `src/main.tsx`:

```javascript
import '@fontsource/mulish';
```

### 5- Icons come from 'react-feather'

```sh
npm i react-feather
```

-----

## Available components (WIP)

### Button

```tsx
import { ArrowUpRight, Loader } from 'react-feather';
import { Button } from '@/components/ui/button.tsx';

function App() {
  return (
    <>
      {/* Primary button */}
      <Button>Primary button</Button>

      {/* Secondary small button */}
      <Button variant="secondary" size="sm">
        Secondary small button
      </Button>

      {/* Button with append icon */}
      <Button>
        Let's go
        <ArrowUpRight size="20" className="-mr-1 ml-1.5" />
      </Button>

      {/* Loading button */}
      <Button size="sm">
        <Loader size="16" className="mr-2 animate-spin-slow" />
        <span>Submit my changes</span>
      </Button>
    </>
  );
}
```

<img src="Buttons.png" width="350">

### Input

🏗️ TODO

### NavBar

🏗️ TODO

### Switch

🏗️ TODO

### Toast

🏗️ TODO
