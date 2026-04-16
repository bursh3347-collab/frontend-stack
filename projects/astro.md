# Astro

> The web framework for content-driven websites. Zero JS by default.

| Metric | Data |
|------|------|
| GitHub | [withastro/astro](https://github.com/withastro/astro) |
| Stars | ~51,400 |
| License | MIT |
| Language | TypeScript |
| Latest | v6.1 (March 2026) |
| Maintainer | Astro (acquired by Cloudflare) |
| Contributors | 1,000+ |
| npm Weekly | Millions |

## TEMC Scores

| Dimension | Score | Reasoning |
|------|------|------|
| T (Tech) | 88 | Island architecture (partial hydration), zero JS default, server-first rendering. Astro 6 brings experimental Rust compiler, live content collections, CSP support. Supports React/Vue/Svelte/Solid components in same project. |
| E (Ecosystem) | 85 | 51k+ stars, Cloudflare acquisition (2026) = long-term stability. 533+ npm dependents. Active Discord. Official integrations for all major frameworks. |
| M (Market) | 80 | Dominant in content-driven sites (blogs, docs, marketing). Starlight for docs. Cloudflare backing accelerates enterprise adoption. Not a SaaS framework though. |
| C (Combo) | 55 | Different paradigm from Next.js base stack. Best for landing pages, blogs, docs — not interactive SaaS dashboards. Can complement Next.js for marketing site while SaaS stays on Next.js. |
| **Overall** | **77.8** | T×0.25 + E×0.20 + M×0.25 + C×0.25 = 22.0+17.0+20.0+13.75 |

## Core Value

- **Zero JS by default**: Ships pure HTML, only hydrates interactive islands
- **Island Architecture**: `<Counter client:load />` — opt-in interactivity per component
- **Framework agnostic**: Use React, Vue, Svelte, Solid, Preact in same project
- **Content Collections**: Type-safe Markdown/MDX with schema validation
- **Server-first**: SSR by default, static output optional
- **Cloudflare-backed**: Acquired 2026, long-term investment guaranteed

```astro
---
// src/pages/index.astro
import Layout from '../layouts/Layout.astro';
import Counter from '../components/Counter.tsx';
---
<Layout title="Home">
  <h1>Welcome</h1>
  <!-- Zero JS until you opt in -->
  <Counter client:visible />
</Layout>
```

## Architecture Highlights

- **Monorepo**: pnpm workspace + Turbo build system
- **Compiler**: Custom compiler (Rust experimental in v6)
- **Rendering**: Server-first with optional SSG/SSR/Hybrid
- **Integrations**: @astrojs/react, @astrojs/vue, @astrojs/svelte, @astrojs/node, @astrojs/vercel, @astrojs/cloudflare
- **Content Layer**: Content Collections with Zod schema validation

## Risks

- Not designed for highly interactive SaaS apps (use Next.js for that)
- Cloudflare acquisition could mean platform lock-in over time
- Smaller job market compared to Next.js/React
- Island architecture adds mental overhead for mixed interactive/static pages

## Solo Dev Verdict

Astro是内容站点的终极选择——博客、文档、Landing Page性能碾压Next.js。但不适合SaaS仪表盘等高交互场景。天子策略：SaaS用Next.js，Landing Page/文档用Astro。Cloudflare收购后生态稳定性有保障。如果要做SEO密集的内容营销站，Astro是第一选择。
