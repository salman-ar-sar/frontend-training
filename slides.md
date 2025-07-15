---
# You can also start simply with 'default'
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: Frontend Foundations
info: |
  ## Fundamentals of Frontend
  Freshers Training Program

# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
layout: center
slideNumber: true
---

# Foundation

### Fundamentals of Frontend

#### HTML · CSS · JavaScript

##### Freshers Training Program

---

## 🧭 Welcome & Agenda

- Introductions & icebreaker: share your favorite webpage  
- What we’ll cover:  
  1. Origins & purposes of HTML/CSS/JS  
  2. Core syntax and structure  
  3. Interactive demo + best practices  
  4. Next steps & resources

---

## Why HTML Was Created

- Invented by Tim Berners‑Lee at CERN (~1991)  
- Designed to share linked documents across institutions  
- Hypertext + markup made publishing simple and universal

---

## 🎨 HTML Basics + Semantics

- Tags: `<head>`, `<body>`, headings, lists, images, links  
- Semantic HTML = accessibility + SEO  
- **Quiz**: What’s the correct tag for a navigation menu?

---

## Understanding the DOM

- Browser builds a DOM tree from HTML  
- Enables JS to target and manipulate elements  
- **Interactive**: Inspect elements using DevTools

---

## Why CSS Was Introduced

- Proposed by Håkon Wium Lie in 1994  
- Replaced HTML hacks like `<font>` and `<blink>`  
- Separated content (HTML) from presentation (CSS)

---

## CSS Syntax & Box Model

- Selectors: element, class, ID  
- Box‑model: margin ▪ border ▪ padding ▪ content  

```css
.box {
  box-sizing: border-box;
  margin: 10px;
  padding: 8px;
  border: 1px solid #333;
}
```

---

## Layout Techniques

- Normal flow, floats (legacy), Flexbox & Grid  

```css
.container {
  display: flex;
  gap: 10px;
}
```

- **Quiz**: Which layout fits a 2‑column responsive design?

---

## Responsive Design

- Media queries, fluid images, mobile-first  

```css
@media (max-width: 600px) {
  .container { flex-direction: column; }
}
```

---

## Why JavaScript Was Created

- Created by Brendan Eich in ~May 1995  
- Added interactivity to static HTML pages  
- Designed as a “language for the masses”

---

## JavaScript Core Concepts

- Variables, data types, functions, control flow, DOM methods  

```js
const btn = document.getElementById('myBtn');
btn.addEventListener('click', () => {
  document.body.style.background =
    '#' + Math.floor(Math.random()*16777215).toString(16);
});
```

---

## Browser & Event Loop

- JS runs in engines like V8 and SpiderMonkey  
- Event loop handles asynchronous callbacks  
- Tip: use `console.log`, breakpoints & the Profiler tab

---

## Integrating HTML · CSS · JS

- Input → JS validation → CSS feedback  

```js
const input = document.querySelector('input');
input.addEventListener('input', () => {
  input.classList.toggle('error', input.value.length < 3);
});
```

---

## Best Practices 🧹

- Semantic, accessible HTML  
- DRY, modular CSS  
- JS: use `const`/`let`, avoid globals  
- Tools: ESLint, Prettier, code reviews

---

## Tools & Starter Setup

- VS Code + Prettier + ESLint  
- Chrome/Firefox DevTools  
- Use Slidev’s dev server for live editing

---

## Resources & Next Steps

- **Learn**: MDN, freeCodeCamp, JavaScript.info  
- **Build**: an interactive project (e.g., to-do list)  
- **Workshop**: live pair-coding session next week  
- **Q&A**: What are you most excited to build?
