# Tailwind CSS

> A utility-first CSS framework for rapidly building custom user interfaces.

| Metric | Data |
|------|------|
| GitHub | [tailwindlabs/tailwindcss](https://github.com/tailwindlabs/tailwindcss) |
| Stars | 94,583 |
| License | MIT |
| Language | TypeScript (v4) |
| Maintainer | Tailwind Labs (Adam Wathan) |

## TEMC Scores

| Dimension | Score | Reasoning |
|------|------|------|
| T (Tech) | 94 | Utility-first paradigm that won the CSS war. v4 rewritten in Rust (Lightning CSS). JIT compiler. CSS-first configuration in v4. |
| E (Ecosystem) | 95 | 95k stars. Used by virtually every modern frontend project. Tailwind UI, Headless UI, shadcn/ui all built on it. |
| M (Market) | 95 | De facto standard for modern CSS. Required skill for frontend developers. |
| C (Combo) | 98 | **Core of base tech stack**. shadcn/ui depends on it. Every project uses it. |
| **Overall** | **95.6** | |

## Core Value

- **Utility-first**: `className="flex items-center gap-4 p-4"` — no CSS files
- **Design tokens**: Consistent spacing, colors, typography via config
- **JIT mode**: Only generates CSS you actually use
- **Dark mode**: Built-in dark mode support
- **v4**: Rewritten in Rust, CSS-first config, native cascade layers
- **Responsive**: Mobile-first breakpoints (`sm:`, `md:`, `lg:`)

## Risks

- Long className strings (mitigated by component abstraction)
- Learning curve for traditional CSS developers
- v3 → v4 migration requires effort

## 天子点评

基准栈核心，v4 Rust重写后性能飞升。和shadcn/ui深度绑定，必选无悬念。一人公司写CSS最快的方式——不用起名字、不用切文件、不用管作用域。className写完就是成品。
