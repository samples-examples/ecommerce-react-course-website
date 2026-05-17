# React Course Syllabus to Code Linkage

This document provides a mapping between the topics covered in the [React & Next.js Training Syllabus](https://www.chetanpanchal.com/training/dev-react-nextjs) and their specific implementations in this project's source code. You can use this guide during demonstrations to show participants how these concepts are applied in a real-world application.

_Note: As this is a standard React (Vite) project, it demonstrates the React-specific portions of the syllabus. Next.js specific topics (App Router, Server Components, etc.) are outside the scope of this particular codebase._

## React Introduction

- **Functional components**:
  - `src/App.jsx:12` - Main `App` component definition.
  - `src/components/ProductCard.jsx:4` - `ProductCard` component definition.
- **JSX syntax and rules**:
  - `src/App.jsx:13-27` - Overall layout combining HTML-like tags with React components.
- **Conditional rendering**:
  - `src/pages/Auth.jsx:41` - Ternary operator (`mode === "signup" ? "Sign Up" : "Login"`).
  - `src/pages/Auth.jsx:44` - Logical AND (`error && <div className="error-message">...</div>`).
  - `src/pages/ProductDetails.jsx:23-25` - Early return for loading state (`if (!product) return ...`).
- **Lists and keys**:
  - `src/pages/Home.jsx:17-19` - Iterating over products using `.map()` and assigning the `key` prop.
  - `src/pages/Checkout.jsx:26-67` - Rendering cart items.

## Components and Props

- **Component composition**:
  - `src/App.jsx:14-26` - Composing multiple components together (e.g., nesting `<Navbar />` and `<Routes>` inside `<CartProvider>` and `<AuthProvider>`).
- **Passing props**:
  - `src/pages/Home.jsx:18` - Passing the `product` object down to the `<ProductCard>` component.
- **Destructuring props**:
  - `src/components/ProductCard.jsx:4` - Destructuring `{ product }` directly in the function parameters.
- **Children props**:
  - `src/context/CartContext.jsx:6` - Accepting `{ children }` to wrap application components inside the provider.
  - `src/context/AuthContext.jsx:5` - Accepting `{ children }` for the authentication provider.

## State and Interactivity

- **useState hook**:
  - `src/pages/Auth.jsx:7-8` - Managing `mode` (login/signup) and `error` states.
  - `src/pages/ProductDetails.jsx:8` - Holding the currently viewed `product` data.
  - `src/context/CartContext.jsx:7` - Tracking the `cartItems` array.
- **State updates and immutability**:
  - `src/context/CartContext.jsx:17` - Updating array state immutably (`[...prevItems, { id, quantity: 1 }]`).
  - `src/context/CartContext.jsx:32-35` - Modifying existing array items immutably using `.map()`.
- **Event Handling**:
  - `src/pages/Auth.jsx:93` - Inline arrow function for `onClick` (`onClick={() => setMode("login")}`).
  - `src/components/ProductCard.jsx:27` - Calling a function with parameters in `onClick` (`onClick={() => addToCart(product.id)}`).
- **Form handling**:
  - `src/pages/Auth.jsx:43` - Intercepting form submission using `onSubmit` (integrated with `react-hook-form`).
- **useEffect hook & Dependency arrays**:
  - `src/pages/ProductDetails.jsx:12-21` - Fetching/setting product data on component mount or when the `id` changes (dependency array `[id]`).

## Hooks and Context

- **Creating context**:
  - `src/context/CartContext.jsx:4` - Using `createContext(null)`.
  - `src/context/AuthContext.jsx:3` - Using `createContext(null)`.
- **Context as provider**:
  - `src/context/CartContext.jsx:66-74` - The `<CartContext.Provider>` component supplying values down the tree.
- **useContext hook / Custom hooks**:
  - `src/context/CartContext.jsx:78-84` - Custom `useCart` hook that consumes the `CartContext`.
  - `src/context/AuthContext.jsx:56-62` - Custom `useAuth` hook that consumes the `AuthContext`.

## Routing (React Router Application)

_Although Next.js App Router is covered in the syllabus, this Vite-based project leverages React Router for equivalent client-side routing concepts._

- **Setup and Router Architecture**:
  - `src/main.jsx:8-10` - Application wrapped in `<BrowserRouter>`.
  - `src/App.jsx:18-23` - Route definitions using `<Routes>` and `<Route>`.
- **Dynamic Routes**:
  - `src/App.jsx:22` - Route with dynamic segment (`/products/:id`).
  - `src/pages/ProductDetails.jsx:7` - Extracting the dynamic segment using the `useParams` hook.
- **Navigation & Links**:
  - `src/components/ProductCard.jsx:22` - Using `<Link>` component for client-side navigation without full page reloads.
  - `src/pages/ProductDetails.jsx:9` & `16` - Programmatic navigation using the `useNavigate` hook.
