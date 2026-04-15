# Framer Motion (Motion)

> A production-ready React animation library with a declarative API.

| Metric | Data |
|------|------|
| GitHub | [motiondivision/motion](https://github.com/motiondivision/motion) |
| Stars | 31,534 |
| License | MIT |
| Language | TypeScript |

## TEMC Scores

| Dimension | Score | Reasoning |
|------|------|------|
| T (Tech) | 88 | Declarative animations, layout animations, gesture support, scroll-triggered animations. Hardware accelerated. |
| E (Ecosystem) | 82 | 31.5k stars. Used by many popular sites. Rebranded from Framer Motion to Motion for framework-agnostic support. |
| M (Market) | 75 | Go-to React animation library. Competing with CSS animations and GSAP. |
| C (Combo) | 78 | Works great with Next.js + shadcn. Used for landing pages, dashboards, micro-interactions. |
| **Overall** | **80.1** | |

## Core Value

- **Declarative**: `<motion.div animate= x: 100  />` — simple API
- **Layout animations**: `layoutId` for shared element transitions
- **Gestures**: Drag, hover, tap, pan, scroll
- **Exit animations**: `AnimatePresence` for unmount animations
- **Spring physics**: Natural-feeling motion
- **Scroll-triggered**: Viewport-aware animations

## Risks

- Bundle size (~30kb) larger than CSS-only solutions
- Overuse can hurt performance
- Rebranding may cause confusion

## 天子点评

Landing page和产品演示的加分项。不是核心依赖，但能让SaaS产品看起来更专业——首页动画、组件过渡、滚动触发效果，这些是转化率的隐形推手。按需引入，不要全局滥用。
