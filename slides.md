---
theme: dracula
title: Clean Code & React Setup
subtitle: Modern Practices for Scalable Frontend Development
class: text-center
transition: slide-left
mdc: true
---

# Clean Code & React Project Setup  

### Modern Best Practices for Developers

##### Freshers Training Program

---

## 🧹 Why Clean Code Matters

- Improves readability for teams and future you
- Reduces bugs by promoting clarity
- Easier to test and maintain
- Foundation for scalable applications

<!--
Start by connecting clean code to real-world pain points: messy code causes confusion, slows teams, and increases bugs.
Explain how focusing on clarity and simplicity saves time in debugging and onboarding new developers.
-->

---

## ✨ Code Readability Principles

- Descriptive variable and function names
- Single Responsibility Principle (SRP)
- DRY (Don't Repeat Yourself)
- Consistent code formatting (linters, formatters)
- Code comments only when necessary

<!--
Discuss practical examples of good vs bad naming.
Explain how SRP leads to simpler, smaller functions and components.
Highlight why consistent formatting with tools reduces debates in code reviews.
-->

---

## 🔨 Code Reusability Principles

- Small, reusable React components
- Custom Hooks for shared logic
- Utility functions for repeated logic
- Avoid premature abstraction—refactor when needed

<!--
Explain how React encourages reusability naturally via components and hooks.
Mention balance: avoid over-engineering; extract when duplication happens 2-3 times.
-->

---

## ⚙️ Setting Up a React Project

- **Traditional way**: `create-react-app` (CRA)
- **Modern way**: Vite (faster, simpler dev experience)
- Steps:
  - Project initialization (Vite)
  - Install dependencies
  - Add linters, formatters
  - Folder structure setup
  - Setup routing, state management if needed

<!--
Quickly explain why CRA is older and heavier.
Introduce Vite: lightning-fast dev server powered by esbuild.
Walk through setup: `npm create vite@latest`, choosing React template, installing dependencies like react-router-dom, axios.
-->

---

## ⚡ What is Vite?

- Next-gen frontend tooling
- Uses **esbuild** for fast bundling and dev server
- Supports React, Vue, Svelte, etc.
- Instant hot module replacement (HMR)
- Production build uses Rollup

<!--
Emphasize Vite’s speed advantages.
Explain esbuild is written in Go, dramatically faster than webpack (JS-based).
Mention Vite handles both dev server (esbuild) and optimized production builds (Rollup).
-->
---

## What Is a Bundler?

- Bundlers generate a **dependency graph** from your entry point
- **Transform** code (JSX, TypeScript, CSS, images)
- **Optimize** with tree-shaking, minification, and asset hashing
- Popular tools: Webpack, Rollup, Parcel, esbuild

<!--
Time: 0–3 min  
Explain bundlers assemble modules into optimized browser-ready code.  
Use dev tools screenshot to show module imports vs single bundle output.
-->

---

## 🪄 Vite’s Pipeline in React SPA

- **Dev Stage**  
  - Uses esbuild + native ESM → instant server start  
  - Hot Module Replacement (HMR) for real-time updates  
- **Production Build**  
  - Uses Rollup for bundling, code splitting, tree-shaking  
  - Generates minified and hashed `dist/` assets  

- **Steps**: `npm create vite`, install deps, run `npm run dev` → `npm run build`
- Benefit: lightning-fast development and efficient production builds

---

## 🔄 Why Rollup in Production?

- esbuild is ultra-fast but less flexible  
- Rollup excels at plugin support, flexibility, and mature bundling  
- Vite combines both: esbuild for speed, Rollup for optimized output

---

## 📦 Bundlers: esbuild vs Rollup vs Webpack

| Feature           | esbuild           | Rollup           | Webpack           |
|-------------------|-------------------|------------------|-------------------|
| Speed             | ⚡ Ultra fast (Go) | Fast (JS)        | Slower (JS)       |
| Use-case          | Dev server (Vite) | Production builds | Flexible all-rounder |
| Ecosystem         | Newer, minimal plugins | Mature, optimized | Very mature, lots of plugins |

<!--
Explain bundlers handle packaging your code into optimized assets.
Highlight why modern tooling prefers esbuild for dev, Rollup for production.
Webpack is still widely used in enterprise setups but newer projects favor Vite.
-->

---

## 🧱 Folder Structure Suggestions

```shell
src/
├─ components/
├─ hooks/
├─ pages/
├─ services/
├─ styles/
└─ App.jsx
```

- **components/**: reusable UI blocks
- **hooks/**: shared logic
- **pages/**: route-specific views
- **services/**: API handling
- **styles/**: CSS/global styling

<!--
Clarify why structured folders keep code maintainable.
Encourage team consistency but flexibility depending on project complexity.
-->

---

## 🚀 React Ecosystem Variants

- **React DOM**: standard web apps
- **Next.js**: React + SSR + SSG + API routes
- **Remix**: React + enhanced data loading
- **React Native**: mobile apps (iOS/Android)
- **Expo**: easier React Native setup
- **Electron/React Desktop**: desktop apps

<!--
Clarify React itself powers many ecosystems.
Explain differences: Next.js for SEO & SSR, Remix for loaders and nested routes, React Native for mobile, Electron for desktop.
-->

---

## 🆚 Vite vs Next.js

| Feature              | Vite (React SPA)                             | Next.js (React Framework)             |
|----------------------|----------------------------------------------|----------------------------------------|
| Dev Server & HMR     | ✅ Fast, esbuild-powered                      | Webpack / TurboPack with HMR           |
| Bundler              | Rollup via `vite build`                      | Webpack / SWC / TurboPack              |
| Rendering            | CSR only                                      | SSR, SSG, ISR                          |
| Routing              | Manual (React Router)                         | File-based in `pages/`                 |
| API Endpoints        | Separate backend                             | Built-in in `pages/api`                |
| Asset Optimization   | CSS/JS minification, tree-shaking            | Image optimization, metadata, etc.     |

---

## ✨ Key Benefits of Vite

- Blazing-fast cold start and updates (esbuild + HMR)  
- Pre-bundles dependencies to speed up loading  
- Bundle-free during dev; Rollup primes production build  
- Zero-config integration with React, Vue, Svelte ecosystem  

---

## ⚙️ How Next.js Differs

- Built-in: **server-side rendering (SSR)**, **static site generation (SSG)**, API routes  
- Generation: `next dev`, then `next build`, `next start`  
- Bundling: Uses Webpack/TurboPack with SWC compiler and file-based routing  
- Great for SEO and enterprise use-cases  

---

## ✅ Recommended Use Cases

- **Vite SPA**: Ideal for fast prototyping and small/medium client-side apps  
- **Next.js**: Best for SEO-heavy sites, SSR requirements, integrated backend routes  

---

## 💡 Best Practices Summary

- Vite = esbuild (dev) + Rollup (build)
- Next.js = Webpack/TurboPack + SWC for full-stack applications
- Pick based on project needs: speed vs integrated web features

<!-- 
- **Bundlers**: Start by showing code imports; explain why browsers need compiled bundles to reduce HTTP overhead and support syntax.
- **Vite Pipeline**: Demonstrate `npm run dev` startup times vs traditional tools; show folder `dist/` contents post-build.
- **Rollup Reasoning**: Cite Vite docs—Rollup offers deeper plugin support and bundling maturity.
- **Vite vs Next.js**: Present comparison table; discuss when to choose each (SPA vs SSR-heavy).
- **Benefits**: Mention real-world speed wins—Reddit reports 30–70% faster build & HMR with Vite.
- **Next.js Difference**: Note upcoming TurboPack integration and Vercel-first stack.
- ✅ Final Slide: Emphasize decision criteria—project type, SEO, performance, server needs.
-->

---

## ✅ ESLint & Prettier Setup

- **ESLint**: code quality and rule enforcement
- **Prettier**: consistent code formatting
- Install ESLint + Prettier + plugins
- Setup `.eslintrc`, `.prettierrc`, add scripts
- Use VS Code extensions for auto-fix on save

<!--
Explain how ESLint catches bugs early and Prettier avoids style debates.
Show typical configs (plugin:react/recommended, plugin:prettier/recommended).
Demo or describe auto-fix on save.
-->

---

## 📚 Summary

- Clean code reduces bugs and improves maintainability
- Modern React uses Vite for speed and simplicity
- Understand bundlers: esbuild, Rollup, Webpack
- Follow a clear folder structure
- Choose the right React variant based on project type
- Automate consistency with ESLint & Prettier

<!--
Reinforce takeaway: setup and clean code practices are the foundation for any successful React project.
Encourage team standards for folder layout and consistent tooling.
-->

---

## 🎁 Resources & Next Steps

- [react.dev/learn](https://react.dev/learn)
- [vite.dev](https://vite.dev/)
- [eslint.org](https://eslint.org/)
- [prettier.io](https://prettier.io/)
- **Next**: practice setting up Vite + ESLint + Prettier  
- **Optional**: explore Next.js or Remix based on goals

<!--
Give learners actionable next steps.
Encourage practicing the full setup with Vite + ESLint + Prettier before exploring advanced frameworks.
-->
