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

- Created at Facebook (2011) by Jordan Walke
- Solved scaling issues in dynamic interfaces like News Feed
- Made UI updates more predictable and performant
- Shifted from imperative (jQuery) to declarative programming
- Inspired modern UI frameworks like Vue and Svelte

<!--
Time: 4–7 min  
React was created by Facebook’s Jordan Walke to solve problems in their large applications like News Feed. Traditional DOM manipulation was becoming too complex and error-prone. React introduced a declarative approach, allowing developers to describe what the UI should look like, not how to change it. It also allowed breaking down interfaces into small reusable pieces.
Explain the struggles developers had with UI manipulation using jQuery — leading to tangled code known as "spaghetti code".
React introduced the Virtual DOM to optimize DOM updates, solving key performance bottlenecks.
Mention how React popularized the component-based architecture which many modern frameworks adopted later.
-->

---

## What React Is & How It Works

- Component-based, declarative UI library
- JSX combines HTML and JavaScript
- Virtual DOM efficiently updates the real DOM
- One-way data flow ensures predictable UI state
- Ecosystem includes React Router, Redux, TanStack Query

<!--
Time: 7–10 min  
React allows you to build user interfaces declaratively, meaning you describe the UI and React takes care of updating it efficiently. JSX blends HTML and JavaScript for clearer syntax. React creates a Virtual DOM, compares differences with previous renders, and only updates necessary parts in the real DOM—leading to better performance.
Reconciliation is the process of comparing the Virtual DOM with the real DOM to determine what needs to change.
Clarify React is a library, not a full framework — it handles UI concerns, leaving routing and data fetching to external libraries.
JSX simplifies writing UI logic by embedding it directly in JavaScript, reducing mental overhead.
Explain the Virtual DOM diffing algorithm improves performance by minimizing direct DOM manipulations.
Highlight unidirectional data flow improves maintainability, makes debugging easier compared to two-way binding.
-->

---

## 🗂 Recommended Folder Layout

- Keeps code modular and maintainable
- Easier onboarding for new team members
- Promotes separation of concerns
- Scales well in growing projects
- Possible structure:

```shell
src/
├─ components/  # Reusable UI components
├─ pages/       # Route-based screens
├─ hooks/       # Custom logic reuse
├─ services/    # API/data logic
├─ styles/      # Global styles
├─ utils/       # Utility functions
└─ App.jsx      # Root component
```

<!--
Time: 10–14 min  
A clean folder structure helps keep large codebases maintainable. Components are small UI elements, Pages are route-based views, Hooks encapsulate logic, and Services handle APIs or utilities. This structure scales well, avoids deeply nested files, and promotes clarity.
Walk through the importance of organizing code for scalability.
Discuss how components handle UI pieces, pages map to routes, hooks abstract reusable logic (e.g., fetching), and services keep API logic separate from UI.
Optional: explain when to add folders like contexts or utils as projects grow.
-->

---

## 🧩 Functional Components

```jsx
function Greeting({ name }) {
  return <h1>Hello, {name}!</h1>;
}
```

- Simple functions that return UI markup
- Support Hooks like `useState`, `useEffect`
- Simpler syntax compared to class components
- Easier to read, test, and maintain
- Encourage modular, reusable components

<!--
Time: 14–18 min  
Since React 16.8, function components are the standard. They're simpler to write, easier to test, and support Hooks for adding state and side effects. The example shows a basic function component rendering dynamic content.
Show why functional components became the preferred approach after React 16.8.
Demonstrate their ease of use, how hooks allow adding stateful logic, and why they promote code reuse.
Mention class components are now legacy but useful to understand when working on older codebases.
-->

---

## 🔁 Smart vs Dumb Components

- **Smart (Container):** handles data, API calls, and state
- **Dumb (Presentational):** renders UI based on props only
- Keeps logic separate from UI rendering
- Improves component reusability
- Simplifies testing by decoupling business logic

- Example: `UserListContainer` vs `UserCard`

<!--
Time: 18–22 min  
Smart components manage logic and state (e.g., data fetching), while dumb components just display UI based on props. This separation makes code modular and easier to test. Containers handle logic, presentational components handle styling and display.
Define smart components as those with logic responsibilities (fetching data, handling state), and dumb components as purely UI-focused.
This division improves maintainability, supports single responsibility principle, and enhances testability.
Mention you can convert dumb components into smart ones later as requirements change.
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
Reinforce main takeaways: React simplifies UI development, promotes clean componentization, and encourages scaling best practices.
Advise applying these patterns even in small projects to build good habits.
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
