## Context

The Propose slide has three `.value-card` elements inside `.cards-3`. The `.value-card` class is shared across multiple slides (優勢, 風險, etc.), so the flip interaction must be scoped to only these three cards. CSS 3D card flip requires a perspective container, a rotating inner wrapper, and two absolutely-positioned faces.

## Goals / Non-Goals

**Goals:**
- 3D flip on hover for the three artifact cards on the Propose slide only
- Back face shows Traditional Chinese example snippets in monospace style
- Smooth transition (≈500ms), no JavaScript required

**Non-Goals:**
- Flip on other `.value-card` elements on other slides
- Touch/tap support (presentation context, mouse-driven)
- Animated typing or progressive reveal on the back face

## Decisions

**`.flip-card` modifier class, not global `.value-card` hover** — Scopes the flip to only the three target cards. Other slides using `.value-card` are unaffected. Alternative (CSS `:nth-child` scoping within the Propose slide) was rejected as fragile if slides are reordered.

**Pure CSS, no JavaScript** — The flip is triggered by CSS `:hover` on `.flip-card`. No JS event listeners needed. Simpler, no risk of breaking navigation JS.

**HTML structure per card:**
```
<div class="value-card flip-card">
  <div class="card-inner">
    <div class="card-front">
      <h3>proposal.md</h3>
      <p>講清楚為什麼現在要做...</p>
    </div>
    <div class="card-back">
      <pre>## 為什麼
AI 產出快但容易走偏，
沒有事先對齊就會白做。</pre>
    </div>
  </div>
</div>
```

**Back face content (Traditional Chinese):**

| Card | 標題 | 內容 |
|------|------|------|
| proposal.md | `## 為什麼` | AI 產出快但容易走偏，沒有事先對齊就會白做。 |
| design.md | `## 設計決策` | 選 Markdown 而非 Wiki → 可以 commit，有版本可追溯。 |
| tasks.md | (checklist) | `- [x] 1.1 建立提案文件`<br>`- [x] 1.2 設計架構`<br>`- [ ] 2.1 實作功能`<br>`- [ ] 2.2 測試驗收` |

**Back face styling** — monospace font, slightly tinted background (`var(--surface)` or light teal tint), smaller font size (13px) to fit the snippet cleanly within the card height.

## Risks / Trade-offs

- [Fixed card height] → `.value-card` has `min-height: 170px`. Back face content must fit within this height. Snippets are kept short to avoid overflow.
- [Flip on presentation projector] → On a projector, hover requires mouse movement over the card. Speaker must deliberately hover to trigger — this is intentional for demo control.
