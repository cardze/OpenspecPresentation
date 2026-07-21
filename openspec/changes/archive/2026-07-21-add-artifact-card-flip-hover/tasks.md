## 1. Add Flip CSS

- [x] 1.1 Add `.flip-card` perspective container styles (`perspective: 800px`, `cursor: pointer`)
- [x] 1.2 Add `.card-inner` styles (`transform-style: preserve-3d`, `transition: transform 500ms`)
- [x] 1.3 Add `.flip-card:hover .card-inner` rule (`transform: rotateY(180deg)`)
- [x] 1.4 Add `.card-front` and `.card-back` shared styles (absolute position, `backface-visibility: hidden`, full width/height)
- [x] 1.5 Add `.card-back` specific styles (`transform: rotateY(180deg)`, monospace font, tinted background, 13px font size, padding)

## 2. Restructure Propose Slide Cards

- [x] 2.1 Wrap proposal.md `.value-card` content with `.flip-card` > `.card-inner` > `.card-front` / `.card-back` structure; back face shows `## 為什麼` + example in Traditional Chinese
- [x] 2.2 Wrap design.md `.value-card` content with `.flip-card` > `.card-inner` > `.card-front` / `.card-back` structure; back face shows `## 設計決策` + example in Traditional Chinese
- [x] 2.3 Wrap tasks.md `.value-card` content with `.flip-card` > `.card-inner` > `.card-front` / `.card-back` structure; back face shows `- [x]` / `- [x]` checklist in Traditional Chinese
