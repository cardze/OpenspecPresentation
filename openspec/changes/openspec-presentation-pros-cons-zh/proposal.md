## Why

目前專案只有 OpenSpec 骨架與提示檔，缺少可用於對外或對內溝通的視覺化介紹材料。為了讓主管與 PM 在短時間理解 OpenSpec 的價值與代價，需要一份以繁體中文呈現、由左到右敘事、插圖優先的 HTML 簡報。

## What Changes

- 新增一份以本專案為範例的 HTML 簡報，主題為 OpenSpec 的優點與限制。
- 簡報採左到右敘事流程，覆蓋 Explore、Propose、Apply、Archive 四個階段。
- 全文使用繁體中文，並以插圖與流程圖為主、文字為輔。
- 加入一頁 CLI 示意流程（示意，不要求 live demo）。
- 提供適合主管與 PM 的結論頁，包含導入建議與使用情境判斷。

## Capabilities

### New Capabilities
- `openspec-presentation`: 提供可視化、可瀏覽的 OpenSpec 介紹簡報能力，使用本專案內容作為證據來源並輸出繁體中文左到右敘事。

### Modified Capabilities
- 無。

## Impact

- Affected code: 新增簡報頁面檔案與對應樣式、圖示資產或嵌入式 SVG 結構。
- APIs: 無。
- Dependencies: 可選擇零依賴靜態 HTML/CSS/JS，或最小化前端依賴。
- Systems: 提升此倉庫作為 OpenSpec 導覽與說明用途的可用性。