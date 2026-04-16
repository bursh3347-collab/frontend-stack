# SolidJS

> A declarative, efficient, and flexible JavaScript library for building user interfaces with fine-grained reactivity.

| Metric | Data |
|------|------|
| GitHub | [solidjs/solid](https://github.com/solidjs/solid) |
| Stars | ~33,000 |
| License | MIT |
| Language | TypeScript |
| Latest | v1.8.x |
| Maintainer | Ryan Carniato |
| Bundle Size | ~5kb min+gzip |

## TEMC Scores

| Dimension | Score | Reasoning |
|------|------|------|
| T (Tech) | 92 | No Virtual DOM = 50-70% better runtime performance vs React. Fine-grained reactivity (Signals) compiles to direct DOM updates. ~5kb bundle (vs React+ReactDOM ~40kb). Closest to vanilla JS performance in benchmarks. |
| E (Ecosystem) | 72 | 33k stars, growing but much smaller than React. SolidStart meta-framework. Sponsors: Cloudflare, Netlify, Vercel, Builder.io. npm: solid-js has moderate downloads. |
| M (Market) | 68 | Signals pattern influenced Angular, React, Vue — but adoption remains niche. SolidStart not yet production-proven at scale. Hiring market thin. |
| C (Combo) | 50 | Different ecosystem from Next.js/React base stack. JSX syntax similar but reactivity model fundamentally different (no re-renders). Not a drop-in React replacement. TanStack Query supports Solid. |
| **Overall** | **70.5** | T×0.25 + E×0.20 + M×0.25 + C×0.25 = 23.0+14.4+17.0+12.5 |

## Core Value

- **No Virtual DOM**: Compiles JSX to direct DOM operations
- **Fine-grained Reactivity**: Signals update only specific DOM nodes, not components
- **~5kb bundle**: Smallest major framework
- **Familiar JSX**: React developers can pick up quickly
- **True reactivity**: `createSignal`, `createEffect`, `createMemo` — no stale closures
- **Benchmarks**: Consistently #1-2 in js-framework-benchmark (near vanilla JS)

```tsx
import { createSignal } from "solid-js";

function Counter() {
  const [count, setCount] = createSignal(0);
  // Only this specific text node updates, not the whole component
  return <button onClick={() => setCount(count() + 1)}>
    Count: {count()}
  </button>;
}
```

## Architecture Highlights

- **Compiler**: Babel plugin transforms JSX to fine-grained DOM operations
- **Reactivity**: Signal-based (createSignal, createStore, createResource)
- **SSR**: SolidStart meta-framework (Vinxi-based)
- **Routing**: @solidjs/router
- **No re-renders**: Components run once, only reactive expressions update

## Key Influence

Solid's Signals pattern has been adopted by:
- **Angular** (v16+ Signals)
- **Vue** (already signal-like with ref/reactive)
- **Preact** (Signals)
- **Qwik** (fine-grained reactivity)

Solid didn't win the adoption war, but it won the ideas war.

## Risks

- Small ecosystem: far fewer libraries than React
- SolidStart still maturing vs Next.js production-proven
- Hiring: very few developers know Solid
- React Compiler may close the performance gap
- Component functions run once — different mental model causes bugs for React devs

## Solo Dev Verdict

技术上SolidJS是当前最强前端框架（性能接近原生JS），Signals理念已影响整个行业。但生态太小，不适合一人公司主技术栈。天子策略：**学习Signals思想**（已被Angular/Vue/Preact采纳），但生产项目仍用React/Next.js。如果做性能极端敏感的工具（如实时数据可视化），SolidJS是秘密武器。
