# Remix

> Full-stack web framework built on web standards — React Router's evolution into a framework.

| Metric | Data |
|--------|------|
| GitHub | https://github.com/remix-run/remix |
| Stars | ~31,000 |
| License | MIT |
| Language | TypeScript |
| Last Updated | Active (merged into React Router v7) |
| Contributors | 1,000+ |
| npm Weekly | ~800k downloads (react-router ~12M) |

## TEMC Score

| Dimension | Score | Weight | Weighted | Rationale |
|-----------|-------|--------|----------|-----------|
| **T** Technology | 88 | 25% | 22.00 | Web standards-first (Fetch API, FormData, Response). Nested routes with parallel data loading. React Router v7 merges Remix into the router — framework becomes optional layer. Vite-powered builds. |
| **E** Ecosystem | 75 | 20% | 15.00 | 31k⭐, strong community but smaller than Next.js. Shopify adopted Remix for Hydrogen (commerce framework). Acquired by Shopify in 2022. |
| **M** Market | 78 | 30% | 23.40 | Clear #2 React framework behind Next.js. Web standards approach attracts developers frustrated by Next.js vendor lock-in (Vercel). Growing in e-commerce via Shopify Hydrogen. |
| **C** Combination | 82 | 25% | 20.50 | Compatible with天子 React stack. Alternative deployment story (not Vercel-dependent). Vite-powered = familiar toolchain. Weaker shadcn/Radix integration vs Next.js. |
| **Total** | — | 100% | **80.9** | |

## Architecture Highlights

### Web Standards Foundation
Remix uses Web Fetch API, Request/Response objects, FormData, and Web Streams natively. Code written for Remix is portable to any JS runtime (Node, Deno, Cloudflare Workers, Bun).

### Nested Routes + Parallel Loading
Each route segment is a module with its own `loader`, `action`, and `ErrorBoundary`. Parent and child routes load data in parallel — eliminates request waterfalls.

### Progressive Enhancement
Forms work without JavaScript. `<Form>` enhances to client-side navigation when JS loads. This means:
- Works on slow connections
- Resilient to JS failures
- Better accessibility

### React Router v7 Merger
Remix is now React Router v7 with framework mode. The router becomes the framework:
```
react-router v7/
├── Framework Mode (= Remix)    # Full SSR/SSG framework
├── Library Mode (= Router)     # Client-side SPA routing
└── Shared Core                 # Route matching, data loading
```

```
remix-run/remix/
├── packages/
│   ├── remix-react/        # React integration
│   ├── remix-server-runtime/ # Server utilities
│   ├── remix-dev/          # CLI + Vite plugin
│   └── remix-cloudflare/   # Cloudflare adapter
├── templates/              # Starter templates
└── decisions/              # Architecture Decision Records
```

## Key Extractable Patterns

1. **Loader/Action pattern** — Colocated data fetching with route modules (→ best-practices/)
2. **Progressive enhancement forms** — Forms that work without JS (→ code-base/patterns/)
3. **Nested error boundaries** — Granular error isolation per route segment (→ best-practices/)
4. **Web standard Response utilities** — `json()`, `redirect()`, typed responses (→ code-base/api/)

## Competitive Comparison

| | Remix / RR v7 | Next.js | Astro | SvelteKit |
|---|---|---|---|---|
| Stars | 31k (+ 54k RR) | 133k | 51k | (Svelte 84k) |
| Rendering | SSR + SPA | SSR/SSG/ISR/RSC | MPA + Islands | SSR/SSG |
| Data Loading | Loaders (parallel) | RSC / fetch | Content Collections | Load functions |
| Build Tool | Vite | Turbopack | Vite | Vite |
| Deploy | Anywhere | Vercel-optimized | Anywhere | Anywhere |
| Forms | Progressive enhancement | Client-only | N/A | Progressive |
| Vendor Lock-in | Low (Shopify) | Medium (Vercel) | Low | Low |
| TypeScript | Excellent | Excellent | Excellent | Good |

## Solo Dev Verdict

**Remix is the escape hatch from Vercel lock-in.** For天子, Next.js remains the primary framework, but Remix/React Router v7 knowledge is valuable for: (1) Shopify Hydrogen e-commerce projects, (2) edge-first deployments on Cloudflare Workers, (3) understanding web standards deeply. The loader/action pattern is elegant and teaches good data architecture. Not a replacement for Next.js, but a strong complement.

**Priority**: 🟢 Good to know — strategic alternative for specific use cases.
