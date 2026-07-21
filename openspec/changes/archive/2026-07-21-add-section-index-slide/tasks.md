## 1. Update Slide Counts

- [x] 1.1 Update `.deck` CSS width from `1400%` to `1500%`
- [x] 1.2 Update `.slide` CSS width from `calc(100% / 14)` to `calc(100% / 15)`
- [x] 1.3 Update JS `const total` from `14` to `15`
- [x] 1.4 Prepend `"路線圖"` to the `stageNames` array for the new index slide (position 2)

## 2. Add jumpTo Helper

- [x] 2.1 Add `function jumpTo(index) { current = index; render(); }` to the JS block

## 3. Add Index Slide CSS

- [x] 3.1 Add `.index-slide` grid and layout styles (full-width, centered heading)
- [x] 3.2 Add `.section-cards` grid styles (2-column card grid)
- [x] 3.3 Add `.section-card` button styles (number, name, description; hover state using existing CSS variables)

## 4. Insert Index Slide HTML

- [x] 4.1 Insert `<article class="slide index-slide">` as the third `<article>` in `#deck` (after the cover slide)
- [x] 4.2 Add `.visual` area with `.section-cards` grid containing 5 `<button class="section-card">` elements with correct `jumpTo()` indices and labels
- [x] 4.3 Add `.copy` area with heading `今天的路線` and subtitle
