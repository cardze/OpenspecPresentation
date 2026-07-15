## 1. Theme Token Setup

- [x] 1.1 Define dark theme color tokens for background, text, cards, borders, and controls
- [x] 1.2 Add a theme application mechanism (class or data-attribute) without changing slide structure
- [x] 1.3 Keep supervisor mode mapped to the existing light theme tokens

## 2. Mode-Theme Coupling

- [x] 2.1 Update mode switch logic so `dev` mode applies dark theme and `supervisor` applies light theme
- [x] 2.2 Ensure mode switch updates copy and theme together in a single interaction
- [x] 2.3 Ensure switching mode does not reset current slide index, progress, or stage state

## 3. Persistence and Fallback

- [x] 3.1 Restore mode and corresponding theme from persisted storage on page load
- [x] 3.2 Add graceful fallback to supervisor/light theme if storage access fails
- [x] 3.3 Verify persisted dev mode reloads into dark theme consistently

## 4. Readability and Regression Validation

- [x] 4.1 Verify dark theme readability for headings, body copy, evidence text, and cards
- [x] 4.2 Verify mode toggle, navigation buttons, and progress indicator remain clear in dark theme
- [x] 4.3 Verify slide count remains 12 and Explore -> Propose -> Apply -> Archive order is unchanged
