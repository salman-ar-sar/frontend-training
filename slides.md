---
theme: dracula
title: State Management & Forms
subtitle: React useState, Controlled Forms & Validation
class: text-center
transition: slide-left
mdc: true
---

# State Management & Forms

### React useState, Controlled Forms & Validation

##### Freshers Training Program

---

## useState & State Lifting

- `useState` for local component state
- "Lifting state up" to share between child components  
- Ensures single source of truth via parent state  
- Best practice for coordinated UI components

<!--
Time: 0–4 min  
Explain how `useState` works in-function. Then illustrate lifting state using React docs: moving state up to parent to share between siblings ([Reddit](https://www.reddit.com/r/reactjs/comments/10fxloj/how_do_you_use_reacthookform_and_zod_together/?utm_source=chatgpt.com), [React](https://legacy.reactjs.org/docs/lifting-state-up.html?utm_source=chatgpt.com), [React](https://react.dev/learn/sharing-state-between-components?utm_source=chatgpt.com)).
-->

---

## Controlled vs Uncontrolled Forms

- Controlled: React state drives form inputs
- Uncontrolled: DOM holds value (via refs)  
- Controlled allows dynamic validation & real-time feedback  
- Common pattern in React apps

```jsx
  const [email, setEmail] = useState('');
  const emailRef = useRef();

  // Controlled
  <input value={email} onChange={e => setEmail(e.target.value)} />

  // Uncontrolled
  <input ref={emailRef} />
```  

<!--
Time: 4–8 min  
Define controlled components. Show simple example with `value` + `onChange`. Explain benefits—easy validation, reset, conditional logic.
-->

---

## Intro to React Hook Form & Zod

- React Hook Form: performant, hook-based form library  
- Zod: schema-first validation with TypeScript support  
- Schema + resolver integration for type-safe forms ([Shadcn UI](https://ui.shadcn.com/docs/forms/react-hook-form?utm_source=chatgpt.com), [FreeCodeCamp](https://www.freecodecamp.org/news/what-is-lifting-state-up-in-react/?utm_source=chatgpt.com), [FreeCodeCamp](https://www.freecodecamp.org/news/react-form-validation-zod-react-hook-form/?utm_source=chatgpt.com))  
- Minimal re-rendering and powerful validation

<!--
Time: 8–12 min  
Explain react-hook-form’s advantages: minimal re-renders, easy integration with schemas via resolvers. Cite Zod tutorial from contentful & freeCodeCamp ([Micah Jon](https://micahjon.com/2023/form-validation-with-zod/?utm_source=chatgpt.com)).
-->

---
layout: statement
class: font-bold
---

# Demo

## Controlled Form with React Hook Form & Zod

<!-- 
1. **Parent** holds form state context  
2. Create controlled `<input>` using RHF’s `register`  
3. Define Zod schema (e.g., email, password, confirm)  
4. Setup `useForm({ resolver: zodResolver(schema) })`  
5. Submit => console.log or error messages displayed  
6. On error: real-time inline messages; highlight fields
- Start with demo code loaded in browser  
- Show real-time error as user types (e.g., invalid email)  
- Show unsuccessful submit with errors  
- Correct fields then successful submit  
- Explain how controlled forms and schema validation works live
-->

---

## Advanced Validation Features

- Cross-field checks: e.g. `confirmPassword` matches `password`  
- Dynamic schemas using `superRefine` or conditional logic ([Micah Jon](https://micahjon.com/2023/form-validation-with-zod/?utm_source=chatgpt.com), [FreeCodeCamp](https://www.freecodecamp.org/news/react-form-validation-zod-react-hook-form/?utm_source=chatgpt.com), [Contentful](https://www.contentful.com/blog/react-hook-form-validation-zod/?utm_source=chatgpt.com))  
- Full type safety and server-side reuse with Zod

<!--
Time: 12–15 min  
Show advanced Zod capabilities like `refine` or `superRefine`. Explain how full validation logic can be shared between client and server.
-->

---
layout: statement
class: font-bold
---

# Demo

## Global State Management with Zustand and Jotai

---

## Zustand & Jotai for Global State

- Zustand: simple, lightweight, and easy to use
- Jotai: atomic state management with React hooks
- Both integrate well with React Hook Form for global form state

<!--
Time: 15–18 min  
Explain how Zustand and Jotai work. Show example with global form state.
-->

---

## 📚 Next Steps

- Try your own form with and without RHF
- Use other schemas like Yup or Joi via RHF resolver  
- Explore more about state libraries (Zustand, Jotai, Redux) for global form state
