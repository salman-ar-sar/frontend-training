---
theme: dracula
title: State Management & Forms
subtitle: React useState, Controlled Forms & Validation
class: text-center
transition: slide-left
mdc: true
---

# API Integration, Error Handling & Testing

### Building Robust and Testable React Apps

##### Freshers Training Program

---

## 🧩 Axios / Fetch Abstraction

- Use `axios.create()` or wrapper functions for common config  
- `fetch` vs `axios`: native vs abstraction & interceptors  
- Keep API logic outside components in `services/` or custom hooks  
- Enables centralized error handling, retries, and logging

<!--
Explain why centralized API setup prevents duplication and improves consistency.
**Time**: 0–3 min  
Explain purpose of centralizing API logic (services/hooks) for consistency and ease of maintenance. Show an axios instance with auth header setup and error interceptors.
-->

---

## 🔄 fetch vs Axios: Which One & Why?

- **fetch** is a native, lightweight browser API — zero dependencies, modern syntax, small bundle size
- **Axios** is a robust, promise-based library supporting:
  - automatic JSON parsing (`response.data`)
  - auto-reject on HTTP errors (non-2xx)
  - request/response interceptors, timeouts, progress tracking, cancellations
  - backward browser support (IE11 via XHR fallback)

- **fetch** gives low-level control — but requires manual `.json()`, error checking (`response.ok`), and polyfills for older browsers 

---

- **fetch** is minimal and ideal for small or dependency-free apps, but requires manual handling for JSON parsing and error checks including:

  ```js
  const res = await fetch(url);
  if (!res.ok) throw new Error(res.status);
  const data = await res.json();
  ```

- **Axios** streamlines tasks into concise code:

  ```js
  const { data } = await axios.get(url);
  // errors thrown automatically for 4xx/5xx
  ```

- Axios features like **interceptors** enhance maintainability:

  ```js
  axios.interceptors.request.use(cfg => {
    cfg.headers.Authorization = `Bearer ${token}`;
    return cfg;
  });
  ```

- Fetch is better when aiming for minimal footprint or in environments relying on native service workers.

---

<!--
Time: 0–4 min  
Walk through differences: explain Fetch is native and light, but Axios provides convenience features out-of-the-box:
1. Auto JSON parse and non-2xx errors -> Axios simplifies error handling.
2. Interceptors: show how Axios centrally handles auth headers or logging.
3. Cancellations and timeouts built into Axios.
4. Fetch may need polyfills for wide browser support.
Use code snippets live to show boilerplate difference.
-->

## 🔄 Managing Loading & Error States

- State variables: `loading`, `error`, `data`  
- Show spinner or fallback UI on loading  
- Display user-friendly error messages, retry options  
- Clean up effects or cancel requests on unmount to avoid leaks

```ts
const [loading, setLoading] = useState(true);
const [error, setError] = useState(null);
useEffect(() => {
  fetchData().catch(setError).finally(() => setLoading(false));
}, []);
```

<!-- 
Discuss cleanup with AbortController to avoid stale state.

-->
---

## 🚀 TanStack Query (Formerly React Query)

- Declarative, auto-managed **server-state** library for React  
- Handles **data fetching**, **caching**, **retries**, and **background updates** out-of-the-box
- Zero-config simplicity: write `useQuery({...})` and let it manage `isLoading`, `error`, and `data`
- Supports **pagination**, **infinite scrolling**, **optimistic updates**, and **SSR/SSG prefetching**
- Lightweight (no extra dependencies), extensible, and includes DevTools for debugging

<!--
Time: 0–3 min  
Explain that TanStack Query simplifies server-state management by abstracting fetch logic, caching, and mutations.  
Show a basic `useQuery` example and point out features like automatic retries, background refresh, and status flags.  
Highlight how it drastically reduces boilerplate compared to manual `useState`/`useEffect` data handling.
-->

---

## 🎉 User Feedback via Toasts 🚨

- Use third-party libs like react-toastify, Sonner, noty, or Material UI Snackbar  
- Show success, warning, or error messages on API result  
- Ensure accessibility (ARIALiveRegion) for screen reader support  
- Auto-dismiss timeouts and manual closers for better UX

<!--
Mention feedback loop: every action should update the user visibly.
Live demo: trigger an API call, show toast on success & error. Emphasize UX: toast disappears after timeout, ARIA roles alert assistive tech.
-->

---
layout: statement
---

# Demo

## API Integration, Error Handling with and without TanStack Query

---

## 🧪 React Testing Library Basics

- Encourage testing UI from the user’s perspective  
- Queries: `getByRole`, `getByText`, `findBy…`  
- Use Jest & RTL for rendering, interaction, assertions  
- Test critical flows like form submissions and API responses

<!--
Highlight RTL’s principle: test what users see, not implementation details.
-->

---

## 🏗 Building Testable Components

- Separation of concerns: UI logic vs data logic  
- Depend on props, context, or hooks—not direct APIs  
- Inject mocks or stubs easily for HTTP or behavior  
- Prefer controlled state and avoid global singletons
- A simple component test:

```js
render(<MyComp/>);
expect(screen.getByRole('button')).toBeEnabled();
```

<!--
Explain how small, self-contained components simplify testing.
Explain queries vs implementation detail isolation ([DhiWise](https://www.dhiwise.com/post/the-new-age-axios-aetup-separation-of-concerns-in-react?utm_source=chatgpt.com), [Stack Overflow](https://stackoverflow.com/questions/59162638/what-is-the-difference-between-using-react-testing-library-and-cypress?utm_source=chatgpt.com)).
-->

---

## 🧷 Structuring Tests for CI Compatibility

- Organize tests next to components: `Component.test.tsx`  
- Use `setupTests.js` to configure RTL, jest-dom globals  
- Select test environment: jsdom, or use Vitest with `@testing-library/jest-dom/vitest` ([Stack Overflow](https://stackoverflow.com/questions/63336382/which-is-the-best-practise-for-using-axios-in-react-project?utm_source=chatgpt.com), [Medium](https://tianyaschool.medium.com/jest-and-react-testing-library-best-practices-for-front-end-testing-f4a2b9ab69c0?utm_source=chatgpt.com), [GitHub](https://github.com/testing-library/jest-dom?utm_source=chatgpt.com))  
- Output coverage reports (`--coverage`) for CI dashboards  
- Add pre-commit `lint-staged` and CI test runners (GitHub Actions, Jenkins)

---

## 📌 Recap & Best Practices

- Central API abstraction ensures live updates and unified errors  
- Manage loading & error states consistently  
- Provide actionable feedback via toasts/snackbars  
- Use React Testing Library for user-centric tests ([Testing Library](https://testing-library.com/docs/react-testing-library/setup/?utm_source=chatgpt.com), [Testing Library](https://testing-library.com/docs/react-testing-library/intro/?utm_source=chatgpt.com))  
- Build components with testability in mind  
- CI-friendly test structure ensures healthy pipelines

---

## 📚 Resources

- Axios best practices ([GitHub](https://github.com/testing-library/jest-dom?utm_source=chatgpt.com), [DhiWise](https://www.dhiwise.com/post/the-new-age-axios-aetup-separation-of-concerns-in-react?utm_source=chatgpt.com))  
- RTL docs & queries ([Testing Library](https://testing-library.com/docs/react-testing-library/intro/?utm_source=chatgpt.com))  
- Testing best practices & CI ([Zealous System](https://www.zealousys.com/blog/react-testing-libraries/?utm_source=chatgpt.com))
