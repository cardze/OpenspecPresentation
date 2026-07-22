## Context

The presentation currently has 15 slides. The 優勢 slide (Slide 12, index 11) makes the case for OpenSpec's value. Immediately after is the 風險與代價 slide. Inserting a comparison slide between them gives the audience the "why we chose this over the alternative" moment at the natural high point of the presentation, right after establishing OpenSpec's strengths.

The slide count synchronization pattern is already established in this codebase: four locations must be updated together — CSS `.deck { width: Xvw% }`, CSS `.slide { width: calc(100% / X) }`, `const total = X`, and the `stageNames` array.

## Goals / Non-Goals

**Goals:**
- Add one comparison slide positioned after 優勢 (new slide 13, 0-based index 12)
- Show a table comparing OpenSpec vs Spec Kit across 5 dimensions: 維護者, 目標規模, 啟動門檻, 流程步驟, 適合情境
- Framing is "right tool for context" — honest, not disparaging of Spec Kit
- Update all four slide-count sync points (1500% → 1600%, /15 → /16, total 15 → 16, stageNames +1)
- Update index slide jump targets for slides that shift right of the insertion point

**Non-Goals:**
- Detailed feature-by-feature deep dive on Spec Kit
- Logos or external images (keep self-contained)
- Modifying SPEECH.md (presenter can add verbiage at their discretion)

## Decisions

**Slide position: after 優勢, before 風險與代價** — The comparison lands best right after OpenSpec's strengths are established. The audience thinks "OK but why not Spec Kit?" and the slide answers that immediately. Inserting before 風險 preserves the closing rhythm: strengths → comparison → honest trade-offs → adoption.

**Table layout using `.split-compare` panels** — The existing `.split-compare` + `.panel` pattern (used on the 痛點 slide) is the right fit for a two-column comparison. No new CSS needed.

**Tone: complementary, not competitive** — Spec Kit is a 123k-star GitHub-maintained project. Saying "Spec Kit is bad" would be unconvincing and wrong. The framing is: Spec Kit is comprehensive and enterprise-ready; OpenSpec fits smaller teams that need to start immediately without platform setup. The slide heading: `為什麼不是 Spec Kit？因為我們不需要那麼多。`

**stageNames entry: `比較`** — Short, matches the kicker style of other slides.

**Index slide jump targets**: the index cards jump to 0-based indices. Inserting at index 12 shifts the 評估 (優勢) card from 11→11 (unchanged, it's before the insert point) and 導入策略 from 13→14, 結語 from 14→15.

Wait - let me recalibrate. Current 0-based indices:
- 問題 → 3
- 流程 → 4
- 實例 → 10
- 評估 → 11 (優勢 slide)
- 導入 → 13

New slide inserts at index 12 (after 優勢 at 11). Slides at index 12 and 13 shift to 13 and 14. So:
- 導入 → 14 (was 13)
- 結語 → 15 (was 14, no index card)

Only the 導入 index card needs updating: `jumpTo(13)` → `jumpTo(14)`.

## Risks / Trade-offs

- **Accuracy risk**: Spec Kit details must be factually correct — claims about setup steps and target audience are sourced from the official README (verified during explore). Do not add claims not confirmed from that source.
- **Slide count drift**: missing any of the four sync points will break navigation. Must update all four.
- **Tone risk**: comparison slides can read as defensive. Keep the table neutral and let the final kicker line carry the framing.
