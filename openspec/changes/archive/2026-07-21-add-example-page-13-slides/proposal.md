## Why

目前簡報雖已涵蓋流程與優缺點，但缺少具體案例頁，導致收尾說服力不足。新增一頁「實作範例」能把抽象價值轉成可感知結果，特別有助於工程版受眾理解落地方式。

## What Changes

- 將簡報頁數由 12 頁擴充為 13 頁。
- 新增一頁「實作範例（Case Study）」並放在 CLI 示意頁後。
- 在實作範例頁呈現：問題、做法、命令路徑、結果與一句收斂。
- 保持既有受眾模式切換（supervisor/dev）與主題聯動行為。
- 更新導航計數、進度條、章節標籤與文案映射以支援 13 頁。

## Capabilities

### New Capabilities
- `presentation-example-page`: 提供一頁可視化案例說明，將 OpenSpec 流程從概念敘述延伸到具體落地結果，並支援 supervisor/dev 雙版本文案。

### Modified Capabilities
- 無。

## Impact

- Affected code: `presentation.html` 的 deck 結構、頁碼/進度邏輯、copy map 資料與新增案例頁區塊。
- APIs: 無。
- Dependencies: 無新增外部依賴，維持靜態 HTML/CSS/JS。
- Systems: 提升簡報結尾說服力與工程受眾的落地理解深度。