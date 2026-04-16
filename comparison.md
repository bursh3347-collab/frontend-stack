# Frontend Framework & Library Comparison

## Frameworks

| Project | Stars | Type | Language | Learning Curve | Best For | Stack Match |
|---------|-------|------|----------|---------------|----------|-------------|
| **Next.js** | 133k | Full-stack Framework | TS/JS | Medium | Production React apps, SaaS | 🟢 100% |
| **Vue.js** | 210k+ | Progressive Framework | TS/JS | Easy | Approachable full-stack | 🔴 25% |
| **Svelte** | 84k | Compile-time Framework | TS/JS | Easy | Max performance, DX | 🔴 30% |
| **Astro** | 51k | Content Framework | TS/JS | Easy | Content sites, blogs, docs | 🟡 45% |
| **SolidJS** | 33k | Reactive Framework | TS/JS | Medium | Performance-critical UIs | 🔴 35% |

## UI Libraries

| Project | Stars | Type | Styled? | Accessible? | Best For | Stack Match |
|---------|-------|------|---------|------------|----------|-------------|
| **shadcn/ui** | 94k | Copy-paste components | ✅ Tailwind | ✅ Radix | Default choice for React+Tailwind | 🟢 100% |
| **Radix UI** | 18.8k | Headless primitives | ❌ Unstyled | ✅ Full WAI-ARIA | Building custom design systems | 🟢 95% |
| **Headless UI** | 28k | Headless components | ❌ Unstyled | ✅ Full WAI-ARIA | Tailwind-native accessible UI | 🟢 90% |

## Animation

| Project | Stars | Type | Frameworks | Best For | Stack Match |
|---------|-------|------|-----------|----------|-------------|
| **Motion** | 27k | Animation library | React/JS/Vue | All animations & transitions | 🟢 90% |
| **Framer Motion** | (→Motion) | Legacy name | React | See Motion | — |

## State & Data

| Project | Stars | Type | Bundle Size | Best For | Stack Match |
|---------|-------|------|------------|----------|-------------|
| **TanStack Query** | 48.6k | Server state | ~13kb | API data fetching & caching | 🟢 95% |
| **Zustand** | 51k | Client state | ~1kb | Client-side UI state | 🟢 90% |

## Styling

| Project | Stars | Type | Bundle Size | Best For | Stack Match |
|---------|-------|------|------------|----------|-------------|
| **Tailwind CSS** | 87k | Utility-first CSS | Tiny (purged) | All styling needs | 🟢 100% |

## Stack Match Score (vs Base Stack: Next.js + Tailwind + shadcn/ui + TS)

| Project | Match | Role in Stack |
|---------|-------|---------------|
| Next.js | 🟢 100% | Foundation framework |
| Tailwind CSS | 🟢 100% | Styling foundation |
| shadcn/ui | 🟢 100% | Core UI components |
| TanStack Query | 🟢 95% | Server state (essential) |
| Radix UI | 🟢 95% | shadcn/ui foundation |
| Headless UI | 🟢 90% | Alternative accessible components |
| Zustand | 🟢 90% | Client state complement |
| Motion | 🟢 90% | Animation layer |
| Astro | 🟡 45% | Content/marketing sites only |
| SolidJS | 🔴 35% | Different ecosystem (learn ideas) |
| Svelte | 🔴 30% | Different ecosystem |
| Vue.js | 🔴 25% | Different ecosystem |

## TEMC Score Rankings

| # | Project | T | E | M | C | Overall |
|---|---------|---|---|---|---|--------|
| 1 | TanStack Query | 90 | 90 | 88 | 92 | **90.0** |
| 2 | Zustand | 90 | 88 | 82 | 85 | **86.3** |
| 3 | Motion | 88 | 85 | 82 | 88 | **85.8** |
| 4 | Headless UI | 85 | 82 | 80 | 90 | **84.3** |
| 5 | Astro | 88 | 85 | 80 | 55 | **77.8** |
| 6 | SolidJS | 92 | 72 | 68 | 50 | **70.5** |

*Note: Next.js, shadcn/ui, Tailwind CSS, Radix UI, Vue.js, Svelte scored in their respective project files.*
