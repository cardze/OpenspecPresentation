## Why

The presenter's identity (topic, group, name) is currently hidden in a small span inside the Slide 1 kicker — easy to miss and visually undersized for a presentation opener. A dedicated intro slide makes the presenter context immediately clear before the content begins.

## What Changes

- Add a new intro slide prepended before the current Slide 1 (cover)
- Intro slide displays: presentation topic, group, and presenter name — no field labels on the topic
- Remove the `.presenter-info` span from Slide 1's kicker (now redundant)
- Update slide counter to reflect the additional slide

## Capabilities

### New Capabilities
- `presenter-intro-slide`: A dedicated opening slide showing topic ("OpenSpec 優缺點"), group ("外匯財會組"), and name ("王上澤") in the same visual style as existing slides

### Modified Capabilities

## Impact

- `presentation.html`: new `<article class="slide">` inserted before current first slide; `.presenter-info` span removed from Slide 1 kicker; slide counter (1 / 13 → 1 / 14) updated
