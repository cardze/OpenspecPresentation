## ADDED Requirements

### Requirement: Artifact cards flip on hover
The three artifact cards (proposal.md, design.md, tasks.md) on the Propose slide SHALL perform a 3D flip animation when hovered, revealing a back face.

#### Scenario: Card flips on hover
- **WHEN** the user hovers the cursor over an artifact card
- **THEN** the card performs a smooth 3D flip (≈500ms) to reveal the back face

#### Scenario: Card returns on mouse leave
- **WHEN** the user moves the cursor away from the card
- **THEN** the card flips back to the front face

### Requirement: Back face shows Traditional Chinese example content
Each card's back face SHALL display a short Traditional Chinese example snippet representing real content from that artifact type.

#### Scenario: proposal.md back content
- **WHEN** the proposal.md card is flipped
- **THEN** the back face shows a `## 為什麼` header with a brief example motivation in Traditional Chinese

#### Scenario: design.md back content
- **WHEN** the design.md card is flipped
- **THEN** the back face shows a `## 設計決策` header with an example decision and rationale in Traditional Chinese

#### Scenario: tasks.md back content
- **WHEN** the tasks.md card is flipped
- **THEN** the back face shows example `- [x]` and `- [ ]` checklist lines in Traditional Chinese

### Requirement: Flip is scoped to Propose slide cards only
The flip interaction SHALL only apply to cards with the `.flip-card` class and SHALL NOT affect `.value-card` elements on other slides.

#### Scenario: Other slides unaffected
- **WHEN** the user hovers over a `.value-card` on the 優勢 or 風險 slides
- **THEN** no flip animation occurs
