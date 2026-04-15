# Zustand

> A small, fast, and scalable bear-necessities state management solution for React.

| Metric | Data |
|------|------|
| GitHub | [pmndrs/zustand](https://github.com/pmndrs/zustand) |
| Stars | 57,745 |
| License | MIT |
| Language | TypeScript |
| Maintainer | Poimandres (Daishi Kato) |

## TEMC Scores

| Dimension | Score | Reasoning |
|------|------|------|
| T (Tech) | 90 | Minimal API, no boilerplate, no providers needed. TypeScript-first. Middleware support (persist, devtools, immer). ~1kb bundle. |
| E (Ecosystem) | 88 | 58k stars. Part of pmndrs ecosystem. npm: millions of weekly downloads. Used by major companies. |
| M (Market) | 82 | Winning the React state management war against Redux. Simpler than Jotai (from same author). |
| C (Combo) | 85 | Perfect for client-side state in Next.js apps. Complements React Query (server state) + Zustand (client state). |
| **Overall** | **86.3** | |

## Core Value

- **Tiny API**: `create((set) => ({...}))` — that's it
- **No boilerplate**: No actions, reducers, dispatch
- **No providers**: Works outside React (vanilla JS)
- **Middleware**: `persist` (localStorage), `devtools`, `immer`
- **~1kb**: Smallest state management library
- **TypeScript**: Full type inference

```typescript
const useStore = create((set) => ({
  count: 0,
  increment: () => set((state) => ({ count: state.count + 1 })),
}))
```

## Risks

- Simple API means less structure for large teams
- No built-in selectors optimization (need `shallow` comparison)
- Server Components in Next.js reduce need for client state

## 天子点评

客户端状态首选，API极简，1kb体积完美。Server Components时代客户端状态需求在减少，但购物车、UI状态、表单暂存这些场景仍然需要。Zustand + React Query = 客户端+服务端状态完美分离。
