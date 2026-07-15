## ADDED Requirements

### Requirement: Presentation language and audience fit
The presentation MUST use Traditional Chinese throughout, and the messaging SHALL be understandable by managers and PMs without relying on deep engineering jargon.

#### Scenario: All visible copy is Traditional Chinese
- **WHEN** a viewer navigates through all presentation slides
- **THEN** all titles, labels, and body copy MUST be written in Traditional Chinese

#### Scenario: Manager-facing summary is present
- **WHEN** the viewer reaches the concluding slides
- **THEN** the presentation SHALL provide a concise decision-oriented summary for management audiences

### Requirement: Left-to-right narrative flow
The presentation SHALL communicate a clear left-to-right progression from problem framing to OpenSpec workflow, trade-offs, and adoption guidance.

#### Scenario: Visual progression is explicit
- **WHEN** a viewer moves between slides or sections
- **THEN** the interface MUST provide clear directional cues that indicate rightward progression

#### Scenario: Workflow sequence is preserved
- **WHEN** the workflow section is displayed
- **THEN** the content SHALL present Explore, Propose, Apply, and Archive in that exact order

### Requirement: Illustration-first communication
Each slide MUST prioritize illustrations, diagrams, or visual cards over long-form text, with text used only for key messages.

#### Scenario: Each slide includes a primary visual
- **WHEN** any slide is rendered
- **THEN** it MUST include at least one primary illustration or diagram that carries the main message

#### Scenario: Text remains concise
- **WHEN** slide content is authored
- **THEN** the slide SHALL avoid dense paragraphs and keep copy focused on short, high-signal statements

### Requirement: Repository-grounded OpenSpec explanation
The presentation MUST reflect OpenSpec behaviors evidenced by this repository, including schema-driven flow and artifact lifecycle.

#### Scenario: Workflow explanation maps to repo artifacts
- **WHEN** the presentation describes Propose, Apply, and Archive
- **THEN** it SHALL align with repository evidence such as prompts, skills, and schema configuration

#### Scenario: Capability claims are bounded by available evidence
- **WHEN** benefits and limitations are presented
- **THEN** claims MUST avoid unsupported external metrics and remain grounded in observable repository context

### Requirement: CLI workflow demonstration slide
The presentation SHALL include one non-live CLI demonstration slide that explains key command stages for proposing and progressing a change.

#### Scenario: CLI slide is explicitly non-live
- **WHEN** the CLI demonstration slide is shown
- **THEN** it MUST clearly indicate that the commands are illustrative and not a live terminal demo

#### Scenario: Command stages are understandable
- **WHEN** a manager or PM reads the CLI slide
- **THEN** they SHALL be able to understand command purpose at a high level without implementation detail
