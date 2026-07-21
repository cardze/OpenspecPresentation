## ADDED Requirements

### Requirement: Index slide appears as third slide
The presentation SHALL display a section index slide at position 3 (after presenter intro and cover), before the content slides.

#### Scenario: Index slide is third
- **WHEN** the user navigates to slide 3
- **THEN** the index slide with section cards is visible

### Requirement: Index slide displays five section cards
The index slide SHALL display exactly five clickable section cards: 問題, 流程, 實例, 評估, 導入 — each with a number, name, and one-line description.

#### Scenario: All five cards visible
- **WHEN** the index slide is displayed
- **THEN** five cards are visible, each showing a section number, Chinese name, and brief description

### Requirement: Clicking a section card jumps to its first slide
Each section card SHALL navigate the presentation to the first slide of that section when clicked.

#### Scenario: Jump to 問題
- **WHEN** the user clicks the 問題 card
- **THEN** the presentation navigates to Slide 4 (痛點)

#### Scenario: Jump to 流程
- **WHEN** the user clicks the 流程 card
- **THEN** the presentation navigates to Slide 5 (全景)

#### Scenario: Jump to 實例
- **WHEN** the user clicks the 實例 card
- **THEN** the presentation navigates to Slide 11 (實作範例)

#### Scenario: Jump to 評估
- **WHEN** the user clicks the 評估 card
- **THEN** the presentation navigates to Slide 12 (優勢)

#### Scenario: Jump to 導入
- **WHEN** the user clicks the 導入 card
- **THEN** the presentation navigates to Slide 14 (導入策略)

### Requirement: Index slide matches existing visual style
The index slide SHALL use the same CSS variables, font, and card visual language as existing slides.

#### Scenario: Style consistency
- **WHEN** the index slide is visible
- **THEN** it uses the same background, typography, and border styles as other slides
