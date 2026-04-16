# Motion (formerly Framer Motion)

> A production-grade animation library for React, JavaScript, and Vue.

| Metric | Data |
|------|------|
| GitHub | [motiondivision/motion](https://github.com/motiondivision/motion) |
| Stars | ~27,000 |
| License | MIT |
| Language | TypeScript |
| Latest | v3.x (Motion 3) |
| Maintainer | Matt Perry (Motion Division) |
| Frameworks | React, JavaScript (vanilla), Vue |

> **Note**: This is the rebranded successor to Framer Motion. The repo `motiondivision/motion` is the same codebase, now independent from Framer. Supersedes the `framer-motion.md` analysis in this repo.

## TEMC Scores

| Dimension | Score | Reasoning |
|------|------|------|
| T (Tech) | 88 | Spring physics, layout animations, gesture support, AnimatePresence for exit animations, variants for orchestration, scroll-triggered animations. Motion 3: centralized animation state priority. Hardware-accelerated. |
| E (Ecosystem) | 85 | 27k stars. Most popular React animation library. Now independent = faster iteration. Powers Framer (design tool). Used by major companies. npm: millions of weekly downloads. |
| M (Market) | 82 | De facto React animation standard. Now expanding to vanilla JS and Vue. Motion 3 rebranding = broader reach beyond React. Competes with GSAP (industry standard for complex animations). |
| C (Combo) | 88 | **Perfect stack fit**: Next.js + Tailwind + Motion = complete UI layer. shadcn/ui components often use Motion for animations. Essential for landing pages, onboarding flows, micro-interactions. |
| **Overall** | **85.8** | T×0.25 + E×0.20 + M×0.25 + C×0.25 = 22.0+17.0+20.5+22.0 |

## Core Value

- **Declarative**: `<motion.div animate= x: 100  />` — animation as props
- **Spring physics**: Real spring animations, not bezier curves
- **Layout animations**: Automatic FLIP animations with `layout` prop
- **Gestures**: Drag, hover, tap, focus, viewport detection
- **Exit animations**: `AnimatePresence` for mount/unmount transitions
- **Variants**: Orchestrate animations across component trees
- **Scroll**: Scroll-triggered and scroll-linked animations
- **Framework-expanding**: Now React + vanilla JS + Vue

```tsx
import { motion, AnimatePresence } from "motion/react";

function Card({ isVisible }) {
  return (
    <AnimatePresence>
      {isVisible && (
        <motion.div
          initial= opacity: 0, y: 20 
          animate= opacity: 1, y: 0 
          exit= opacity: 0, y: -20 
          whileHover= scale: 1.05 
          transition= type: "spring", stiffness: 300 
          className="rounded-lg bg-white p-6 shadow-lg"
        >
          <h2>Animated Card</h2>
        </motion.div>
      )}
    </AnimatePresence>
  );
}
```

## Key Changes: Framer Motion → Motion

| Aspect | Framer Motion | Motion |
|--------|--------------|--------|
| Package | `framer-motion` | `motion` |
| Import | `from "framer-motion"` | `from "motion/react"` |
| Owner | Framer | Motion Division (independent) |
| Scope | React only | React + JS + Vue |
| Version | v11 → | v3 (reset) |
| Development | Tied to Framer's priorities | Independent, community-driven |

## Motion vs GSAP

| Feature | Motion | GSAP |
|---------|--------|------|
| React integration | ✅ Native | ⚠️ Wrapper needed |
| Declarative | ✅ Props-based | ❌ Imperative |
| Spring physics | ✅ Built-in | ⚠️ Plugin |
| Layout animations | ✅ Automatic | ❌ Manual |
| Complex timelines | ⚠️ Basic | ✅ Industry best |
| ScrollTrigger | ✅ Good | ✅ Best-in-class |
| License | MIT | Custom (free for most) |
| Bundle | ~16kb | ~24kb (core) |

## Risks

- Rebranding may cause temporary confusion (framer-motion → motion)
- GSAP still superior for complex timeline animations
- Bundle size (~16kb) not trivial for performance-sensitive sites
- Independent from Framer = less corporate backing, but more freedom

## Solo Dev Verdict

React动画的事实标准，现在独立后更强。天子的SaaS项目必备：Landing Page微交互、页面过渡、列表动画、模态框进出。shadcn/ui很多组件背后就是Motion。从`framer-motion`迁移到`motion`只需改import路径。现在还支持Vue和原生JS，一套动画技能多处复用。**基准栈必装项。**
