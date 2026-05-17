# Missing Syllabus Topics in Source Code

This document lists the topics from the [React & Next.js Training Syllabus](https://www.chetanpanchal.com/training/dev-react-nextjs) that are **not** demonstrated or implemented in the current source code of this Vite-based React project. 

Since this codebase is a client-side React application built with Vite, all Next.js-specific features are naturally excluded. Additionally, several advanced React patterns and hooks are not currently utilized.

## React Core Concepts Missing

### Components and Props
*   **Class components Overview**: The codebase exclusively uses functional components.
*   **Prop types**: No `prop-types` validation is implemented for components.

### State and Interactivity
*   **Lifting state up**: State is mostly managed via Context (e.g., `CartContext`, `AuthContext`) or locally within components, rather than being explicitly lifted up between sibling components.
*   **Cleanup functions**: The `useEffect` hook in `ProductDetails.jsx` does not return a cleanup function.

### Hooks and Context
*   **Advanced Hooks**: The following hooks are not used:
    *   `useReducer`
    *   `useRef`
    *   `useMemo`
    *   `useCallback`
*   **New React 19 Hooks**:
    *   `use()` for promises/context
    *   `useActionState`
    *   `useOptimistic`
    *   `useFormStatus`
    *   `useTransition`

### React Patterns
*   **Component Patterns**:
    *   Higher-Order Components (HOC)
    *   Render props
    *   Compound components
    *   Controlled vs Uncontrolled components (Forms use `react-hook-form` which handles this internally, but explicit raw controlled/uncontrolled examples are missing)
*   **Refs and DOM**:
    *   Creating refs (`useRef`)
    *   `forwardRef`
    *   `useImperativeHandle`

### Performance and Optimization
*   **Optimization Techniques**:
    *   `React.memo`
    *   Code splitting with `React.lazy`
    *   `Suspense`
    *   Profiler usage
*   **Error Handling**:
    *   Error boundaries (no custom error boundary components implemented)

---

## Next.js Specific Concepts Missing (Entirely absent)

Because this is a standard Vite React application, the following Next.js ecosystem topics are completely omitted:

### Next.js Setup and Routing
*   Server-Side Rendering (SSR), Static Site Generation (SSG), and Partial Prerendering (PPR)
*   App Router architecture (Layouts, loading UI, parallel/intercepting routes)
*   Turbopack

### Data Fetching and Server Actions
*   React Server Components vs Client Components (`'use client'`)
*   Server-side data fetching with caching/revalidation
*   Route handlers and API Routes
*   Server Actions
*   After API & Middleware

### Optimization and SEO (Next.js)
*   Caching Strategies (Data Cache, Full Route Cache, Router Cache, `unstable_cache`)
*   Next.js Image Optimization (`next/image`)
*   Next.js Font Optimization (`next/font`)
*   Metadata API (Static/Dynamic metadata, Open Graph, JSON-LD)

### Authentication and Database
*   **NextAuth.js**: Currently, authentication is mocked entirely on the client side via `AuthContext`.
*   **Database Integration**: No backend database connection exists; data is loaded from local static arrays.
*   **Client vs Server Auth**: Not demonstrated.

### Deployment and Production
*   Production build specifics for Next.js / Vercel deployment.
*   Environment variable configuration (though Vite supports this, it's not explicitly used in the code).
