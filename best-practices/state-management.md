# State Management Best Practices

> When to use what — synthesized from Zustand, React Query, and Next.js Server Components.

## State Types Decision Tree

```
Server data (API responses)?  → React Query / SWR / Server Components
Form state?                   → React Hook Form + Zod
URL state?                    → nuqs / useSearchParams
Global client state?          → Zustand
Component-local state?        → useState / useReducer
Complex derived state?        → useMemo + selectors
```

## The Modern Stack

| State Type | Solution | Bundle |
|-----------|----------|--------|
| Server state | React Query / Server Components | ~12kb / 0kb |
| Client global | Zustand | ~1kb |
| Form state | React Hook Form + Zod | ~9kb |
| URL state | nuqs | ~2kb |
| Local state | React useState | 0kb |

**Total**: ~24kb for complete state management (vs Redux toolkit: ~40kb+)

## Zustand Patterns

### Basic Store
```typescript
const useStore = create<State>()((set) => ({
  user: null,
  setUser: (user) => set({ user }),
  logout: () => set({ user: null }),
}))
```

### With Persist Middleware
```typescript
const useStore = create(
  persist(
    (set) => ({ theme: 'light', toggleTheme: () => set((s) => ({ theme: s.theme === 'light' ? 'dark' : 'light' })) }),
    { name: 'app-settings' }
  )
)
```

### Selector Pattern (Performance)
```typescript
// ❌ Re-renders on ANY store change
const { user, theme } = useStore()

// ✅ Re-renders only when user changes
const user = useStore((s) => s.user)
```

## Key Principle

> **Server Components reduce the need for client state by 60-80%.**
> Most data in a Next.js app should be fetched in Server Components, not stored in client state.
