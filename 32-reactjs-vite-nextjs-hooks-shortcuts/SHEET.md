# ⚛️ Module 32: React.js, Vite, Next.js & Hooks Master Sheet (30 Items)

Complete reference for 30 essential React.js CLI commands, Vite setups, Next.js triggers, and React Hooks code templates categorized by difficulty level (🟢 Easy, 🟡 Medium, 🔴 Hard).

---

## 🟢 Level 1: Easy / Beginner CLI & Setup Commands (1 - 10)

```bash
# 1. Initialize new React project using Vite (Fastest)
npm create vite@latest my-app -- --template react

# 2. Initialize new Next.js App Router project
npx create-next-app@latest my-next-app

# 3. Start local development server (Vite)
npm run dev

# 4. Start local development server (Next.js)
npx next dev

# 5. Build production bundle (Vite)
npm run build

# 6. Preview production build locally (Vite)
npm run preview

# 7. Build production bundle (Next.js)
npx next build

# 8. Start production server (Next.js)
npx next start

# 9. Install TailwindCSS for React Vite project
npm install -D tailwindcss postcss autoprefixer

# 10. Install React Router DOM
npm install react-router-dom
```

---

## 🟡 Level 2: Medium / Intermediate React Hooks Cheatsheets (11 - 20)

```jsx
// 11. useState Hook Template
const [count, setCount] = useState(0);

// 12. useEffect Hook Template (ComponentDidMount & Cleanup)
useEffect(() => {
    console.log("Component mounted");
    return () => console.log("Cleanup on unmount");
}, []);

// 13. useRef Hook Template (DOM Element Reference)
const inputRef = useRef(null);
const focusInput = () => inputRef.current.focus();

// 14. useContext Hook Template
const theme = useContext(ThemeContext);

// 15. useMemo Hook Template (Expensive Calculation Caching)
const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);

// 16. useCallback Hook Template (Function Reference Memoization)
const handleClick = useCallback(() => {
    doSomething(a, b);
}, [a, b]);

// 17. Custom Hook Skeleton Template
function useFetch(url) {
    const [data, setData] = useState(null);
    useEffect(() => {
        fetch(url).then(res => res.json()).then(setData);
    }, [url]);
    return data;
}

// 18. React Router Route Definition Template
<Routes>
    <Route path="/" element={<Home />} />
    <Route path="/about" element={<About />} />
</Routes>

// 19. React Controlled Input Form Binding
<input value={text} onChange={(e) => setText(e.target.value)} />

// 20. Conditional Rendering Operator
{isLoading ? <Spinner /> : <DataView />}
```

---

## 🔴 Level 3: Hard / Advanced Next.js & Optimization Commands (21 - 30)

```bash
# 21. Run Next.js linter check
npx next lint

# 22. Analyze Next.js production bundle sizes
ANALYZE=true npx next build

# 23. Clear Next.js build cache folder (.next)
rm -rf .next

# 24. Install Lucide React Icons package
npm install lucide-react

# 25. Install Shadcn UI CLI
npx shadcn@latest init

# 26. Add Component via Shadcn UI CLI
npx shadcn@latest add button card dialog

# 27. Install TanStack React Query for async data fetching
npm install @tanstack/react-query

# 28. Install Zustand lightweight state management
npm install zustand

# 29. Install Framer Motion animation library
npm install framer-motion

# 30. Run React production bundle typecheck without emitting files
npx tsc --noEmit
```
