## Context

目前倉庫以 OpenSpec 結構與提示檔為主，尚未提供可直接給主管與 PM 瀏覽的成果型材料。此變更要新增一份靜態 HTML 簡報，使用本專案中的 OpenSpec 流程檔案作為內容證據，主題為 OpenSpec 的優點與限制。

約束條件如下：
- 簡報需以繁體中文呈現。
- 敘事方向需由左到右，能在單頁水平流程或逐頁前進中清楚感知。
- 內容以插圖與流程視覺為主，避免大量文字。
- 需納入一頁 CLI 示意流程，但不要求 live demo。

主要利害關係人是主管與 PM，因此內容必須可快速理解治理價值、導入成本與風險邊界。

## Goals / Non-Goals

**Goals:**
- 提供 12 頁可瀏覽的 OpenSpec 介紹簡報，聚焦優點與限制。
- 將 Explore、Propose、Apply、Archive 四階段轉為高可讀視覺流程。
- 使用本倉庫現有檔案作為可追溯內容來源，降低主觀宣稱。
- 提供可供決策的結語頁，包含何時適合採用與導入建議。

**Non-Goals:**
- 不建立完整品牌官網或長篇文件站。
- 不提供 OpenSpec CLI 的即時操作展示。
- 不做跨工具量化 benchmarking。

## Decisions

### Decision 1: 採用零依賴靜態簡報（HTML/CSS/JS）
- Rationale: 降低維運負擔，適合在任意環境直接開啟與分享。
- Alternative considered: 使用簡報框架或前端框架（例如 React + slide 套件）。
- Why not alternative: 對本次目標而言依賴過重，且不利於快速交付與閱讀。

### Decision 2: 版面以左到右主軸設計，並提供明確前進提示
- Rationale: 符合需求指定的敘事方向，讓受眾理解流程遞進。
- Alternative considered: 傳統上下捲動單頁。
- Why not alternative: 不易強化階段遞進感，流程訊息會被稀釋。

### Decision 3: 每頁採「主視覺 + 極短文字 + 證據點」三段式
- Rationale: 主管與 PM 對資訊密度敏感，圖像主導可提高理解速度。
- Alternative considered: 長段文字解釋每個技能檔。
- Why not alternative: 文字負荷高，簡報節奏不佳。

### Decision 4: 以 capability 對應規格，內容僅引用可見檔案
- Rationale: 維持 OpenSpec 要求的可追溯性與一致性。
- Alternative considered: 加入外部資料與主觀比較。
- Why not alternative: 會削弱可驗證性，且可能與倉庫證據不一致。

## Risks / Trade-offs

- [風險] 插圖比重過高可能導致資訊不足。
  - Mitigation: 每頁保留一條主講句與一個證據點。
- [風險] 左到右互動在手機上可讀性下降。
  - Mitigation: 手機版改為逐頁卡片，但保留向右前進語意。
- [風險] 內容僅依賴倉庫現況，可能缺少量化說服力。
  - Mitigation: 明確標示「可觀察限制」，並提供導入試點建議。
- [Trade-off] 零依賴架構減少互動特效彈性。
  - Mitigation: 使用適度 CSS 動效與 SVG 插圖補足表達。

## Migration Plan

1. 新增簡報檔案與資產（若有）至倉庫。
2. 以本變更規格核對逐頁內容與流程順序。
3. 完成後由 `opsx:apply` 落實實作與驗證。
4. 若內容與規格一致，進入 archive 流程保存。

## Open Questions

- 最終是否需要企業品牌樣式（Logo、字體、色票）？
- 是否要加上導入前後對照頁作為管理層決策輔助？
