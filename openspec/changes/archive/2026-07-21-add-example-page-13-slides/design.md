## Context

目前簡報在雙受眾與暗色主題上已可切換，但敘事在結尾缺少具體案例承接，容易讓重點停留在功能描述。此變更要新增第 13 頁「實作範例」，將抽象流程轉成具體成果故事，並保留 supervisor/dev 模式對應文案。

此變更為結構性更新，需同步調整投影片總數、deck 寬度、進度計算、頁碼顯示與文案映射長度。

## Goals / Non-Goals

**Goals:**
- 將簡報由 12 頁擴充為 13 頁。
- 新增一頁案例頁並置於 CLI 示意頁之後。
- 案例頁同時支援 supervisor/dev 兩種文案語氣。
- 保持既有模式切換、主題聯動與導航體驗。

**Non-Goals:**
- 不改動既有每頁視覺骨架設計語言。
- 不新增外部資料來源或後端 API。
- 不重構整體框架為多檔案系統。

## Decisions

### Decision 1: 採用固定 13 頁而非動態插頁
- Choice: 將總頁數固定更新為 13，直接納入 deck。
- Rationale: 簡化進度與導航邏輯，避免模式間頁數不一致。
- Alternative: 僅在 dev 模式動態插入案例頁。
- Why not alternative: 會造成 mode 切換時頁碼與流程不一致。

### Decision 2: 案例頁放在 CLI 示意之後
- Choice: 新頁放在原第 8 頁後（成為新第 9 頁）。
- Rationale: CLI 示意先交代機制，再用案例頁示範落地效果，敘事更順。
- Alternative: 放在最末頁。
- Why not alternative: 結尾頁應收斂決策，不宜再引入新資訊。

### Decision 3: 案例頁採五段式信息模塊
- Choice: 問題、做法、命令路徑、結果、收斂。
- Rationale: 工程版可快速抓實作脈絡，主管版可快速抓決策價值。
- Alternative: 純長文敘事。
- Why not alternative: 視覺與閱讀效率較差。

### Decision 4: 文案映射與常數同步更新
- Choice: `total`、`stageNames`、`copyMap` 與 DOM slide 數一起調整。
- Rationale: 避免進度與渲染不同步造成錯頁。
- Alternative: 只新增 DOM 頁，不更新映射資料。
- Why not alternative: 會導致索引越界與文案遺漏。

## Risks / Trade-offs

- [Risk] 新增頁面後進度條與頁碼邏輯可能錯位。
  - Mitigation: 以單一 `total=13` 驗證所有計算分支。
- [Risk] 案例頁訊息過多破壞節奏。
  - Mitigation: 僅保留五段式關鍵詞，不塞長段落。
- [Trade-off] 增頁會拉長簡報時間。
  - Mitigation: 將案例頁控制在 30-45 秒可講完。

## Migration Plan

1. 新增案例頁到 deck 結構。
2. 更新 `total`、進度與頁碼邏輯至 13。
3. 擴充 `stageNames` 與 `copyMap`，加入案例頁 supervisor/dev 文案。
4. 驗證模式切換、主題切換、導航與行動裝置顯示。
5. 檢查結尾頁仍維持收斂定位。

## Open Questions

- 案例頁是否需要放「前後對照數字」占位（例如返工率下降）？
- 是否要在案例頁加入「可複製命令清單」區塊供工程版快速帶走？