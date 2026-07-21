## Context

`presentation.html` is a self-contained single-file deck. Navigation uses a `current` index + `render()` pattern with hardcoded `total` (currently 14). The deck is a horizontal flex strip moved via `translateX`. All slide counts are hardcoded in three places: CSS (`deck` width, `slide` width) and JS (`total`, `stageNames`).

## Goals / Non-Goals

**Goals:**
- Insert an index slide at position 2 (0-based), after the cover slide
- Display 5 section cards, each clickable, jumping to the correct slide index
- Match visual style of existing slides (CSS variables, card/panel patterns)
- Keep all hardcoded counts consistent (15 slides total)

**Non-Goals:**
- Dynamic slide counting (still hardcoded — pre-existing pattern)
- Highlight the active section as the user navigates through the deck
- Mobile-specific layout changes

## Decisions

**Large clickable cards over pills** — The 5 sections each need a number, name, and one-line description. Pills are too small. `.panel`-style cards (already used in comparison slides) provide enough space and fit the visual language. Cards are styled as `<button>` elements for accessibility and native click handling.

**`jumpTo(index)` helper function** — Rather than inline `onclick` attributes with `current = N; render()`, a named `jumpTo(n)` function is exposed on the JS scope. Cards call `jumpTo(N)` via `onclick`. This keeps HTML clean and the function is reusable.

**Index slide uses two-column card grid** — The `.visual` area holds a 2×3 grid (or 3+2) of section cards. The `.copy` area provides a short heading and subtitle. This reuses the existing two-column slide layout without new structural CSS.

**Jump targets (0-based after insertion):**
```
問題  → index 3  (Slide 4 / 痛點)
流程  → index 4  (Slide 5 / 全景)
實例  → index 10 (Slide 11 / 實作範例)
評估  → index 11 (Slide 12 / 優勢)
導入  → index 13 (Slide 14 / 導入策略)
```

## Risks / Trade-offs

- [Hardcoded jump indices] → If slides are reordered later, indices break. Mitigation: document the mapping in a comment near the index slide HTML.
- [Hardcoded total] → Must update 4 locations (CSS ×2, JS ×2) consistently. Mitigation: task list covers all four.
