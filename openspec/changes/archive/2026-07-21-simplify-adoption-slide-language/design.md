## Context

The 導入策略 slide (Slide 11) currently shows three `.stage-card` elements with English scope labels (Pilot/Team/Org) and jargon sub-descriptions. These terms were identified as confusing during a review: "Pilot", "跨職能小隊", "review gate", and "回灌機制" all require prior knowledge to interpret. The slide's core message — start small, spread gradually, make it habit — is simple and should read that way.

## Goals / Non-Goals

**Goals:**
- Replace all jargon in the `.visual` area with plain Chinese
- The three steps should be immediately understandable without explanation
- Keep the existing `.workflow-band` + `.stage-card` HTML structure (visual layout unchanged)

**Non-Goals:**
- Changing the CSS or visual structure
- Rewriting other slides
- Adding timelines or scope labels back in any form

## Decisions

**Keep three cards, replace labels only** — The three-column card grid is visually clean and the audience already sees it. Removing the cards would require layout work. Only the text inside changes.

**New card content:**
| Card | stage-title | mini |
|------|-------------|------|
| ① | 先試一個專案 | 用 OpenSpec 跑一次完整流程 |
| ② | 推給組員一起用 | 建立共同的提案與任務習慣 |
| ③ | 固定成小組標準 | 每次交付都有規格可追溯 |

**Update `.copy` heading** — "建議分三階段導入：先小試，再擴大" is still valid but slightly formal. Adjust to: "怎麼開始？三步走。"

## Risks / Trade-offs

- [Loss of specificity] → The original timelines (2-4 週, 1-2 月, 季度) are removed. This is intentional — for a casual demo, precision signals complexity, not credibility.
