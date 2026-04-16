# Headless UI

> Completely unstyled, fully accessible UI components, designed to integrate beautifully with Tailwind CSS.

| Metric | Data |
|------|------|
| GitHub | [tailwindlabs/headlessui](https://github.com/tailwindlabs/headlessui) |
| Stars | ~28,300 |
| License | MIT |
| Language | TypeScript |
| Latest | v2.2.9 (React) |
| Maintainer | Tailwind Labs |
| Frameworks | React, Vue |

## TEMC Scores

| Dimension | Score | Reasoning |
|------|------|------|
| T (Tech) | 85 | Full WAI-ARIA accessibility out of the box. v2.0: built-in anchor positioning, combobox virtualization, HTML form components, improved hover/focus/active detection. Tailwind v4 support. |
| E (Ecosystem) | 82 | 28k stars. By Tailwind Labs = same team as Tailwind CSS. Powers Catalyst UI kit. React + Vue support. Used by Tailwind UI (paid component library). |
| M (Market) | 80 | Standard choice for accessible Tailwind components. Catalyst extends it for enterprise. Fewer components than Radix but deeper Tailwind integration. |
| C (Combo) | 90 | **Perfect stack fit**: Headless UI + Tailwind CSS = accessible unstyled components with utility styling. Alternative/complement to Radix UI (which shadcn/ui uses). Direct Tailwind Labs lineage. |
| **Overall** | **84.3** | T×0.25 + E×0.20 + M×0.25 + C×0.25 = 21.25+16.4+20.0+22.5 |

## Core Value

- **Fully accessible**: WAI-ARIA compliant out of the box
- **Completely unstyled**: Zero visual opinions, style with Tailwind
- **Tailwind-native**: Built by Tailwind Labs, designed for Tailwind CSS
- **Render props**: Full control over rendering and styling
- **v2.0 features**: Anchor positioning, checkbox, form components, combobox virtualization
- **React + Vue**: Official support for both frameworks

```tsx
import { Menu, MenuButton, MenuItems, MenuItem } from '@headlessui/react';

function MyDropdown() {
  return (
    <Menu>
      <MenuButton className="rounded bg-black/20 px-4 py-2 text-sm text-white">
        Options
      </MenuButton>
      <MenuItems anchor="bottom" className="w-52 rounded bg-white shadow-lg">
        <MenuItem>
          <a className="block px-4 py-2 data-[focus]:bg-blue-100" href="/edit">
            Edit
          </a>
        </MenuItem>
        <MenuItem>
          <a className="block px-4 py-2 data-[focus]:bg-blue-100" href="/delete">
            Delete
          </a>
        </MenuItem>
      </MenuItems>
    </Menu>
  );
}
```

## Components (v2.x)

| Component | Description |
|-----------|-------------|
| Menu | Dropdown menu |
| Listbox | Custom select |
| Combobox | Autocomplete (with virtualization) |
| Dialog | Modal dialog |
| Disclosure | Collapsible sections |
| Popover | Floating panels |
| Radio Group | Radio buttons |
| Switch | Toggle switch |
| Tabs | Tab panels |
| Checkbox | Checkbox (v2.0 new) |
| Field/Input/Label | Form components (v2.0 new) |

## Headless UI vs Radix UI

| Feature | Headless UI | Radix UI |
|---------|------------|----------|
| Stars | 28k | 18.8k |
| Components | ~12 | ~30+ |
| Styling | Tailwind-native | Any CSS |
| Frameworks | React + Vue | React only |
| Used by | Catalyst, Tailwind UI | shadcn/ui |
| Accessibility | ✅ Full | ✅ Full |
| Animations | CSS transitions | Bring your own |

## Risks

- Fewer components than Radix UI (~12 vs ~30+)
- shadcn/ui chose Radix over Headless UI = ecosystem momentum favors Radix
- React + Vue only (no Svelte/Solid adapters)
- Tailwind Labs focus may shift to Catalyst (paid product)

## Solo Dev Verdict

如果你用Tailwind CSS（天子基准栈），Headless UI是最自然的无样式组件选择——同一个团队出品。但shadcn/ui选择了Radix作为底层，这意味着大多数天子的UI组件已经通过shadcn→Radix路径解决了。Headless UI的价值在于：①需要Vue支持时（Radix不支持Vue）②需要Catalyst企业级组件时 ③特定组件（如Combobox虚拟化）比Radix实现更好。建议：shadcn/ui为主，Headless UI作为补充。
