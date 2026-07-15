## Context

現有 `presentation.html` 已完成 12 頁主管導向版本，並具備左到右導覽、進度條、鍵盤與觸控互動。當前限制是內容僅有單一語氣，主管與工程受眾無法在同一份簡報中切換到更適配的訊息密度。

本變更需要在不分叉檔案、不改動現有流程節奏的前提下，加入受眾模式切換（`supervisor` / `dev`），讓同一套版面可以切換兩種文案。

## Goals / Non-Goals

**Goals:**
- 在單一 HTML 中提供主管版與工程版切換。
- 切換後即時更新當頁文案，且不改變目前頁碼。
- 保持相同 12 頁與相同流程順序（Explore → Propose → Apply → Archive）。
- 使用 localStorage 保留最後一次模式偏好。

**Non-Goals:**
- 不建立第二份簡報檔案。
- 不改動核心版面結構與頁數。
- 不新增外部前端框架或狀態管理依賴。

## Decisions

### Decision 1: 採用單一狀態來源 `mode`
- Choice: 使用全域前端狀態 `mode`（`supervisor` / `dev`）作為唯一文案選擇依據。
- Rationale: 單一來源可避免狀態分歧，維持渲染可預測。
- Alternative: 使用多組 CSS 類別切換大量 DOM 區塊顯示。
- Why not alternative: DOM 重複度高、維護成本高、易產生不一致。

### Decision 2: 文案資料化（slide copy map）
- Choice: 每頁標題、內文與證據欄位改由資料映射（supervisorCopy/devCopy）驅動。
- Rationale: 後續調整文案時不需改動版面結構。
- Alternative: 在 HTML 內硬編兩份文案並用條件顯示。
- Why not alternative: 可讀性與維護性較差。

### Decision 3: 切換控件放在頂部 meta 區
- Choice: 在現有頂欄區放置 segmented control。
- Rationale: 使用者可隨時切換，不影響左右翻頁按鈕心智模型。
- Alternative: 放在底部或隱藏在設定區。
- Why not alternative: 可發現性較低或與翻頁操作競爭注意力。

### Decision 4: 切換不重置投影片位置
- Choice: 模式切換僅重渲染當前頁文案，不變更 `current` index。
- Rationale: 保持講述節奏，避免使用者迷失。
- Alternative: 切換後回到第 1 頁。
- Why not alternative: 破壞會議情境與即時比較需求。

## Risks / Trade-offs

- [Risk] 文案資料化後結構複雜度上升。
  - Mitigation: 使用固定欄位鍵名與驗證清單。
- [Risk] 切換控件在小螢幕可能擁擠。
  - Mitigation: 行動裝置採壓縮字樣與水平滾動保護。
- [Trade-off] 單頁雙模式會增加內容維護工作量。
  - Mitigation: 共用視覺骨架，僅維護文案差異。
- [Risk] localStorage 不可用時偏好無法保留。
  - Mitigation: 回退到預設 `supervisor` 並不中斷功能。

## Migration Plan

1. 新增模式切換控件與 `mode` 狀態初始化。
2. 將每頁文案抽離為雙版本映射資料。
3. 導入切換事件與即時重渲染（不改 `current` index）。
4. 加入 localStorage 讀寫與錯誤回退。
5. 驗證兩種模式流程一致、文案正確、互動不回歸。

## Open Questions

- 工程版證據欄是否固定採 artifact/state/command 三段格式？
- 後續是否需要第三種模式（例如 sales/demo）？