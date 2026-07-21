## Context

`presentation.html` is a self-contained single-file presentation. Slides are `<article class="slide">` elements inside a `<section class="deck">`. Navigation and slide counting are managed by inline JavaScript. The current cover slide (Slide 1) embeds presenter info in the `.kicker` as a small subordinate span.

## Goals / Non-Goals

**Goals:**
- Prepend a new intro slide with topic, group, and name
- Match the existing two-column (`.visual` / `.copy`) slide layout and CSS variables
- Remove the redundant `.presenter-info` span from Slide 1
- Keep the slide counter accurate

**Non-Goals:**
- Introducing new CSS classes or design tokens
- Making presenter info editable at runtime
- Supporting multiple presenters

## Decisions

**Reuse `.visual` / `.copy` layout** — The new slide uses the same two-column structure as all other slides. No new layout class needed. The `.visual` area uses the existing `.brand-mark` element for visual weight without adding new assets.

**Topic displayed as `h2`, no label** — The topic "OpenSpec 優缺點" sits as an `h2` (matching other slides' headings). Group and name are rendered as `.presenter-info` spans (already styled as muted, block-level metadata). No additional label element needed.

**Slide inserted as first `<article>` in `#deck`** — Prepending keeps the JS navigation logic untouched; the counter auto-increments because it counts `article.slide` elements.

## Risks / Trade-offs

- Counter reads `1 / 13` hardcoded in `<span id="counter">` → must be updated to `1 / 14` manually; if future slides are added this will drift again (pre-existing issue, not introduced here)
