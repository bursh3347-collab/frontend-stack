# Frontend Component Architecture Best Practices

> Synthesized from shadcn/ui, Radix UI, Bulletproof React, and modern React patterns.

## 1. Component Hierarchy

```
Primitives (Radix UI)       → Accessible, unstyled building blocks
  ↓
Design System (shadcn/ui)   → Styled, themed components
  ↓
Feature Components          → Business logic + UI composition
  ↓
Page Components             → Layout + data fetching + feature assembly
```

## 2. Compound Component Pattern (from Radix UI)

```tsx
<Dialog>
  <Dialog.Trigger>Open</Dialog.Trigger>
  <Dialog.Content>
    <Dialog.Title>Title</Dialog.Title>
    <Dialog.Description>Description</Dialog.Description>
  </Dialog.Content>
</Dialog>
```

**Why**: Each sub-component has a single responsibility. Flexible composition without prop drilling.

## 3. Copy-Paste Over Package (shadcn philosophy)

**Traditional**: `npm install @ui-lib/button` → fight API, override styles
**shadcn way**: `npx shadcn-ui add button` → own the code, modify freely

**When to use each**:
- **Copy-paste (shadcn)**: When you need full control over styling and behavior
- **Package (npm)**: For utilities that don't need customization (date-fns, lodash)

## 4. Server vs Client Components (Next.js)

```
Server Components (default):
- Data fetching
- Static content
- Layout components
- Accessing backend resources

Client Components ('use client'):
- Interactivity (onClick, onChange)
- State (useState, useReducer)
- Effects (useEffect)
- Browser APIs
- Third-party client libs
```

**Rule**: Start with Server Components. Add 'use client' only when needed.

## 5. Styling Strategy

```
Tailwind CSS utility classes     → 90% of styling needs
  + CSS variables (shadcn theme) → Theming and dark mode
  + cn() utility (clsx+twMerge) → Conditional class merging
  + Framer Motion               → Animations
```

The `cn()` utility from shadcn:
```typescript
import { clsx, type ClassValue } from 'clsx'
import { twMerge } from 'tailwind-merge'

export function cn(...inputs: ClassValue[]) {
  return twMerge(clsx(inputs))
}
```
