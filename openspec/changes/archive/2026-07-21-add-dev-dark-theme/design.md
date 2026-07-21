## Context

現有簡報已支援 `supervisor` 與 `dev` 兩種文案模式，但視覺主題仍主要偏向淺色，導致工程版在視覺辨識與情境一致性上不夠明確。本變更要在既有單頁架構中，新增模式與主題聯動：主管版維持淺色，工程版切換為暗色。

需求邊界為不新增第二份 HTML、不改 12 頁結構、不改左到右流程，僅在樣式與模式渲染層面擴充。

## Goals / Non-Goals

**Goals:**
- 建立 `supervisor`（淺色）與 `dev`（暗色）主題聯動規則。
- 切換模式時同步切換主題與文案，且不重置目前頁碼。
- 維持既有導航、進度條、鍵盤與觸控互動行為。
- 在暗色主題下維持良好文字與元件對比。

**Non-Goals:**
- 不提供獨立第三種主題覆寫選項。
- 不跟隨系統深色偏好自動切換。
- 不改動投影片順序與內容骨架。

## Decisions

### Decision 1: mode 驅動 theme（單一映射規則）
- Choice: `mode=supervisor -> light theme`，`mode=dev -> dark theme`。
- Rationale: 規則簡單且可預測，避免模式與主題分離造成混亂。
- Alternative: mode 與 theme 完全獨立。
- Why not alternative: 增加狀態組合與測試矩陣，超出本次範圍。

### Decision 2: CSS 變數分層切換
- Choice: 以主題層級 class 或 data-attribute 切換 CSS tokens（背景、文字、卡片、邊框、按鈕）。
- Rationale: 可最小改動現有樣式結構，且易於維護。
- Alternative: 針對每個元件硬編兩套樣式。
- Why not alternative: 重複度高且容易樣式漂移。

### Decision 3: 主題切換不影響導航狀態
- Choice: 切換時保留 `current` slide index，不重置進度。
- Rationale: 符合簡報現場即時對照情境。
- Alternative: 切換後回到第一頁。
- Why not alternative: 破壞使用者心流與比較效率。

### Decision 4: 偏好儲存延續既有 localStorage
- Choice: 持續使用現有儲存機制保存 mode（進而決定 theme）。
- Rationale: 不新增儲存鍵複雜度，沿用既有行為。
- Alternative: 另存獨立 theme key。
- Why not alternative: 與本次「mode 決定 theme」原則衝突。

## Risks / Trade-offs

- [Risk] 暗色主題局部對比不足造成可讀性下降。
  - Mitigation: 逐區塊檢查文字/背景對比，優先正文與按鈕可讀性。
- [Trade-off] mode 與 theme 綁定降低客製自由度。
  - Mitigation: 先確保一致體驗，未來若有需求再提獨立主題 change。
- [Risk] 新增主題 class 可能影響既有元件陰影與邊框層次。
  - Mitigation: 對 card、panel、terminal 區塊做逐頁驗證。

## Migration Plan

1. 定義暗色主題 CSS tokens 與套用入口。
2. 將 mode 切換流程串接到主題 class/data-attribute 切換。
3. 驗證在任意頁切換時，頁碼與進度狀態維持不變。
4. 驗證重整後 mode/theme 偏好恢復。
5. 進行桌機與手機可讀性檢查。

## Open Questions

- 是否需要為工程版加入更明顯的 terminal-style 視覺語彙（例如發光邊框）？
- 暗色主題是否要在簡報匯出截圖場景下提供列印友善模式？