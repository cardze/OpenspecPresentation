## Why

目前簡報只有單一受眾語氣，主管與工程人員在同一版本中會同時遇到資訊過多或過少的問題。新增受眾模式切換可以在不分叉檔案的前提下，讓同一份簡報同時服務決策溝通與技術溝通。

## What Changes

- 在現有簡報新增受眾模式切換：`supervisor` 與 `dev`。
- 維持同一套 12 頁骨架與左到右流程，不建立第二份 HTML。
- 將每頁核心文字改為雙文案映射（主管版/工程版），切換時即時更新。
- 讓模式選擇在重整後仍保留（localStorage）。
- 在 UI 明確標示目前模式，並保留鍵盤與行動裝置可用性。

## Capabilities

### New Capabilities
- `audience-mode-toggle`: 提供單頁簡報中的受眾模式切換能力，在相同版面下切換主管版與工程版文案，並維持流程一致性與使用者偏好持久化。

### Modified Capabilities
- 無。

## Impact

- Affected code: `presentation.html` 的頂部控制列、文案資料結構、前端狀態管理與渲染邏輯。
- APIs: 無。
- Dependencies: 無新增外部依賴，維持靜態 HTML/CSS/JS。
- Systems: 提升簡報在多受眾場合的適配能力，降低維護兩份簡報的成本。