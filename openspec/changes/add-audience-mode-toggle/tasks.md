## 1. Mode Toggle UI Setup

- [x] 1.1 Add an audience mode toggle control in the top meta area (`supervisor` and `dev`)
- [x] 1.2 Add visible active-state styling and accessible labels for the selected mode
- [x] 1.3 Ensure keyboard and touch interactions can operate the mode toggle control

## 2. Mode State and Persistence

- [x] 2.1 Add a single source of truth for mode state in presentation script (`supervisor` default)
- [x] 2.2 Persist selected mode in localStorage and restore it on page load
- [x] 2.3 Add fallback behavior to `supervisor` mode when storage is unavailable

## 3. Dual Copy Mapping and Rendering

- [x] 3.1 Define per-slide dual-copy mapping for title/body/evidence (`supervisorCopy` and `devCopy`)
- [x] 3.2 Update rendering logic so mode switch updates copy without resetting current slide index
- [x] 3.3 Keep slide count and stage sequence unchanged across both modes

## 4. Validation and Review

- [x] 4.1 Verify mode switch on mid-deck slide preserves position and navigation state
- [x] 4.2 Verify both modes maintain Explore -> Propose -> Apply -> Archive sequence
- [x] 4.3 Verify dev mode evidence copy includes technical context (artifact/state/command semantics)
