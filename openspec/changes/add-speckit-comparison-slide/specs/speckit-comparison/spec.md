## ADDED Requirements

### Requirement: Comparison slide exists in the deck
The presentation SHALL contain a slide comparing OpenSpec and Spec Kit, positioned immediately after the 優勢 slide.

#### Scenario: Slide is present
- **WHEN** the presenter navigates past the 優勢 slide
- **THEN** a comparison slide with the heading `為什麼不是 Spec Kit？` appears next

### Requirement: Comparison table covers five dimensions
The comparison slide SHALL display a side-by-side table covering: 維護者, 目標規模, 啟動門檻, 流程步驟, and 適合情境.

#### Scenario: Table is complete
- **WHEN** the comparison slide is viewed
- **THEN** both OpenSpec and Spec Kit columns are populated for all five rows

### Requirement: Framing is complementary, not competitive
The slide copy SHALL frame the comparison as "right tool for context" — acknowledging Spec Kit's strengths while explaining why OpenSpec fits better for small-team AI-assisted work.

#### Scenario: Tone check
- **WHEN** the slide is read
- **THEN** no claim disparages Spec Kit; the conclusion is that scale and setup cost drove the choice

### Requirement: Slide count is updated consistently
All four slide-count sync points in `presentation.html` SHALL reflect 16 slides after this change.

#### Scenario: Navigation works
- **WHEN** the presenter navigates through all slides
- **THEN** all 16 slides are reachable and the progress bar reaches 100% on the final slide

### Requirement: Index slide jump target for 導入 is updated
The 導入 section card on the index slide SHALL jump to index 14 (was 13) after the new slide is inserted.

#### Scenario: Index card navigates correctly
- **WHEN** the presenter clicks the 導入 section card on the index slide
- **THEN** navigation lands on the 導入策略 slide
