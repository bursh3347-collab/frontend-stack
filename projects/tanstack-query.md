# TanStack Query

> Powerful asynchronous state management, server-state utilities and data fetching for TS/JS, React, Vue, Solid, Svelte & Angular.

| Metric | Data |
|------|------|
| GitHub | [TanStack/query](https://github.com/TanStack/query) |
| Stars | ~48,600 |
| License | MIT |
| Language | TypeScript |
| Latest | v5 |
| Maintainer | Tanner Linsley |
| npm Weekly | 711M+ total downloads |
| Contributors | 1,019 |

## TEMC Scores

| Dimension | Score | Reasoning |
|------|------|------|
| T (Tech) | 90 | Solves server state perfectly: auto-caching, background refetching, stale-while-revalidate, optimistic updates, infinite scroll, SSR/RSC support. TypeScript-first. Zero boilerplate. |
| E (Ecosystem) | 90 | 48.6k stars, 711M+ npm downloads, 1019 contributors, 719K+ GitHub dependents. Framework-agnostic (React/Vue/Solid/Svelte/Angular). Dedicated DevTools. |
| M (Market) | 88 | De facto standard for server state in React. query.gg paid course. Growing in Vue/Solid/Svelte ecosystems. Every serious React app uses it or SWR. |
| C (Combo) | 92 | **Perfect complement to base stack**: Next.js + TanStack Query + Zustand = server state + client state separation. Works with Supabase, any REST/GraphQL API. Essential for any SaaS. |
| **Overall** | **90.0** | T×0.25 + E×0.20 + M×0.25 + C×0.25 = 22.5+18.0+22.0+23.0 |

## Core Value

- **Server state solved**: Fetch, cache, synchronize, update server data
- **Zero boilerplate**: `useQuery({ queryKey, queryFn })` — that's it
- **Auto everything**: Caching, refetching, garbage collection, pagination
- **Optimistic updates**: Update UI before server confirms
- **Framework agnostic**: React, Vue, Solid, Svelte, Angular
- **DevTools**: Dedicated query inspector
- **Suspense**: First-class React Suspense support
- **RSC**: Streaming with React Server Components

```typescript
import { useQuery, useMutation, useQueryClient } from '@tanstack/react-query';

function Todos() {
  const { data, isLoading } = useQuery({
    queryKey: ['todos'],
    queryFn: fetchTodos,
  });

  const queryClient = useQueryClient();
  const mutation = useMutation({
    mutationFn: addTodo,
    onSuccess: () => queryClient.invalidateQueries({ queryKey: ['todos'] }),
  });

  if (isLoading) return 'Loading...';
  return <ul>{data.map(todo => <li key={todo.id}>{todo.title}</li>)}</ul>;
}
```

## Architecture Highlights

- **Core**: Framework-agnostic `@tanstack/query-core`
- **Adapters**: `@tanstack/react-query`, `@tanstack/vue-query`, `@tanstack/solid-query`, `@tanstack/svelte-query`, `@tanstack/angular-query`
- **Build**: pnpm monorepo + nx + tsup
- **TypeScript**: 100% type-safe, extensive generics
- **Patterns**: Query keys for cache identity, query functions for data fetching, mutations for writes

## TanStack Query vs Alternatives

| Feature | TanStack Query | SWR | RTK Query |
|---------|---------------|-----|----------|
| Stars | 48.6k | 30k | (part of Redux) |
| Bundle | ~13kb | ~4kb | ~15kb |
| Devtools | ✅ Dedicated | ❌ | ✅ |
| Mutations | ✅ Full | ⚠️ Basic | ✅ Full |
| Offline | ✅ | ❌ | ✅ |
| Pagination | ✅ Infinite | ⚠️ | ✅ |
| Framework | Multi | React | React |
| Suspense | ✅ | ✅ | ❌ |

## Risks

- Next.js App Router's `fetch` with caching may reduce need for some use cases
- v5 removed onSuccess/onError callbacks from useQuery (migration friction)
- Learning curve for advanced patterns (optimistic updates, infinite queries)
- Over-engineering risk: simple apps may not need this complexity

## Solo Dev Verdict

**必装库，没有之一。** 任何与服务端交互的React/Next.js应用都应该用TanStack Query。它和Zustand组成完美搭档：TanStack Query管服务端状态（API数据），Zustand管客户端状态（UI状态）。对天子的SaaS项目来说，这不是可选项，是必需品。48k星+711M下载=行业标准。
