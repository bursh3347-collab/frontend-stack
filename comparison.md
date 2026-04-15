# Frontend Framework & Library Comparison

## Frameworks

| Project | Stars | Type | Language | Learning Curve | Best For |
|---------|-------|------|----------|---------------|----------|
| **Next.js** | 133k | Full-stack Framework | TS/JS | Medium | Production React apps |
| **Vue.js** | 210k+ | Progressive Framework | TS/JS | Easy | Approachable full-stack |
| **Svelte** | 84k | Compile-time Framework | TS/JS | Easy | Max performance, DX |

## UI Libraries

| Project | Stars | Type | Styled? | Accessible? | Best For |
|---------|-------|------|---------|------------|----------|
| **shadcn/ui** | 94k | Copy-paste components | ✅ Tailwind | ✅ Radix | Default choice for React+Tailwind |
| **Radix UI** | 18.8k | Headless primitives | ❌ Unstyled | ✅ Full WAI-ARIA | Building custom design systems |
| **Framer Motion** | 25k | Animation library | — | — | Animations & transitions |

## State & Styling

| Project | Stars | Type | Bundle Size | Best For |
|---------|-------|------|------------|----------|
| **Tailwind CSS** | 87k | Utility-first CSS | Tiny (purged) | All styling needs |
| **Zustand** | 51k | State management | ~1kb | Client-side state |

## Stack Match Score (vs Base Stack: Next.js+Tailwind+Shadcn+TS)

| Project | Match | Notes |
|---------|-------|-------|
| Next.js | 🟢 100% | Foundation |
| Tailwind CSS | 🟢 100% | Foundation |
| shadcn/ui | 🟢 100% | Core UI layer |
| Radix UI | 🟢 95% | shadcn foundation |
| Zustand | 🟢 90% | Client state complement |
| Framer Motion | 🟢 85% | Animation complement |
| Svelte | 🔴 30% | Different ecosystem |
| Vue.js | 🔴 25% | Different ecosystem |
