## Why

The deck has 14 slides covering 5 distinct sections, but the audience gets no roadmap before diving in. An index slide after the cover gives the speaker a natural "here's what we'll cover" moment and lets any viewer quickly jump to a section during Q&A.

## What Changes

- Add a new index slide as Slide 3 (inserted after the cover slide, Slide 2 / 封面)
- The slide displays 5 clickable section cards — each jumps directly to its first relevant slide
- Sections: 問題 → 流程 → 實例 → 評估 → 導入
- Update all hardcoded slide counts (CSS `deck` width, `slide` width, JS `total`, `stageNames`) from 14 → 15

## Capabilities

### New Capabilities
- `section-index-slide`: A visual index slide with 5 clickable section cards that navigate to the corresponding slide in the deck

### Modified Capabilities

## Impact

- `presentation.html`: new `<article class="slide index-slide">` inserted as third slide; JS `jumpTo()` helper added; CSS card styles added; `total`, deck/slide widths, and `stageNames` updated from 14 → 15
