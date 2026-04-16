# Storybook

> The UI development workshop — build, test, and document components in isolation.

| Metric | Data |
|--------|------|
| GitHub | https://github.com/storybookjs/storybook |
| Stars | ~86,000 |
| License | MIT |
| Language | TypeScript |
| Last Updated | Active daily |
| Contributors | 2,000+ |
| npm Weekly | ~20M downloads |

## TEMC Score

| Dimension | Score | Weight | Weighted | Rationale |
|-----------|-------|--------|----------|-----------|
| **T** Technology | 85 | 25% | 21.25 | Component Story Format (CSF3), Vite-powered builder (Storybook 8), visual testing, interaction testing, accessibility testing built-in. Portable stories for unit testing. |
| **E** Ecosystem | 88 | 20% | 17.60 | 86k⭐, 2000+ contributors, 500+ addons. Used by GitHub, Airbnb, Mozilla, Microsoft. Framework support: React, Vue, Angular, Svelte, Web Components, React Native. |
| **M** Market | 75 | 30% | 22.50 | Standard tool for component-driven development in teams. Less critical for solo devs but invaluable for building component libraries and SaaS UI systems. Market mature. |
| **C** Combination | 78 | 25% | 19.50 | Works with shadcn/ui + Radix UI + Tailwind. Storybook 8 uses Vite natively. For天子: useful when building reusable component libraries for Micro SaaS products. Testing integration with Vitest. |
| **Total** | — | 100% | **80.9** | |

## Architecture Highlights

### Component Story Format (CSF3)
Declarative, portable story format:
```typescript
export const Primary: Story = {
  args: { variant: 'primary', children: 'Button' },
  play: async ({ canvasElement }) => {
    const canvas = within(canvasElement);
    await userEvent.click(canvas.getByRole('button'));
    await expect(canvas.getByRole('button')).toHaveFocus();
  },
};
```
Stories are: documentation + visual test + interaction test + accessibility test in one.

### Vite Builder (Storybook 8)
Storybook 8 migrated from Webpack to Vite. Results:
- 2-4x faster startup
- Near-instant HMR
- Shared config with app's Vite setup

### Testing Integration
- **Visual testing**: Chromatic (paid) or Percy for screenshot comparison
- **Interaction testing**: `play` functions with Testing Library
- **Accessibility**: a11y addon runs axe-core on every story
- **Portable stories**: Export stories as test fixtures for Vitest/Jest

```
storybookjs/storybook/
├── code/
│   ├── core/              # Core Storybook runtime
│   ├── builders/
│   │   ├── builder-vite/  # Vite builder (default)
│   │   └── builder-webpack5/
│   ├── renderers/
│   │   ├── react/         # React renderer
│   │   ├── vue3/          # Vue 3 renderer
│   │   └── svelte/        # Svelte renderer
│   ├── addons/
│   │   ├── actions/       # Log component actions
│   │   ├── controls/      # Dynamic prop editing
│   │   ├── docs/          # Auto-generated docs
│   │   ├── a11y/          # Accessibility testing
│   │   └── interactions/  # Interaction testing
│   └── presets/
│       └── react-vite/    # React + Vite preset
```

## Key Extractable Patterns

1. **Component Story Format** — Declarative component documentation (→ best-practices/)
2. **Interaction testing pattern** — `play` functions for automated UI tests (→ code-base/testing/)
3. **Addon architecture** — Plugin system for extensible dev tools (→ best-practices/)
4. **Design system workflow** — Build → Document → Test → Ship components (→ best-practices/)

## Competitive Comparison

| | Storybook | Ladle | Histoire | Docusaurus |
|---|---|---|---|---|
| Stars | 86k | 2.6k | 3.2k | 58k |
| Focus | Component workshop | React stories | Vue stories | Documentation |
| Frameworks | All major | React only | Vue only | React |
| Build Tool | Vite/Webpack | Vite | Vite | Webpack |
| Testing | Visual+Interaction+A11y | Basic | Basic | None |
| Addons | 500+ | Minimal | Minimal | Plugins |
| Enterprise | Chromatic (paid) | — | — | — |

## Solo Dev Verdict

**Storybook is the professional standard for building component systems.** For天子's Micro SaaS strategy, Storybook becomes valuable when: (1) building a shared UI component library across multiple products, (2) creating a design system for consistent branding, (3) testing UI components in isolation before integration. Not day-one priority, but essential as products mature. The CSF3 format doubles as documentation and tests — huge time savings for solo devs.

**Priority**: 🟢 Important for scaling — adopt when building shared component library.
