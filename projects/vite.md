# Vite

> Next generation frontend tooling — blazing fast dev server and optimized builds.

| Metric | Data |
|--------|------|
| GitHub | https://github.com/vitejs/vite |
| Stars | ~72,000 |
| License | MIT |
| Language | TypeScript |
| Last Updated | Active daily |
| Contributors | 1,000+ |
| npm Weekly | ~16M downloads |

## TEMC Score

| Dimension | Score | Weight | Weighted | Rationale |
|-----------|-------|--------|----------|-----------|
| **T** Technology | 92 | 25% | 23.00 | Native ESM dev server (no bundling in dev), esbuild for pre-bundling (10-100x faster than Webpack), Rollup for production builds. Vite 6 introduces Environment API for multi-runtime support (browser, SSR, edge). |
| **E** Ecosystem | 90 | 20% | 18.00 | 72k⭐, adopted by Nuxt, SvelteKit, Astro, Remix, Vitest, Storybook. 1000+ plugins. Official templates for React/Vue/Svelte/Preact/Lit. |
| **M** Market | 88 | 30% | 26.40 | De facto standard build tool for new projects. Replaced webpack/CRA in most greenfield apps. Vitest (Vite-native testing) gaining rapidly. |
| **C** Combination | 90 | 25% | 22.50 | Direct compatibility with天子 stack: powers Remix, Astro, Storybook 8+. While Next.js uses Turbopack, Vite knowledge transfers to all non-Next projects. Essential for code-base module development. |
| **Total** | — | 100% | **89.9** | |

## Architecture Highlights

### Native ESM Dev Server
Vite serves source files over native ES modules. The browser does the import resolution. Result: instant server start regardless of app size (vs Webpack's full-bundle approach).

### Dual Engine Strategy
- **Dev**: esbuild (Go, 10-100x faster) for dependency pre-bundling
- **Prod**: Rollup (mature, extensive plugin ecosystem) for optimized output
- **Future**: Rolldown (Rust, unifying dev/prod) in development

### HMR Architecture
Vite's HMR propagates over native ESM — only the changed module and its direct importers are invalidated. Sub-50ms updates even in large apps.

### Environment API (Vite 6)
```
vite/
├── packages/
│   ├── vite/
│   │   ├── src/
│   │   │   ├── node/          # Node.js server
│   │   │   │   ├── server/    # Dev server (ESM)
│   │   │   │   ├── build/     # Production build (Rollup)
│   │   │   │   ├── optimizer/ # Dependency pre-bundling (esbuild)
│   │   │   │   └── plugins/   # Built-in plugins
│   │   │   └── client/        # HMR client runtime
│   ├── plugin-react/          # React Fast Refresh
│   └── plugin-legacy/         # Legacy browser support
├── playground/                # Test fixtures
└── docs/                      # VitePress docs
```

## Key Extractable Patterns

1. **Plugin API pattern** — Rollup-compatible plugin interface (→ code-base/build/)
2. **ESM-first development** — Native modules for instant startup (→ best-practices/)
3. **Proxy configuration** — Dev server proxy for API backends (→ code-base/api/)
4. **Environment variables** — `.env` file handling with `VITE_` prefix pattern

## Competitive Comparison

| | Vite | Webpack | Turbopack | esbuild | Parcel |
|---|---|---|---|---|---|
| Stars | 72k | 65k | (Next.js) | 38k | 43k |
| Dev Start | <300ms | 10-30s | <500ms | <100ms | 1-5s |
| HMR Speed | <50ms | 200ms-2s | <50ms | N/A | 100ms |
| Config | Minimal | Complex | Zero (Next) | Minimal | Zero |
| Plugin Ecosystem | Excellent | Massive | Limited | Limited | Good |
| SSR Support | ✅ Built-in | Plugin | Next.js only | ❌ | ❌ |
| Production | Rollup | Webpack | Webpack | esbuild | SWC |

## Solo Dev Verdict

**Vite is the build tool standard for everything outside Next.js.** If天子 builds any standalone library, component package, tool, or non-Next project, Vite is the default choice. Its plugin ecosystem, instant dev experience, and universal framework support make it essential infrastructure. Even within the Next.js ecosystem, Vitest (Vite-powered testing) is replacing Jest.

**Priority**: 🟡 Important infrastructure — essential for non-Next.js projects and testing.
