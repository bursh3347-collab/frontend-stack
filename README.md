[English](README.md) | [中文](README_CN.md)

![Stars](https://img.shields.io/github/stars/bursh3347-collab/frontend-stack?style=flat-square)
![License](https://img.shields.io/github/license/bursh3347-collab/frontend-stack?style=flat-square)
![Last Commit](https://img.shields.io/github/last-commit/bursh3347-collab/frontend-stack?style=flat-square)

# 🎨 frontend-stack

> ⭐ **Maturity: L2 Growing** — 13 projects analyzed with TEMC scores, best-practice guides, horizontal comparison, and architecture deep-dives.

Top frontend frameworks, UI libraries, build tools & infrastructure deep-dived with architecture analysis and TEMC scoring. React · Next.js · Vite · Tailwind · shadcn · Storybook · Turborepo and more.

**This is not a link collection.** We analyze architectures, benchmark performance, compare approaches, and provide solo dev verdicts.

## 📊 Project Rankings (by TEMC Score)

| Rank | Project | Stars | TEMC | Category |
|------|---------|-------|------|----------|
| 1 | [Next.js](projects/nextjs.md) | 138.9k | **95.6** | Framework |
| 1 | [Tailwind CSS](projects/tailwindcss.md) | 94.6k | **95.6** | Styling |
| 3 | [shadcn/ui](projects/shadcn-ui.md) | 112.4k | **94.3** | UI Components |
| 4 | [React](projects/react.md) | 233k | **94.1** | Core Library |
| 5 | [TanStack Query](projects/tanstack-query.md) | 48.6k | **90.0** | Data Fetching |
| 5 | [Radix UI](projects/radix-ui.md) | 18.8k | **90.4** | UI Primitives |
| 7 | [Vite](projects/vite.md) | 72k | **89.9** | Build Tool |
| 8 | [Zustand](projects/zustand.md) | 57.7k | **86.3** | State Management |
| 9 | [Motion](projects/motion.md) | 31.5k | **85.8** | Animation |
| 10 | [Headless UI](projects/headless-ui.md) | 28.3k | **84.3** | UI Primitives |
| 11 | [Turborepo](projects/turborepo.md) | 27k | **83.7** | Monorepo Build |
| 12 | [Remix](projects/remix.md) | 31k | **80.9** | Framework (alt) |
| 12 | [Storybook](projects/storybook.md) | 86k | **80.9** | UI Development |
| 14 | [Astro](projects/astro.md) | 51.4k | **77.8** | Framework (content) |
| 15 | [Vue.js](projects/vuejs.md) | 53.4k | **74.0** | Framework (alt) |
| 16 | [Svelte](projects/svelte.md) | 86.3k | **72.1** | Framework (alt) |
| 17 | [SolidJS](projects/solid-js.md) | 33k | **70.5** | Framework (alt) |

## 📈 Trending Chart (Last Updated: 2026-04-16)

| Rank | Project | Total Stars | Weekly Growth | Trend |
|------|---------|-------------|---------------|-------|
| 1 | [React](projects/react.md) | 233k | +500 | → |
| 2 | [Next.js](projects/nextjs.md) | 138.9k | +850 | 🚀 |
| 3 | [shadcn/ui](projects/shadcn-ui.md) | 112.4k | +1,200 | 🚀 Fastest |
| 4 | [Tailwind CSS](projects/tailwindcss.md) | 94.6k | +600 | ↑ |
| 5 | [Storybook](projects/storybook.md) | 86k | +200 | → |
| 6 | [Svelte](projects/svelte.md) | 86.3k | +350 | → |
| 7 | [Vite](projects/vite.md) | 72k | +500 | ↑ |
| 8 | [Zustand](projects/zustand.md) | 57.7k | +400 | ↑ |
| 9 | [TanStack Query](projects/tanstack-query.md) | 48.6k | +300 | ↑ |
| 10 | [Remix](projects/remix.md) | 31k | +150 | → |
| 11 | [Motion](projects/motion.md) | 31.5k | +300 | ↑ |
| 12 | [Turborepo](projects/turborepo.md) | 27k | +200 | ↑ |
| 13 | [Radix UI](projects/radix-ui.md) | 18.8k | +150 | → |

> 📊 Stars data verified via GitHub API on 2026-04-16. Weekly growth is estimated based on trajectory.

## 🏆 The Recommended Stack (2024-2026)

```
React (core) + Next.js (framework) + Tailwind CSS (styling) + shadcn/ui (components)
+ Radix UI (primitives) + Zustand (client state) + TanStack Query (server state)
+ Vite (tooling) + Motion (animations) + Turborepo (monorepo)
= The complete modern frontend stack for solo developers
```

## 📂 Repository Structure

```
frontend-stack/
├── projects/                    # Individual project analyses (13 projects)
│   ├── react.md                 # TEMC: 94.1 ⭐ NEW
│   ├── nextjs.md                # TEMC: 95.6
│   ├── shadcn-ui.md             # TEMC: 94.3
│   ├── tailwindcss.md           # TEMC: 95.6
│   ├── vite.md                  # TEMC: 89.9 ⭐ NEW
│   ├── radix-ui.md              # TEMC: 90.4
│   ├── tanstack-query.md        # TEMC: 90.0
│   ├── zustand.md               # TEMC: 86.3
│   ├── motion.md                # TEMC: 85.8
│   ├── headless-ui.md           # TEMC: 84.3
│   ├── turborepo.md             # TEMC: 83.7 ⭐ NEW
│   ├── remix.md                 # TEMC: 80.9 ⭐ NEW
│   ├── storybook.md             # TEMC: 80.9 ⭐ NEW
│   ├── astro.md                 # TEMC: 77.8
│   ├── vuejs.md                 # TEMC: 74.0
│   ├── svelte.md                # TEMC: 72.1
│   ├── solid-js.md              # TEMC: 70.5
│   └── framer-motion.md         # (→ Motion)
├── best-practices/
│   ├── component-architecture.md # Component patterns
│   └── state-management.md      # State management guide
├── comparison.md                # Horizontal comparison
├── roadmap.md                   # Frontend tech trends & predictions
├── CONTRIBUTING.md              # Contribution guide
├── SOURCES.md                   # All source projects (17 entries)
├── README.md                    # English (this file)
└── README_CN.md                 # 中文版本
```

## 📖 Best Practices Guides

| Guide | Key Insight |
|-------|-------------|
| [Component Architecture](best-practices/component-architecture.md) | Feature-based structure beats type-based |
| [State Management](best-practices/state-management.md) | Server state (TanStack Query) + client state (Zustand) = optimal |

## 🔬 TEMC Scoring Framework

| Dimension | Weight | What it measures |
|-----------|--------|------------------|
| **T** Technology | 25% | Code quality + architecture + tech stack match + docs |
| **E** Ecosystem | 20% | Stars/Forks + community + integrations + maintainer rep |
| **M** Market | 30% | Market timing + competitive scarcity + trend fit + commercializability |
| **C** Combination | 25% | Tech stack compat + extractability + business combo + learning cost |

## 🔗 Related Repositories

| Category | Repository | Maturity |
|----------|------------|----------|
| 🤖 AI Agent | [ai-agent-stack](https://github.com/bursh3347-collab/ai-agent-stack) | L2 Growing |
| 🏗️ Full-Stack SaaS | [fullstack-saas-stack](https://github.com/bursh3347-collab/fullstack-saas-stack) | L1 Growing |
| 🎨 Frontend | **frontend-stack** (this) | **L2 Growing** |
| 🔧 Code Base | [code-base](https://github.com/bursh3347-collab/code-base) | L1 Scaffolded |

## 📄 License

Analysis content: MIT. Individual projects retain their original licenses (see SOURCES.md).

---

*Powered by the TianGong Intelligence System — AI-driven open source intelligence engine*
