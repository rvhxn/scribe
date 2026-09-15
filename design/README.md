# Scribe Design System

A modern, accessible design system for Scribe built on **Radix UI** primitives and **shadcn/ui** design patterns. It defines foundational design tokens, component specifications, and interaction patterns across Light and Dark themes.

The source canvas library is located at [`system/product-design-system.lib`](file:///C:/Users/Rohan/Documents/Antigravity/scribe/design/system/product-design-system.lib).

---

## 1. Design Tokens & Foundations

### 1.1 Color Tokens

#### Light Theme (Core Canvas & Chrome)
| Token | Value | Description |
| :--- | :--- | :--- |
| `$color.background` | `#FFFFFF` | Page canvas, elevated popover surfaces |
| `$color.surface` | `#F5F5F5` | Sidebar background, secondary containers |
| `$color.surface.hover` | `#EBEBEB` | Subtle hover state on surface items |
| `$color.surface.raised` | `#FFFFFF` | Elevated cards with border and drop shadow |
| `$color.text.primary` | `#1A1A1A` | Main headings, body prose, high-contrast labels |
| `$color.text.secondary` | `#6B6B6B` | Secondary copy, descriptions, captions |
| `$color.text.tertiary` | `#9E9E9E` | Disabled text, input placeholders |
| `$color.border` | `#E5E5E5` | Structural borders, card outlines |
| `$color.border.subtle` | `#F0F0F0` | Dividers, table row borders |
| `$color.border.focus` | `#CCCCCC` | Focus ring fallback |

#### Dark Theme (Night Mode & Floating HUDs)
| Token | Value | Description |
| :--- | :--- | :--- |
| `$color.dark.bg` | `#18181B` | Dark surface container, floating toolbars |
| `$color.dark.bg.hover` | `#27272A` | Interactive item hover state |
| `$color.dark.bg.selected` | `#3F3F46` | Active selection, selected table row |
| `$color.dark.text.primary` | `#FFFFFF` | Primary dark theme text, headings |
| `$color.dark.text.secondary` | `#A1A1AA` | Secondary dark theme copy, timestamps, icons |
| `$color.dark.border` | `#27272A` / `#3F3F46` | Dark surface borders and dividers |

#### Semantic & Feedback Colors
| Token | Light Value | Dark Value | Purpose |
| :--- | :--- | :--- | :--- |
| `$color.success` | `#166534` (on `#DCFCE7`) | `#4ADE80` (on `#064E3B`) | Published state, passes, confirmations |
| `$color.warning` | `#B45309` (on `#FEF3C7`) | `#FBBF24` (on `#1C1917`) | Unsaved changes, quota alerts |
| `$color.error` / Destructive | `#DC2626` (on `#FEE2E2`) | `#F87171` (on `#1F1315`) | Critical errors, destructive actions |
| `$color.info` | `#2563EB` (on `#EFF6FF`) | `#60A5FA` (on `#111827`) | Contextual information, sync status |
| `$color.ai.highlight` | `#C8F0E8` / `#312E81` | `#A5B4FC` | AI synthesis, diff review badges |

---

### 1.2 Typography

* **Font Family**: `Inter`, `-apple-system`, `BlinkMacSystemFont`, `"Segoe UI"`, `Roboto`, `sans-serif`
* **Scale**:

| Token | Size | Weight | Line Height | Usage |
| :--- | :--- | :--- | :--- | :--- |
| `$font.size.display` | `38px` | `700` | `1.15` | Hero display headings |
| `$font.size.page-title` | `30px` | `600` | `1.2` | Page greetings & main views |
| `$font.size.section` | `18px` | `600` | `1.3` | Section headings, panel titles |
| `$font.size.body-lg` | `17px` | `400` / `500` | `1.5` | Menu actions, large body copy |
| `$font.size.body` | `16px` | `400` | `1.6` | Editor body, narrative text |
| `$font.size.label` | `14px` | `500` / `600` | `1.4` | Form labels, table cells, button text |
| `$font.size.caption` | `13px` | `400` / `500` | `1.4` | Metadata, secondary labels |
| `$font.size.meta` | `12px` | `400` / `500` | `1.3` | Status tags, counters, timestamps |
| `$font.size.overline` | `11px` | `500` | `1.2` | Model selectors, category tags |

---

### 1.3 Spacing & Shape Geometry

* **Base Unit**: `4px`
* **Common Tokens**: `$spacing.xs` (`4px`), `$spacing.sm` (`8px`), `$spacing.md` (`12px`), `$spacing.lg` (`16px`), `$spacing.xl` (`24px`), `$spacing.2xl` (`32px`)
* **Radii**:
  * `$radius.sm` (`6px`): Status tags, micro-badges
  * `$radius.md` (`10–12px`): Input containers, cards, dropdown menus
  * `$radius.lg` (`16px`): Dialog modals, major feature containers
  * `$radius.xl` (`24px`): Floating toolbars, AI diff cards
  * `$radius.full` (`9999px`): Pill buttons, circular icon triggers, avatars

---

## 2. Component Primitives

All components align with Radix UI accessibility requirements and shadcn/ui visual tokens.

### 2.1 Buttons (`Button`)
* **Variants**:
  * `Primary`: Solid `#1A1A1A` fill, white text, pill or rounded shape.
  * `Secondary / Outline`: Transparent background, subtle `#E5E5E5` / `#3F3F46` border.
  * `Ghost`: Background-free, hover-fill only.
  * `AI Action`: Subtle teal/indigo highlight for AI-assisted commands.
  * `Destructive`: Solid red or red outline for permanent actions.
* **Sizes**: `LG` (44px), `MD` (36px), `SM` (28px), and circular Icon triggers.

### 2.2 Toolbars, Popovers & Menus
* **Floating Pill Toolbar**: Format controls (H1, Bold, Italic, List, Quote) + AI actions (Instruct, Polish, Deepen, Enhance).
* **Dropdown Menus**: Radix DropdownMenu primitive in Light and Dark themes, supporting nested sub-menus, keyboard shortcut hints, and metadata footers.
* **Action Popover**: Compact inline resolution popover (`Accept`, `Revise`, `Dismiss` + `esc to dismiss`).

### 2.3 Prompt & Chat Inputs
* **Agent Chat Input**: Multiline prompt container featuring bottom model selector (`GPT-5.4 Nano Medium`, `Claude 4.5 Haiku`), attach trigger, and send button.
* **Inline Floating Bar**: Streamlined prompt input anchored to active text selection.

### 2.4 Sidebar Navigation
* **Modes**:
  * `Expanded` (240px width): Workspace switcher, folder structure with expandable trees, "Create New Folder" action, and bottom user tier badge.
  * `Collapsed Rail` (64px width): Icon-only compact rail with tooltips.
* **User Badges**: Starter and Pro plan indicators with clean avatar badges.

### 2.5 Data Tables
* **Shadcn Primitives**: `Table`, `TableHeader`, `TableRow`, `TableHead`, `TableCell`, `TableFooter`.
* **Features**: Sortable headers, high-contrast semantic status tags (`Published`, `Draft`, `Review`, `Archived`), word count metrics, and pagination controls.
* **Theming**: Fully calibrated for both Light and Dark backgrounds with WCAG AAA compliant text contrast.

### 2.6 Modals & Dialogs
* **Standard Dialog**: Header, form body, and footer actions for document creation and project settings.
* **AlertDialog**: Semantic warning modal for destructive actions (e.g. permanent deletion).

### 2.7 Inputs & Form Elements
* **Inputs**: Standard text input, leading icon search bar, URL prefix field (`scribe.app/p/`), select dropdown, and multiline textarea.
* **Forms**: Radix Checkbox, RadioGroup, Switch, and Slider primitives across Light and Dark themes.

### 2.8 Feedback, Alerts & System States
* **Alerts**: Contextual banners for Info, Warning, and Destructive system notices with semantic tinted surfaces.
* **Toasts**: Non-intrusive action feedback with undo triggers (Sonner-style).
* **AI Generation Card**: Multi-step generation overlay with animated progress indicator and live checklist.
* **Empty States**: Zero-data screens with icon graphics and primary call-to-action buttons.

---

## 3. Design Principles

1. **Monochrome Dominance**: Content and writing take center stage. Chrome stays unobtrusive using grays (`#FFFFFF`, `#F5F5F5`, `#18181B`, `#27272A`).
2. **Semantic Restraint**: Color is strictly reserved for status communication, quality checks, and AI highlights.
3. **Contrast & Readability**: All text pairings guarantee strong contrast ratios against their respective backgrounds in both Light and Dark themes.
4. **Fluid Responsiveness**: Layout elements adapt cleanly across sidebar states and variable editor widths (`680px–720px` optimal reading measure).
