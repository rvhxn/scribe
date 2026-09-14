# Scribe Design System

> Reverse-engineered from product screenshots of **Feldar** — an AI-powered writing assistant.
> This specification captures every visual token, component, and interaction pattern observed across 17 screenshots.

---

## Table of Contents

1. [Color System](#1-color-system)
2. [Typography](#2-typography)
3. [Spacing](#3-spacing)
4. [Shape Language](#4-shape-language)
5. [Layout](#5-layout)
6. [Components](#6-components)
7. [Icons & Imagery](#7-icons--imagery)
8. [Patterns](#8-patterns)

---

## 1. Color System

The application uses a **dual-theme** architecture: a light theme for the main writing canvas/chrome and a dark theme exclusively for floating toolbars, menus, and contextual popovers.

### 1.1 Light Theme (Primary)

| Token                    | Value (approx.)  | Usage                                              |
| ------------------------ | ---------------- | -------------------------------------------------- |
| `--bg-page`              | `#FFFFFF`        | Main canvas / writing area background              |
| `--bg-surface`           | `#F5F5F5`        | Sidebar background, onboarding card fills           |
| `--bg-surface-hover`     | `#EBEBEB`        | Hovered selection cards (onboarding)                |
| `--bg-surface-raised`    | `#FFFFFF`        | Project cards, elevated surfaces (with shadow)      |
| `--bg-muted`             | `#F7F7F7`        | Loading state skeleton background, progress tracks  |
| `--text-primary`         | `#1A1A1A`        | Headings, body text, primary labels                 |
| `--text-secondary`       | `#6B6B6B`        | Subtitles, descriptions, muted body text            |
| `--text-tertiary`        | `#9E9E9E`        | Placeholder text, disabled text, captions           |
| `--text-link`            | `#1A1A1A`        | Links (no underline, weight-differentiated)         |
| `--border-default`       | `#E5E5E5`        | Card borders, input borders                         |
| `--border-subtle`        | `#F0F0F0`        | Dividers within cards, between list items            |
| `--border-focus`         | `#CCCCCC`        | Focused input border                                |

### 1.2 Dark Theme (Floating UI Only)

| Token                    | Value (approx.)  | Usage                                              |
| ------------------------ | ---------------- | -------------------------------------------------- |
| `--dark-bg-solid`        | `#2A2A2A`        | Floating toolbar, dropdown menus, action popover    |
| `--dark-bg-hover`        | `#3A3A3A`        | Hovered menu items (e.g. "Longer" in revise menu)   |
| `--dark-bg-selected`     | `rgba(255,255,255,0.12)` | Selected/active items (e.g. "Polish" highlight) |
| `--dark-text-primary`    | `#FFFFFF`        | Menu item labels, toolbar labels                    |
| `--dark-text-secondary`  | `#999999`        | Muted labels (e.g. "Back" in revise menu)           |
| `--dark-border`          | `rgba(255,255,255,0.10)` | Dividers between menu sections             |

### 1.3 Semantic Colors

| Token                    | Value (approx.)  | Usage                                              |
| ------------------------ | ---------------- | -------------------------------------------------- |
| `--color-error`          | `#E84040`        | Red dot — "Fix critical mistakes" (checks panel)    |
| `--color-info`           | `#4A90D9`        | Blue dot — "Improve accuracy and clarity"           |
| `--color-success`        | `#2E9E6E`        | Teal/green dot — "Tighten word choice" and below    |
| `--color-success-alt`    | `#34A77A`        | Slightly brighter teal for lower-severity checks    |
| `--color-ai-highlight`   | `#C8F0E8`        | Light cyan/teal highlight for AI-generated text diffs |

### 1.4 Button Colors

| Token                    | Value (approx.)  | Usage                                              |
| ------------------------ | ---------------- | -------------------------------------------------- |
| `--btn-primary-bg`       | `#1A1A1A`        | "Continue" button, "Accept" button fill             |
| `--btn-primary-text`     | `#FFFFFF`        | Text on primary buttons                            |
| `--btn-secondary-bg`     | `transparent`    | "Discard" button, "Upgrade" button                  |
| `--btn-secondary-border` | `#D0D0D0`        | Outlined button border                             |
| `--btn-secondary-text`   | `#1A1A1A`        | Text on secondary buttons                          |
| `--btn-icon-bg`          | `#F5F5F5`        | Circular icon button background (e.g. send arrow)   |
| `--btn-icon-bg-dark`     | `#1A1A1A`        | Dark variant icon button (send arrow in chat)        |

### 1.5 Progress Bar Colors

| Token                    | Value (approx.)  | Usage                                              |
| ------------------------ | ---------------- | -------------------------------------------------- |
| `--progress-track`       | `#E0E0E0`        | Progress bar track (checks panel "Writing quality") |
| `--progress-fill`        | `#D0D0D0`        | Progress bar fill (loading/indeterminate state)     |

---

## 2. Typography

The application uses a clean sans-serif typeface throughout, consistent with the system font or a geometric sans like **Inter** or **SF Pro**.

### 2.1 Font Family

| Token             | Value                                                     |
| ----------------- | --------------------------------------------------------- |
| `--font-sans`     | `"Inter", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif` |
| `--font-serif`    | `Georgia, "Times New Roman", serif` (for prose/editor content, if toggled) |
| `--font-mono`     | `"SF Mono", "Fira Code", monospace` (not observed but reserve) |

### 2.2 Type Scale

| Token              | Size (px) | Size (rem) | Weight | Line Height | Usage                                       |
| ------------------- | --------- | ---------- | ------ | ----------- | ------------------------------------------- |
| `--text-display`    | 36–40     | 2.25–2.5   | 700    | 1.1         | Onboarding heading ("What is your main…")   |
| `--text-page-title` | 28–32     | 1.75–2.0   | 600    | 1.2         | Page greeting ("Hello, night owl")          |
| `--text-section`    | 18–20     | 1.125–1.25 | 600    | 1.3         | Section headings ("Start writing", "Checks")|
| `--text-body`       | 16        | 1.0        | 400    | 1.6         | Editor body text, prose content              |
| `--text-body-lg`    | 17–18     | 1.0625–1.125 | 400  | 1.5         | Menu item labels (dark menus)               |
| `--text-label`      | 14        | 0.875      | 500    | 1.4         | Card titles ("New project"), nav items       |
| `--text-caption`    | 13        | 0.8125     | 400    | 1.4         | Subtitles, descriptions, metadata            |
| `--text-meta`       | 12        | 0.75       | 400    | 1.3         | Word count, "Last edited by", timestamps     |
| `--text-overline`   | 11        | 0.6875     | 500    | 1.2         | Model selector labels ("GPT-5.4 Nano")      |

### 2.3 Font Weights

| Token            | Value | Usage                                       |
| ---------------- | ----- | ------------------------------------------- |
| `--weight-regular`  | 400   | Body text, descriptions, captions          |
| `--weight-medium`   | 500   | Labels, nav items, card titles             |
| `--weight-semibold` | 600   | Section headings, active states            |
| `--weight-bold`     | 700   | Display headings, strong emphasis          |

### 2.4 Letter Spacing

| Token                    | Value     | Usage                                    |
| ------------------------ | --------- | ---------------------------------------- |
| `--tracking-tight`       | `-0.02em` | Display/page titles                      |
| `--tracking-normal`      | `0`       | Body text, labels                        |
| `--tracking-wide`        | `0.01em`  | Overline/meta text                       |

---

## 3. Spacing

The application uses a **4px base unit** spacing system.

### 3.1 Spacing Scale

| Token     | Value  | Usage                                                      |
| --------- | ------ | ---------------------------------------------------------- |
| `--sp-1`  | 4px    | Inline icon gaps, tight spacing                            |
| `--sp-2`  | 8px    | Icon-to-label gap in menu items, tight padding             |
| `--sp-3`  | 12px   | Internal card padding (compact), list item padding          |
| `--sp-4`  | 16px   | Standard component padding, input padding, card padding     |
| `--sp-5`  | 20px   | Section gaps, vertical rhythm between small sections        |
| `--sp-6`  | 24px   | Card internal padding (comfortable), sidebar padding        |
| `--sp-8`  | 32px   | Section spacing, gap between heading and content            |
| `--sp-10` | 40px   | Major section breaks                                       |
| `--sp-12` | 48px   | Page top padding, large vertical gaps                       |
| `--sp-16` | 64px   | Page margins (horizontal), onboarding card vertical spacing |

### 3.2 Page Layout Spacing

| Token                     | Value     | Usage                                      |
| ------------------------- | --------- | ------------------------------------------ |
| `--page-margin-x`         | 48–64px   | Horizontal page margins on main content    |
| `--page-margin-top`       | 32–48px   | Top spacing of main content area           |
| `--sidebar-padding-x`     | 12–16px   | Sidebar internal horizontal padding        |
| `--sidebar-padding-y`     | 12px      | Sidebar internal vertical padding          |
| `--editor-max-width`      | 680–720px | Maximum width of the writing/editor area   |
| `--onboarding-max-width`  | 560–600px | Maximum width of onboarding card stack     |

### 3.3 Component Gaps

| Token                     | Value     | Usage                                      |
| ------------------------- | --------- | ------------------------------------------ |
| `--gap-menu-items`        | 0         | Menu items are flush (dividers only)       |
| `--gap-card-stack`        | 12–16px   | Vertical gap between onboarding cards      |
| `--gap-check-items`       | 0         | Check list items flush (dividers separate) |
| `--gap-suggestion-items`  | 0         | AI suggestion list items (dividers)        |
| `--gap-toolbar-items`     | 8–12px    | Horizontal gap between toolbar buttons     |

---

## 4. Shape Language

The visual language is **soft and rounded**, with generous border radii and minimal hard edges.

### 4.1 Border Radii

| Token              | Value    | Usage                                             |
| ------------------- | -------- | ------------------------------------------------- |
| `--radius-none`     | 0        | —                                                 |
| `--radius-sm`       | 6px      | Small badges, inline elements                     |
| `--radius-md`       | 10–12px  | Cards, input fields, menu containers              |
| `--radius-lg`       | 16px     | Onboarding selection cards, large cards            |
| `--radius-xl`       | 20–24px  | Floating toolbar, popup containers, chat input     |
| `--radius-full`     | 9999px   | Pill buttons ("Continue"), icon buttons, avatars   |

### 4.2 Border Widths

| Token               | Value | Usage                                              |
| -------------------- | ----- | -------------------------------------------------- |
| `--border-thin`      | 1px   | Standard card borders, input borders, dividers     |
| `--border-none`      | 0     | Menus/dropdowns rely on shadow, not border         |

### 4.3 Shadows

| Token                  | Value                                    | Usage                                       |
| ----------------------- | ---------------------------------------- | ------------------------------------------- |
| `--shadow-sm`           | `0 1px 2px rgba(0,0,0,0.05)`           | Subtle card elevation (project card)         |
| `--shadow-md`           | `0 4px 12px rgba(0,0,0,0.08)`          | Floating chat input, checks panel            |
| `--shadow-lg`           | `0 8px 24px rgba(0,0,0,0.12)`          | Dropdown menus, floating toolbar, popovers   |
| `--shadow-xl`           | `0 12px 40px rgba(0,0,0,0.16)`         | Loading/generation overlay card              |
| `--shadow-dark-popup`   | `0 8px 30px rgba(0,0,0,0.4)`           | Dark theme popover (toolbar, revise menu)    |

### 4.4 Elevation Layers

| Level | Shadow Token    | z-index | Examples                                    |
| ----- | --------------- | ------- | ------------------------------------------- |
| 0     | none            | 0       | Page background                             |
| 1     | `--shadow-sm`   | 1       | Cards, sidebar                              |
| 2     | `--shadow-md`   | 10      | Chat input, checks panel                    |
| 3     | `--shadow-lg`   | 100     | Dropdown menus, context menus               |
| 4     | `--shadow-xl`   | 200     | Modals, generation overlay                  |
| 5     | `--shadow-dark-popup` | 300 | Floating toolbar (always on top)          |

---

## 5. Layout

### 5.1 Application Shell

```
┌───────────────────────────────────────────────┐
│ ● ● ● [sidebar toggle]                       │ ← Window chrome (macOS)
├──────────┬────────────────────────────────────┤
│          │                                    │
│ Sidebar  │         Main Content Area          │
│ ~240px   │     (centered, max-width ~720px)   │
│          │                                    │
│          │                                    │
│          ├────────────────────────────────────┤
│          │   [Floating elements anchored to   │
│          │    bottom of viewport]              │
├──────────┴────────────────────────────────────┤
│ [User] [Plan] [Upgrade]                       │ ← Sidebar footer
└───────────────────────────────────────────────┘
```

### 5.2 Sidebar

| Property              | Value              |
| --------------------- | ------------------ |
| Width                 | ~240px             |
| Background            | `--bg-surface` (#F5F5F5) |
| Padding               | 12–16px            |
| Collapse behavior     | Toggle button (⊞ icon, top-left) |
| Nav items             | Stacked vertically, icon + label |
| Footer                | User avatar (letter) + name + plan label + "Upgrade" button |

### 5.3 Main Content Area

| Property              | Value              |
| --------------------- | ------------------ |
| Background            | `--bg-page` (#FFFFFF) |
| Max width             | 680–720px          |
| Centering             | Horizontally centered within remaining space |
| Top padding           | ~48px              |

### 5.4 Editor View

| Property              | Value              |
| --------------------- | ------------------ |
| Content max-width     | ~680px             |
| Line length           | ~70–80 characters  |
| Paragraph spacing     | ~1.6em             |

### 5.5 Onboarding Layout

| Property              | Value              |
| --------------------- | ------------------ |
| Centered              | Both axes, full-page |
| Max width             | ~560px             |
| Card stack direction  | Vertical           |
| Card gap              | ~12–16px           |

### 5.6 Responsive Behavior (Inferred)

- Sidebar collapses to a hidden drawer on narrow viewports (toggle button present)
- Editor content area shrinks with viewport but maintains comfortable reading width
- Floating toolbar likely repositions or stacks on mobile
- Onboarding view is single-column, works naturally on mobile

---

## 6. Components

### 6.1 Buttons

#### Primary Button
- Background: `--btn-primary-bg` (near-black)
- Text: `--btn-primary-text` (white)
- Border radius: `--radius-full` (pill shape)
- Padding: 12px 32px (generous horizontal padding)
- Font: `--text-label` weight `--weight-medium`
- Full-width variant used in onboarding ("Continue")
- Inline variant used in AI results ("Accept")

#### Secondary / Outline Button
- Background: transparent
- Border: 1px solid `--btn-secondary-border`
- Text: `--btn-secondary-text`
- Border radius: `--radius-full`
- Padding: 6px 16px
- Used for: "Upgrade", "Discard"

#### Icon Button
- Shape: Circle
- Size: 32–36px diameter
- Background: `--bg-muted` or `--btn-icon-bg-dark`
- Icon: centered, 16–20px
- Used for: Send (↑ arrow), plus (+), search (🔍), more (⋯)

#### Toolbar Button (Dark)
- Background: transparent or `--dark-bg-hover` on hover
- Text: white
- Icon + label layout
- Used in floating toolbar: Polish, Deepen, Enhance

### 6.2 Inputs

#### Chat / Prompt Input
- Background: `--bg-page` (white)
- Border: 1px solid `--border-default`
- Border radius: `--radius-xl` (~20–24px, pill-like)
- Padding: 12–16px
- Placeholder: `--text-tertiary`
- Contains model selector (bottom-left), action buttons (bottom-right)
- Shadow: `--shadow-md`

#### Inline Instruction Input
- Background: `--bg-page`
- Border: 1px solid `--border-default`
- Border radius: `--radius-lg`
- Simpler variant with just text + send button
- Used for "How should Feldar edit" prompt

### 6.3 Selection Cards (Radio-like)

- Background: `--bg-surface`
- Border: none (background differentiation)
- Border radius: `--radius-lg` (~16px)
- Padding: 16–20px
- Content: Bold title + muted description
- Selection indicator: Left-side dot/circle (subtle)
- Hover: `--bg-surface-hover`
- Used in onboarding flow for writing style selection

### 6.4 Navigation Items (Sidebar)

- Layout: Icon (20px) + Label
- Padding: 8–10px horizontal, 6–8px vertical
- Font: `--text-label`, `--weight-medium`
- Active state: likely bold weight or background highlight
- Items: "Library" (cloud icon), "New project" (pen icon)

### 6.5 Dropdown Menus (Dark)

#### Standard Menu
- Background: `--dark-bg-solid`
- Border radius: `--radius-md` (~12px)
- Shadow: `--shadow-dark-popup`
- Items: Icon + Label, stacked vertically
- Item padding: 12–16px horizontal, 10–12px vertical
- Dividers: `--dark-border` (subtle white-alpha line)
- Hover: `--dark-bg-hover`
- Footer section: Muted metadata text (`--dark-text-secondary`)

#### Nested/Sub-menu
- Same styling as parent menu
- Appears to the right of parent
- Connected visually (no gap or slight overlap)
- Items: Text-only (no icons in sub-menus)

### 6.6 Context Menu / More Menu

- Triggered by "⋯" button
- Items observed: Share, Duplicate, Move to Trash, Appearance, Minimal Mode
- Grouped sections separated by dividers
- Footer metadata: Word count, last edited by, timestamp
- White/light background variant with subtle border
- Border radius: `--radius-md`

### 6.7 Floating Toolbar (Text Selection)

#### Top Row (Formatting)
- Background: `--dark-bg-solid`
- Border radius: `--radius-xl`
- Icons: H1, B, I, U, S (strikethrough)
- Second row: Quote (❝), Align (⇅), Highlight (✎), List (≡), Page (📄)
- Divider between formatting and AI actions

#### Bottom Section (AI Actions)
- Items: Instruct, Polish, Deepen, Enhance
- Each has a distinct icon
- Hover: `--dark-bg-selected` or `--dark-bg-hover`
- Expands to sub-menu on hover/click (flyout to the right)

### 6.8 Checks Panel (Sidebar Panel)

- Background: `--bg-surface` (light gray)
- Border radius: `--radius-md`
- Shadow: `--shadow-md`
- Header: "Checks" title
- Score display: "Writing quality" + "--/100"
- Progress bar: Horizontal, full-width, with track and fill
- Check items: Colored dot (semantic) + label text
- Dividers between items
- Collapsible via button (top-right sparkle/wand icon)

### 6.9 AI Result / Diff Card

- Background: `--bg-page`
- Border: 1px solid `--border-default`
- Border radius: `--radius-md`
- Header: Action label ("Add Interiority") + utility icons (copy, retry)
- Body: Mixed text — original in black, AI-added in `--color-ai-highlight` (teal highlight)
- Footer: "Discard" (secondary) + "Accept" (primary) buttons, right-aligned
- Shadow: `--shadow-sm`

### 6.10 Loading / Generation State

- Centered card over dimmed/blurred content
- Background: `--bg-page` (white)
- Border radius: `--radius-lg`
- Shadow: `--shadow-xl`
- Content:
  - Header icon (sparkle/AI icon) + title ("Generating scenes")
  - Step list with status indicators:
    - Active step: Spinner icon + bold text
    - Pending steps: Faded dot + `--text-tertiary` text
- Behind the card: Content shown as skeleton/blurred placeholder lines

### 6.11 AI Suggestion List

- Below the chat input
- Items: Sparkle icon (✨) + suggestion text
- Dividers between items
- No background (flush with page)
- Font: `--text-body`, `--weight-regular`
- Examples: "Suggest a twist…", "Find weak spots…", "Suggest ways to improve…"

### 6.12 Model Selector

- Location: Bottom-left of chat input
- Display: Model name ("GPT-5.4 Nano" / "Claude 4.5 Haiku") + quality label ("Medium")
- Chevron dropdown indicator
- Font: `--text-overline`, `--weight-medium`
- Text color: `--text-secondary`

### 6.13 Avatar / User Badge

- Shape: Circle
- Size: ~28px
- Background: light gray
- Content: Single letter (initial), centered
- Font: `--text-meta`, `--weight-medium`
- Located in sidebar footer

### 6.14 Status Bar (Editor Header)

- Position: Top of editor view
- Content: Status ("Running checks") + word count ("1269 words")
- Separator: Thin vertical pipe `|`
- Action icons: Document, Search, More (⋯)
- Font: `--text-meta`
- Text color: `--text-secondary`

### 6.15 Action Popover (Accept/Revise/Dismiss)

- Background: `--dark-bg-solid`
- Border radius: `--radius-md`
- Items: Icon + label (✓ Accept, ↺ Revise, ✕ Dismiss)
- Footer hint: "esc to dismiss" in muted text
- Compact, 3-item menu
- Shadow: `--shadow-dark-popup`

### 6.16 Revision Options Menu

- Background: `--dark-bg-solid`
- Border radius: `--radius-md`
- Long list of options: Try again, Longer, Shorter, More interiority, etc.
- Hover highlight: `--dark-bg-hover` (e.g. "Longer" highlighted)
- Footer: "Back" link in `--dark-text-secondary`
- Divider above footer
- Shadow: `--shadow-dark-popup`

### 6.17 Bottom Toolbar (Inline, Compact)

- Horizontal layout with icon + label items
- Background: `--dark-bg-solid`
- Border radius: `--radius-full` (pill shape)
- Observed items: Chat icon, ✨ Polish, 🔍 Deepen, 🔗 Enhance, ⚙️ Settings
- Separators: Thin vertical divider between groups
- Sticky to bottom of viewport

---

## 7. Icons & Imagery

### 7.1 Icon Style

| Property        | Value                                           |
| --------------- | ----------------------------------------------- |
| Style           | Outlined / stroke-based (not filled)            |
| Stroke width    | 1.5–2px                                         |
| Size (standard) | 20px                                            |
| Size (toolbar)  | 18px                                            |
| Size (compact)  | 16px                                            |
| Color (light)   | `--text-primary` (#1A1A1A)                      |
| Color (dark UI) | `--dark-text-primary` (#FFFFFF)                 |
| Color (muted)   | `--text-tertiary` (#9E9E9E)                     |

### 7.2 Icon Inventory

| Icon             | Visual Description              | Usage                          |
| ---------------- | ------------------------------- | ------------------------------ |
| Cloud/Library    | Rounded cloud outline           | Sidebar — "Library"            |
| Pen/Edit         | Angled pen nib                  | Sidebar — "New project"        |
| Plus (+)         | Simple cross                    | New project card, add button   |
| Search (🔍)      | Magnifying glass                | Editor header, toolbar         |
| More (⋯)         | Three horizontal dots           | Context menu trigger           |
| Document (📄)    | Page with folded corner         | Editor header, copy action     |
| Share (↑)        | Arrow pointing up from box      | Context menu — "Share"         |
| Duplicate        | Stacked rectangles              | Context menu — "Duplicate"     |
| Trash            | Trash can outline               | Context menu — "Move to Trash" |
| Appearance       | Pen with sparkle                | Context menu — "Appearance"    |
| Minimal Mode     | Wavy/zigzag line                | Context menu — "Minimal Mode"  |
| H1               | "H₁" text glyph                | Toolbar — heading toggle       |
| Bold (B)         | Bold "B"                        | Toolbar — bold                 |
| Italic (I)       | Italic "I"                      | Toolbar — italic               |
| Underline (U)    | Underlined "U"                  | Toolbar — underline            |
| Strikethrough (S)| "S" with horizontal line        | Toolbar — strikethrough        |
| Block quote (❝)  | Large quotation marks           | Toolbar — block quote          |
| Align (⇅)        | Up/down arrows or text align    | Toolbar — alignment            |
| Highlight (✎)    | Pen/highlighter                 | Toolbar — highlight text       |
| List (≡)         | Horizontal lines                | Toolbar — list toggle          |
| Chat bubble (💬) | Speech bubble outline           | Instruct action, toolbar       |
| Sparkle (✨)     | Star/sparkle burst              | Polish, AI suggestions, AI icon|
| Magnify-text (🔍)| Magnifier with lines            | Deepen action                  |
| Link/chain (🔗)  | Interlinked circles             | Enhance action                 |
| Settings (⚙️)    | Gear outline                    | Toolbar settings               |
| Checkmark (✓)    | Simple check                    | Accept action                  |
| Refresh (↺)      | Circular arrow                  | Revise action, retry           |
| Close (✕)        | Simple X                        | Dismiss action                 |
| Chevron (⌄)      | Small down arrow                | Model selector dropdown        |
| Send (↑)         | Up arrow in circle              | Send button in chat input      |
| Spinner          | Animated circular dots          | Loading state (generation)     |
| Copy (⊞)         | Overlapping squares             | Copy action in diff card       |
| Sidebar toggle   | Column/panel icon               | Window chrome                  |

### 7.3 Image Treatments

- **No images or illustrations** observed in the UI
- Content is entirely text-based (writing tool)
- AI-generated text diffs use **inline highlighting** (teal/cyan background) rather than any visual diff imagery
- Skeleton loading states use **blurred/grayed text blocks** rather than shimmer or placeholder images

---

## 8. Patterns

These are recurring **combinations of components** that appear as higher-level patterns across multiple screens.

### 8.1 Selection List Pattern

A vertical stack of selectable options, each a card.

```
┌──────────────────────────────────┐
│ [●] Title (bold)                 │  ← Selection card
│     Description (muted)          │
└──────────────────────────────────┘
┌──────────────────────────────────┐
│ [○] Title (bold)                 │
│     Description (muted)          │
└──────────────────────────────────┘
         ...
┌──────────────────────────────────┐
│          [ Action Button ]       │  ← Full-width pill button
└──────────────────────────────────┘
```

**Used in:** Onboarding writing style selection (Screenshot 1)

### 8.2 AI Chat Input Pattern

A floating input with model selector, attachments, and contextual suggestions.

```
┌──────────────────────────────────────────────┐
│ Placeholder text...                          │
│                                              │
│ [Model ⌄] [Quality]           [+]  [↑ Send] │
└──────────────────────────────────────────────┘
 ✨ Suggestion one
 ─────────────────────────────────────────────
 ✨ Suggestion two
 ─────────────────────────────────────────────
 ✨ Suggestion three
```

**Used in:** Editor bottom panel (Screenshots 3, 9, 10)

### 8.3 Cascading Menu Pattern

A primary menu that reveals a secondary sub-menu to its right on item hover.

```
┌─────────────┐
│ Instruct    │
│ ★ Polish    │──▶ ┌───────────────┐
│ Deepen      │    │ Smooth flow   │
│ Enhance     │    │ Tighten       │
└─────────────┘    │ Clarify       │
                   └───────────────┘
```

**Used in:** Floating toolbar AI actions (Screenshots 8, 13, 14, 15)

### 8.4 AI Action → Result → Resolution Pattern

A three-step flow for AI-assisted editing:

1. **Trigger**: User selects text → floating toolbar appears → picks AI action
2. **Result**: Diff card appears inline showing original vs. AI text
3. **Resolution**: Accept / Revise / Dismiss actions

```
[Select text] → [Floating Toolbar] → [AI Action + Sub-action]
                                          ↓
                                   [Diff Result Card]
                                   ┌──────────────────────┐
                                   │ Action Label    [⊕↺] │
                                   │                      │
                                   │ Original text. NEW   │
                                   │ TEXT HIGHLIGHTED.     │
                                   │                      │
                                   │ [Discard]  [Accept]  │
                                   └──────────────────────┘
                                          ↓
                                   [If Revise → Revision Options Menu]
```

**Used in:** Screenshots 6–16 collectively

### 8.5 Writing Quality Checks Pattern

A panel showing score + categorized issues:

```
┌──────────────────────────────────┐
│ Checks                      [✨] │
│                                  │
│ Writing quality          --/100  │
│ ████████████████░░░░░░░░░░░░░░░ │
│                                  │
│ 🔴 Fix critical mistakes        │
│ ──────────────────────────────── │
│ 🔵 Improve accuracy and clarity │
│ ──────────────────────────────── │
│ 🟢 Tighten word choice          │
│ ──────────────────────────────── │
│ 🟢 Smooth dialogue transitions  │
│ ──────────────────────────────── │
│ 🟢 Clarify character persp.     │
└──────────────────────────────────┘
```

**Used in:** Screenshot 5

### 8.6 Generation Progress Pattern

A centered overlay showing step-by-step AI processing:

```
          [Blurred content behind]

     ┌──────────────────────────────┐
     │ ✨ Generating scenes         │
     │                              │
     │ ⏳ Preparing scenes          │  ← Active (bold, spinner)
     │ ○  Reading story context     │  ← Pending (muted)
     │ ○  Planning scene beats      │
     │ ○  Writing scene desc.       │
     │ ○  Refining scene flow       │
     └──────────────────────────────┘
```

**Used in:** Screenshot 17

### 8.7 Project Card Pattern

A card for creating or opening a writing project:

```
┌───────────────────────┐
│ +                     │
│ Project Title (bold)  │
│ Description (muted)   │
│                       │
│                       │
└───────────────────────┘
```

**Used in:** Dashboard / Library view (Screenshot 2)

### 8.8 Sidebar Shell Pattern

The persistent application chrome:

```
┌────────────────┐
│ [☁ Library   ] │  ← Nav item (active)
│ [✏ New project] │  ← Nav item
│                │
│                │
│    (spacer)    │
│                │
│ [T] Name       │  ← User avatar + info
│     Plan label │
│    [Upgrade]   │  ← CTA button
└────────────────┘
```

**Used in:** Screenshot 2 (and inferred on all authenticated pages)

---

## Appendix: Screenshot Reference Map

| Screenshot | View / State                                                    |
| ---------- | --------------------------------------------------------------- |
| 1          | Onboarding — Writing style selection                            |
| 2          | Dashboard — Library with empty state / new project card         |
| 3          | Editor — Bottom panel with AI chat input + suggestions          |
| 4          | Context menu — Share, Duplicate, Trash, Appearance, Minimal     |
| 5          | Checks panel — Writing quality score + categorized issues       |
| 6          | Inline toolbar (compact) — Polish, Deepen, Enhance             |
| 7          | Autocomplete dropdown (dark) — Continue paragraph, Describe…    |
| 8          | Floating toolbar — Formatting + AI actions (Polish selected)    |
| 9          | Inline instruction input — Model selector (Claude 4.5 Haiku)   |
| 10         | Inline instruction input — "How should Feldar edit" prompt      |
| 11         | Action popover — Accept, Revise, Dismiss + "esc to dismiss"     |
| 12         | Revision options menu — Longer, Shorter, More interiority…      |
| 13         | Floating toolbar — Polish sub-menu (Smooth flow, Tighten…)      |
| 14         | Floating toolbar — Deepen sub-menu (Deepen description…)        |
| 15         | Floating toolbar — Enhance sub-menu (Add foreshadowing…)        |
| 16         | AI diff result card — Add Interiority with highlighted text      |
| 17         | Generation progress overlay — "Generating scenes" with steps    |
