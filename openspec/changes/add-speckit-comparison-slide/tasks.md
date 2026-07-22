## 1. Add Comparison Slide HTML

- [x] 1.1 Insert new `<article class="slide">` after the 優勢 slide (around line 1154) with kicker `Slide 13 / 比較`, heading `為什麼不是 Spec Kit？因為我們不需要那麼多。`, a `.split-compare` visual containing two `.panel` elements (Spec Kit | OpenSpec) each with a `<ul>` covering 維護者, 目標規模, 啟動門檻, 流程步驟, 適合情境, and a `.copy` aside with a short summary paragraph

## 2. Update Slide Count Sync Points

- [x] 2.1 Update CSS: `.deck { width: 1500% }` → `1600%` and `.slide { width: calc(100% / 15) }` → `calc(100% / 16)`
- [x] 2.2 Update JS: `const total = 15` → `16`
- [x] 2.3 Update JS: add `比較` entry to `stageNames` array at the correct position (after 優勢, before 風險與代價)

## 3. Update Index Slide and copyMap

- [x] 3.1 Update the 導入 section card: `onclick="jumpTo(13)"` → `onclick="jumpTo(14)"`
- [x] 3.2 Add a copyMap entry for the new comparison slide so dev/supervisor mode toggle works correctly
