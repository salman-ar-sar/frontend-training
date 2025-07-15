---
# You can also start simply with 'default'
theme: dracula
# some information about your slides (markdown enabled)
title: React Fundamentals
info: |
  ## Intro to React
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
---

# React Fundamentals

### Building Modern UIs

##### Freshers Training Program

<!--
Time: 0–2 min  
Welcome everyone. Introduce the session focus: React fundamentals and component structure. We'll explore why React exists, its core architecture, and practical component patterns used in real-world development.
-->

---
layout: cover
---

## 🚀 Introduction to React

- Why React was created  
- What React is & how it works

<!--
Time: 2–4 min  
Introduce React by explaining its relevance in modern web development. Explain this session will cover its origins, how it works under the hood, and practical organization strategies.
-->

---

## Why React Was Created

- Built at Facebook around 2011  
- To improve maintainability & performance  
- Addressing imperative DOM pain

<!--
Time: 4–7 min  
React was created by Facebook’s Jordan Walke to solve problems in their large applications like News Feed. Traditional DOM manipulation was becoming too complex and error-prone. React introduced a declarative approach, allowing developers to describe what the UI should look like, not how to change it. It also allowed breaking down interfaces into small reusable pieces.
-->

---

## What React Is & How It Works

- Declarative, component-based UI library  
- Uses JSX syntax  
- Virtual DOM & reconciliation strategy

<!--
Time: 7–10 min  
React allows you to build user interfaces declaratively, meaning you describe the UI and React takes care of updating it efficiently. JSX blends HTML and JavaScript for clearer syntax. React creates a Virtual DOM, compares differences with previous renders, and only updates necessary parts in the real DOM—leading to better performance.
-->

---

## 🗂 Recommended Folder Layout

```shell
src/
├─ components/
├─ pages/
├─ hooks/
├─ services/
└─ App.jsx

```

- Components: reusable UI bits  
- Pages: route-level screens  
- Hooks: shared logic  
- Services: API & business logic

<!--
Time: 10–14 min  
A clean folder structure helps keep large codebases maintainable. Components are small UI elements, Pages are route-based views, Hooks encapsulate logic, and Services handle APIs or utilities. This structure scales well, avoids deeply nested files, and promotes clarity.
-->

---

## 🧩 Functional Components

```jsx
function Greeting({ name }) {
  return <h1>Hello, {name}!</h1>;
}
```

- State & effects via Hooks
- Simple, testable, reusable

<!--
Time: 14–18 min  
Since React 16.8, function components are the standard. They're simpler to write, easier to test, and support Hooks for adding state and side effects. The example shows a basic function component rendering dynamic content.
-->

---

## 🔁 Smart vs Dumb Components

- **Smart**: state, data fetching, logic
- **Dumb**: UI, props-driven, stateless
- Example: `UserListContainer` vs `UserCard`

<!--
Time: 18–22 min  
Smart components manage logic and state (e.g., data fetching), while dumb components just display UI based on props. This separation makes code modular and easier to test. Containers handle logic, presentational components handle styling and display.
-->

---

## ✅ Summary

- Component-based architecture
- JSX & Virtual DOM
- Hooks for logic
- Clear folder structure
- Smart vs dumb improves modularity

<!--
Time: 22–24 min  
Summarize main takeaways: React promotes modularity through components, improves clarity with JSX, enhances performance with Virtual DOM, and encourages scalability with smart organization. The smart/dumb pattern ensures maintainable code.
-->

---

## 📚 Next Steps

- Explore react.dev Learn & API guides
- Try the Tic-Tac-Toe tutorial
- Build a simple dashboard
- Use ESLint & Prettier
- Q\&A

<!--
Time: 24–26 min  
Encourage learners to go deeper via React.dev’s official guides. Suggest the Tic-Tac-Toe tutorial, creating a mini-project, and adding code quality tools like ESLint and Prettier. Open the floor for questions to wrap up.
-->
