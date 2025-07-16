# 🚀 Code Splitting in Next.js

## What is Code Splitting?

**Code splitting** means breaking your JavaScript code into smaller chunks so that the browser only loads what it needs, when it needs it — instead of downloading the entire app at once.

---

## ✅ How Code Splitting Works in Next.js

Next.js does **automatic code splitting by page**:

- Each route (`/home`, `/about`, `/posts`) gets its **own JavaScript bundle**.
- Visiting `/about` loads **only its code**, not `/posts`.
- Shared code (like React, layout, etc.) is loaded **once**.

```tsx
export default function Home() {
  return <h1>Home Page</h1>;
}

export default function About() {
  return <h1>About Page</h1>;
}
```

Next.js will:

- Create separate JS files for / and /about
- Load only what’s needed for the current route

## 🔁 Dynamic Code Splitting in Next.js

You can also manually split code using next/dynamic:

```tsx
import dynamic from "next/dynamic";

const HeavyComponent = dynamic(() => import("../components/HeavyComponent"), {
  loading: () => <p>Loading...</p>,
});

export default function Page() {
  return <HeavyComponent />;
}
```

🧠 Result: HeavyComponent is only loaded when this page is visited.

## 🔁 React (CRA) Comparison

In Create React App (CRA):

- By default, CRA bundles the entire app into a single large JS file.

- You must manually use React.lazy() and Suspense to split code.

CRA Example
```tsx
const LazyAbout = React.lazy(() => import("./About"));

function App() {
  return (
    <Suspense fallback={<div>Loading...</div>}>
      <LazyAbout />
    </Suspense>
  );
}
```

⚠️ CRA Downsides:

- Code splitting is manual
- Single entry point means heavier initial bundle
- Harder to optimize large apps


