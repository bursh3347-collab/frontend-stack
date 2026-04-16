# Turborepo

> High-performance monorepo build system — incremental builds, remote caching, task orchestration.

| Metric | Data |
|--------|------|
| GitHub | https://github.com/vercel/turborepo |
| Stars | ~27,000 |
| License | MIT |
| Language | Rust + Go |
| Last Updated | Active daily |
| Contributors | 400+ |
| npm Weekly | ~3.5M downloads |

## TEMC Score

| Dimension | Score | Weight | Weighted | Rationale |
|-----------|-------|--------|----------|-----------|
| **T** Technology | 88 | 25% | 22.00 | Rust-powered task runner, content-aware hashing, remote caching, parallel task execution. Turbo 2.0 introduced watch mode, boundaries, and daemon process for persistent caching. |
| **E** Ecosystem | 82 | 20% | 16.40 | 27k⭐, Vercel-maintained. Integrates with npm/pnpm/yarn workspaces. Growing adoption: Vercel, Shopify, AWS Amplify, and many open-source projects (shadcn/ui uses Turborepo). |
| **M** Market | 80 | 30% | 24.00 | Leading JS monorepo tool alongside Nx. Simpler than Nx (convention over configuration). Critical as projects grow beyond single-app repos. |
| **C** Combination | 85 | 25% | 21.25 | Perfect for天子's multi-product strategy. When running 2-3 Micro SaaS products, shared code (UI components, utils, API clients) lives in a monorepo. Turborepo + pnpm workspaces = standard setup. shadcn/ui itself uses this exact pattern. |
| **Total** | — | 100% | **83.7** | |

## Architecture Highlights

### Content-Aware Hashing
Turborepo hashes file contents (not timestamps) to determine what needs rebuilding. If you change `packages/ui/Button.tsx`, only tasks that depend on `packages/ui` re-run.

### Remote Caching
Build artifacts cached remotely (Vercel or self-hosted). When CI or another developer runs the same build, it's instant — pulled from cache instead of rebuilt.

### Task Graph & Parallel Execution
```json
// turbo.json
{
  "tasks": {
    "build": { "dependsOn": ["^build"], "outputs": [".next/**", "dist/**"] },
    "test": { "dependsOn": ["build"] },
    "lint": {},
    "dev": { "cache": false, "persistent": true }
  }
}
```
Turborepo builds a DAG (directed acyclic graph) of tasks and executes independent tasks in parallel.

### Monorepo Structure Pattern
```
my-turborepo/
├── apps/
│   ├── web/            # Next.js app (product A)
│   ├── api/            # Backend API
│   └── admin/          # Admin dashboard
├── packages/
│   ├── ui/             # Shared UI components (shadcn/ui)
│   ├── config-eslint/  # Shared ESLint config
│   ├── config-ts/      # Shared TypeScript config
│   ├── database/       # Shared Drizzle schema
│   └── utils/          # Shared utilities
├── turbo.json          # Task pipeline config
├── pnpm-workspace.yaml # Workspace definition
└── package.json        # Root package
```

```
vercel/turborepo/
├── crates/
│   ├── turborepo-lib/     # Core Rust library
│   ├── turborepo-cache/   # Caching logic
│   ├── turborepo-graph/   # Task DAG
│   └── turborepo-hash/    # Content hashing
├── packages/
│   ├── turbo-gen/         # Code generation
│   └── create-turbo/      # CLI scaffolding
└── examples/              # Starter templates
```

## Key Extractable Patterns

1. **Monorepo workspace structure** — apps/ + packages/ separation (→ code-base/monorepo/)
2. **Task pipeline configuration** — `turbo.json` DAG definition (→ code-base/build/)
3. **Shared config packages** — ESLint, TypeScript, Prettier shared across apps (→ code-base/config/)
4. **Remote caching setup** — CI/CD acceleration pattern (→ code-base/deploy/)

## Competitive Comparison

| | Turborepo | Nx | Lerna | Moon | Bazel |
|---|---|---|---|---|---|
| Stars | 27k | 24k | 35k | 3k | 23k |
| Language | Rust | TypeScript | TypeScript | Rust | Java |
| Config Complexity | Low | Medium | Low | Medium | High |
| Remote Cache | ✅ (Vercel) | ✅ (Nx Cloud) | ❌ | ✅ | ✅ |
| Task Orchestration | ✅ | ✅ | Basic | ✅ | ✅ |
| Code Generation | Basic | Extensive | ❌ | ✅ | ❌ |
| Framework Plugins | ❌ | React/Angular/Vue | ❌ | ❌ | ❌ |
| Learning Curve | Low | Medium | Low | Medium | High |
| Best For | JS/TS monorepos | Enterprise polyglot | Legacy | Polyglot | Google-scale |

## Solo Dev Verdict

**Turborepo is your scaling infrastructure.** For天子's multi-product Micro SaaS strategy, the moment you have 2 products sharing a UI library or API client, Turborepo pays for itself. The setup is minimal (one `turbo.json`), and the payoff is: (1) shared code without npm publishing overhead, (2) faster CI with remote caching, (3) consistent configs across products. shadcn/ui, t3-oss, and most modern SaaS templates use Turborepo — learning it is learning the industry standard.

**Priority**: 🟡 Important — adopt when launching second Micro SaaS product.
