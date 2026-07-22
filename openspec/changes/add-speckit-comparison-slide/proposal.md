## Why

The presentation evaluates OpenSpec's pros and cons but doesn't explain how it compares to the most prominent alternative — Spec Kit (github/spec-kit, 123k stars, maintained by GitHub). Adding a comparison slide gives the audience context for why OpenSpec was chosen over a well-known option, making the recommendation more credible and grounded.

## What Changes

- Add one new slide after the 優勢 slide (Slide 12) comparing OpenSpec and Spec Kit across: maintainer, target scale, setup cost, workflow steps, and best-fit scenario
- Update slide count from 15 → 16 in CSS (deck width, slide width) and JS (total, stageNames)
- Update the index slide jump targets if any indices shift

## Capabilities

### New Capabilities
- `speckit-comparison`: A side-by-side comparison of OpenSpec and Spec Kit shown as a slide in the presentation, positioned after the 優勢 slide

### Modified Capabilities

## Impact

- `presentation.html`: new slide article, CSS deck/slide width, JS total constant, stageNames array, index slide jump indices
