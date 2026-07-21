## Why

目前簡報已說明 OpenSpec 的流程與受眾切換價值，但還沒有明確講出一個關鍵觀點：實作一旦進入 OpenSpec change 流程後，進度是被 artifacts 與 tasks 外部化管理，而不是綁在單一 chat session 內。補上這個觀點，能更清楚說明 OpenSpec 為什麼適合長週期、可中斷、需要交接的工作。

## What Changes

- 在簡報中新增一個明確觀點：開始實作 OpenSpec change 後，即使 chat session 中斷，仍可透過 `opsx-apply` 從當前階段續做。
- 將這個觀點表述為 artifact-backed workflow continuity，而非單純的聊天記憶延續。
- 在案例敘事或優勢敘事中補上 resume point 的說明，強調 proposal、design、specs、tasks 與完成狀態是可續做依據。
- 保持既有 13 頁骨架、雙受眾模式與主題聯動，不新增第二份簡報。

## Capabilities

### New Capabilities
- `apply-resume-continuity-message`: 在簡報中表達 OpenSpec change 的可中斷、可續做特性，說明 `opsx-apply` 可基於既有 artifacts 與 task state 恢復實作脈絡。

### Modified Capabilities
- 無。

## Impact

- Affected code: `presentation.html` 的案例頁或優勢頁文案、`copyMap` 對應模式文案、必要時的 evidence 敘事。
- APIs: 無。
- Dependencies: 無新增外部依賴，維持靜態 HTML/CSS/JS。
- Systems: 強化簡報對 OpenSpec 治理能力的說服力，特別是在 session 中斷與跨人續做場景下。
