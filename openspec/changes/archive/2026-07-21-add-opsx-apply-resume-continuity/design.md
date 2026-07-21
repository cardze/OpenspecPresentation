## Context

現有簡報已經展示 OpenSpec 的流程、雙受眾模式與案例頁，但還沒有把一個重要治理能力講清楚：工作一旦進入 OpenSpec change 流程後，實作進度是記錄在 proposal、design、specs、tasks 與完成狀態裡，而不是依賴單一 chat session 保持上下文。這次變更的範圍是補強簡報敘事，讓觀眾理解 `opsx-apply` 的價值在於基於 artifact state 續做，而不是「AI 記得上次聊到哪」。

目前簡報是單一 `presentation.html`，透過 `copyMap` 支援 `supervisor` 與 `dev` 兩種文案模式。新增觀點時，應優先重用既有案例頁或優勢頁的敘事位置，避免擴頁或引入新的互動結構。

## Goals / Non-Goals

**Goals:**
- 在簡報中明確表達 OpenSpec change 的可中斷、可續做能力。
- 將續做能力描述為 artifact-backed workflow continuity，而非 chat memory continuity。
- 在 supervisor 與 dev 兩種模式下，都提供各自可理解的 resume 敘事。
- 保持既有 13 頁架構、導航、主題切換與互動行為不變。

**Non-Goals:**
- 不新增新的 CLI 能力或修改 `opsx-apply` 行為。
- 不新增第二個案例頁或再擴充頁數。
- 不調整現有 mode/theme persistence 機制。

## Decisions

### Decision 1: 將 resume continuity 放在既有案例或價值敘事中
- Choice: 將觀點整合進現有案例頁或優勢頁文案，而非新增獨立投影片。
- Rationale: 這個觀點本質上是在補強價值敘事，不需要為單一訊息增加新的頁面負擔。
- Alternative: 另開一頁專門講 session resume。
- Why not alternative: 會讓 deck 膨脹，並稀釋現有案例頁的作用。

### Decision 2: 明確區分 session continuity 與 artifact continuity
- Choice: 文案明示恢復能力來自 change artifacts 與 tasks state。
- Rationale: 這是 OpenSpec 與一般一次性對話流程的本質差異，也是最有說服力的點。
- Alternative: 以「下次還能接著聊」作為主敘事。
- Why not alternative: 容易讓受眾誤以為能力核心是聊天記憶，而不是流程治理。

### Decision 3: 主管版與工程版使用不同語氣但同一核心事實
- Choice: 主管版強調可交接、不中斷；工程版強調 `opsx-apply` 依據 artifact state 恢復。
- Rationale: 同一事實在兩種受眾下的價值焦點不同，應維持既有 dual-copy 設計。
- Alternative: 兩種模式共用同一句 resume 文案。
- Why not alternative: 會削弱模式切換的受眾價值。

## Risks / Trade-offs

- [Risk] 如果文案過度簡化，觀眾可能把 resume 能力理解成單純聊天記憶。
  - Mitigation: 在 evidence 或正文中明示依據是 proposal/design/specs/tasks 與完成狀態。
- [Trade-off] 不擴頁會壓縮單頁訊息密度。
  - Mitigation: 優先改寫案例頁中的結果或收斂句，避免整頁堆太多新文字。
- [Risk] 如果工程版文案過於術語化，主管版切換後會失去直觀性。
  - Mitigation: 延續目前 copyMap 的分眾策略，分別撰寫 supervisor/dev 版本。

## Migration Plan

1. 確定觀點放入案例頁或優勢頁的具體位置。
2. 更新對應視覺卡片與 `copyMap` 中的 supervisor/dev 文案。
3. 驗證 mode 切換後 resume 敘事會同步更新，且不影響當前頁。
4. 檢查簡報在桌機與手機版面仍可讀，避免新增文案造成溢位。

## Open Questions

- 應該把 resume continuity 放在案例頁的「結果」欄，還是放在優勢頁作為獨立價值點？
- 是否要在 CLI 示意頁補一行 `opsx-apply` 續做路徑，讓命令感更具體？
