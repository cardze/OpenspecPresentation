## ADDED Requirements

### Requirement: Presentation SHALL include an example page
The presentation MUST include one dedicated example page that demonstrates how OpenSpec is applied in a concrete project scenario.

#### Scenario: Example page exists in deck
- **WHEN** the presentation is rendered
- **THEN** the deck MUST contain an example page section with visible title and structured content blocks

#### Scenario: Example page follows CLI explanation
- **WHEN** a viewer advances through the workflow and CLI section
- **THEN** the next page MUST present the concrete example before the final summary section

### Requirement: Deck size SHALL be 13 slides
The presentation MUST use 13 slides after adding the example page.

#### Scenario: Counter reflects 13-slide deck
- **WHEN** the viewer opens the first slide
- **THEN** the counter MUST display `1 / 13`

#### Scenario: Navigation reaches slide 13
- **WHEN** the viewer navigates to the end of the deck
- **THEN** the last slide index and progress MUST correspond to slide 13

### Requirement: Example page SHALL support audience modes
The example page MUST provide mode-specific copy for both `supervisor` and `dev`.

#### Scenario: Supervisor mode example copy
- **WHEN** mode is `supervisor`
- **THEN** the example page copy MUST emphasize decision impact and business clarity

#### Scenario: Dev mode example copy
- **WHEN** mode is `dev`
- **THEN** the example page copy MUST emphasize technical flow, commands, and implementation outcomes

### Requirement: Existing mode/theme behaviors SHALL remain intact
Adding the example page MUST NOT break current mode toggle behavior or mode-driven theme behavior.

#### Scenario: Mode switch on example page
- **WHEN** a viewer switches `supervisor` and `dev` on the example page
- **THEN** copy and theme MUST update together without resetting slide position

#### Scenario: Mode persistence after reload
- **WHEN** a viewer reloads after selecting a mode
- **THEN** the presentation MUST restore the selected mode and corresponding theme in the 13-slide deck

### Requirement: Workflow narrative SHALL remain ordered
The full narrative flow MUST remain left-to-right and preserve Explore → Propose → Apply → Archive sequence.

#### Scenario: Workflow order verification
- **WHEN** a viewer traverses the workflow slides and example page
- **THEN** Explore, Propose, Apply, and Archive MUST appear in their original order and the example page MUST not reorder them

#### Scenario: Final summary remains a summary
- **WHEN** the viewer reaches the final slide
- **THEN** the final slide MUST remain a summary/decision page rather than a new feature explanation page
