# React

> The library for web and native user interfaces — the foundation of modern frontend.

| Metric | Data |
|--------|------|
| GitHub | https://github.com/facebook/react |
| Stars | ~233,000 |
| License | MIT |
| Language | JavaScript / TypeScript |
| Last Updated | Active daily |
| Contributors | 1,600+ |
| npm Weekly | ~28M downloads |

## TEMC Score

| Dimension | Score | Weight | Weighted | Rationale |
|-----------|-------|--------|----------|-----------|
| **T** Technology | 95 | 25% | 23.75 | Fiber architecture, concurrent rendering, server components, hooks API — production-grade at planetary scale. React 19 introduces Actions, `use()`, and document metadata. Compiler (React Compiler / Forget) eliminates manual memoization. |
| **E** Ecosystem | 98 | 20% | 19.60 | Largest frontend ecosystem on Earth: 233k⭐, 28M weekly npm downloads, 1600+ contributors. Next.js/Remix/Gatsby built on top. Every major UI library (shadcn, Radix, MUI, Ant Design) is React-first. |
| **M** Market | 90 | 30% | 27.00 | ~65% market share in production web apps. Used by Meta, Netflix, Airbnb, Uber, Discord, and virtually every tech company. Dominant in job market. React Native extends to mobile. |
| **C** Combination | 95 | 25% | 23.75 | Perfect match with天子 base stack (Next.js = React). All code-base modules, SaaS templates, and UI libraries assume React. Zero friction integration. |
| **Total** | — | 100% | **94.1** | |

## Architecture Highlights

### Fiber Reconciler
React's custom reconciler enables incremental rendering — work can be split into chunks and spread across frames. This is the foundation for concurrent features (Suspense, Transitions, streaming SSR).

### Server Components (RSC)
React 19's paradigm shift: components that run only on the server, with zero client JS. Enables:
- Direct database access in components
- Smaller client bundles
- Streaming HTML with Suspense boundaries

### React Compiler (Forget)
Automatic memoization at build time. Eliminates `useMemo`, `useCallback`, `React.memo` boilerplate. Ships with React 19 in experimental mode.

### Hooks Architecture
Functional composition model: `useState`, `useEffect`, `useContext`, `useReducer`, custom hooks. Replaced class components as the standard pattern.

```
react/
├── packages/
│   ├── react/              # Core API (createElement, hooks)
│   ├── react-dom/          # DOM renderer + server
│   ├── react-reconciler/   # Fiber reconciler (shared)
│   ├── react-server/       # RSC runtime
│   ├── react-compiler/     # Auto-memoization compiler
│   └── shared/             # Internal utilities
├── fixtures/               # Test apps
└── scripts/                # Build tooling
```

## Key Extractable Patterns

1. **Hooks composition pattern** — Custom hooks as reusable logic units (→ code-base/patterns/)
2. **Suspense boundary architecture** — Declarative loading states (→ best-practices/)
3. **Server/Client component boundary** — `'use client'` / `'use server'` directives (→ best-practices/)
4. **Concurrent rendering patterns** — `useTransition`, `useDeferredValue` for responsive UIs

## Competitive Comparison

| | React | Vue.js | Svelte | SolidJS |
|---|---|---|---|---|
| Stars | 233k | 210k | 84k | 33k |
| Approach | Virtual DOM + Fiber | Virtual DOM + Proxy | Compile-time | Fine-grained reactivity |
| Bundle Size | ~42kb | ~33kb | ~2kb (compiled) | ~7kb |
| Learning Curve | Medium | Low | Low | Medium |
| Ecosystem Size | Massive | Large | Growing | Small |
| Job Market | Dominant | Strong (Asia) | Niche | Niche |
| Server Components | ✅ RSC | ❌ | ❌ | ❌ (partial) |
| TypeScript | Excellent | Excellent | Good | Excellent |

## Solo Dev Verdict

**React is not optional — it's the foundation.** Every tool in天子's stack (Next.js, shadcn/ui, Radix UI, Zustand) is built on React. Understanding React deeply (hooks, Suspense, RSC, Compiler) directly multiplies productivity across the entire stack. The ecosystem moat is insurmountable for competitors in the next 3-5 years.

**Priority**: 🔴 Core infrastructure — must master.
