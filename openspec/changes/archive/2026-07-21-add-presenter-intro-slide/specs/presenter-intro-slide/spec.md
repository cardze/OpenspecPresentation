## ADDED Requirements

### Requirement: Presenter intro slide is the first slide
The presentation SHALL display a dedicated intro slide as the first slide in the deck, before the cover slide.

#### Scenario: Intro slide appears first
- **WHEN** the presentation loads
- **THEN** the first visible slide is the presenter intro slide, not the cover

### Requirement: Intro slide displays topic without label
The intro slide SHALL display the presentation topic ("OpenSpec 優缺點") as a heading with no label prefix.

#### Scenario: Topic rendered as heading
- **WHEN** the intro slide is visible
- **THEN** "OpenSpec 優缺點" appears as the primary heading (`h2`)
- **THEN** no label text (e.g., "科目：" or "主題：") precedes it

### Requirement: Intro slide displays group and name
The intro slide SHALL display the presenter's group ("外匯財會組") and name ("王上澤") as muted metadata below the topic.

#### Scenario: Group and name visible
- **WHEN** the intro slide is visible
- **THEN** "組別：外匯財會組" and "姓名：王上澤" are both displayed

### Requirement: Presenter info removed from cover slide
The `.presenter-info` span inside Slide 1 (cover)'s kicker SHALL be removed.

#### Scenario: Cover kicker is clean
- **WHEN** the cover slide is visible
- **THEN** the kicker shows only "Slide 2 / 封面" with no presenter info span
