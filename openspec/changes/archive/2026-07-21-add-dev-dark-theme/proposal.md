## Why

目前簡報已支援主管版與工程版文案切換，但兩者仍共用同一淺色視覺語言，工程受眾的識別度與沉浸感不足。為了讓模式切換更直覺且可感知，工程版需要具備專屬暗色主題。

## What Changes

- 新增模式與主題的聯動規則：`supervisor` 對應淺色主題、`dev` 對應暗色主題。
- 保持同一份 HTML 與同一套 12 頁骨架，不建立第二份簡報。
- 切換模式時同步切換文案與主題，且不重置目前頁碼。
- 保留既有 localStorage 偏好機制，使重整後維持模式與主題一致。
- 針對暗色主題調整卡片、文字、按鈕、提示與 CLI 區塊對比，確保可讀性。

## Capabilities

### New Capabilities
- `dev-dark-theme`: 提供工程版模式的暗色主題能力，並與受眾模式切換狀態一致化。

### Modified Capabilities
- 無。

## Impact

- Affected code: `presentation.html` 的 CSS tokens、模式切換渲染邏輯、主題樣式條件。
- APIs: 無。
- Dependencies: 無新增外部套件，維持靜態 HTML/CSS/JS。
- Systems: 提升工程版辨識度與展示一致性，同時維持主管版現有體驗。