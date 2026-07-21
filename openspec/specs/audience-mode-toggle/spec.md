## ADDED Requirements

### Requirement: Presentation SHALL support audience mode toggle
The presentation MUST provide two audience modes, `supervisor` and `dev`, within the same HTML document.

#### Scenario: Toggle control is available
- **WHEN** the presentation page is loaded
- **THEN** the UI MUST show a discoverable control to switch between `supervisor` and `dev` modes

#### Scenario: Mode label is explicit
- **WHEN** a mode is selected
- **THEN** the active mode MUST be visually indicated in the interface

### Requirement: Mode switch SHALL update content without resetting slide position
Switching modes MUST update the current slide text content while preserving the current slide index and navigation state.

#### Scenario: Switch mode on slide 8
- **WHEN** a viewer switches from `supervisor` to `dev` while viewing slide 8
- **THEN** slide 8 MUST remain active and only mode-dependent copy changes

#### Scenario: Navigation state is preserved
- **WHEN** the mode is switched
- **THEN** progress indicators and stage labels MUST remain consistent with the current slide position

### Requirement: Both modes SHALL preserve the same narrative structure
Both audience modes MUST use the same 12-slide order and the same workflow sequence (Explore, Propose, Apply, Archive).

#### Scenario: Workflow order remains unchanged
- **WHEN** a viewer compares supervisor and dev modes
- **THEN** workflow slides MUST appear in the same order in both modes

#### Scenario: Slide count remains 12
- **WHEN** mode is switched
- **THEN** total slide count MUST remain 12

### Requirement: Mode preference SHALL persist across reload
The selected audience mode MUST be persisted locally so that reloading the page restores the last selected mode.

#### Scenario: Restore dev mode after refresh
- **WHEN** a viewer selects `dev` mode and reloads the page
- **THEN** the presentation MUST initialize in `dev` mode

#### Scenario: Storage unavailable fallback
- **WHEN** local storage is unavailable or fails
- **THEN** the presentation MUST fall back to `supervisor` mode without breaking navigation

### Requirement: Mode-specific copy SHALL include evidence context
Each slide MUST provide audience-appropriate copy and evidence text for both modes.

#### Scenario: Supervisor copy remains decision-oriented
- **WHEN** `supervisor` mode is active
- **THEN** slide copy MUST use concise, non-jargon language focused on decision-making

#### Scenario: Dev copy remains implementation-oriented
- **WHEN** `dev` mode is active
- **THEN** slide copy MUST include technical context such as artifacts, states, or command semantics
