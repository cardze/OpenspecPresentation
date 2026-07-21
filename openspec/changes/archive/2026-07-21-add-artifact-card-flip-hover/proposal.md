## Why

The Propose slide shows three artifact cards (proposal.md, design.md, tasks.md) with abstract descriptions, but gives the audience no sense of what these files actually look like. A hover-triggered card flip reveals a short Traditional Chinese example snippet on the back — turning a static description into a live preview during the demo.

## What Changes

- The three artifact cards on the Propose slide get a 3D flip-on-hover interaction
- Front face: existing title + description (unchanged)
- Back face: short Traditional Chinese example snippet per card
  - `proposal.md` → `## 為什麼` + example motivation
  - `design.md` → `## 設計決策` + example decision with rationale
  - `tasks.md` → example `- [x]` / `- [ ]` checklist lines
- Flip is scoped to a new `.flip-card` modifier class — does NOT affect other `.value-card` elements on other slides
- New CSS classes added: `.flip-card`, `.card-inner`, `.card-front`, `.card-back`

## Capabilities

### New Capabilities
- `artifact-card-flip`: Card flip hover interaction on the Propose slide's three artifact cards, showing Traditional Chinese example content on the back face

### Modified Capabilities

## Impact

- `presentation.html`: new CSS for 3D flip; three `.value-card` elements on the Propose slide restructured with `.flip-card` wrapper and front/back faces
