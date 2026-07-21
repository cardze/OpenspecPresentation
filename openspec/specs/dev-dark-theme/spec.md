## ADDED Requirements

### Requirement: Mode-specific theme mapping
The presentation MUST map audience modes to fixed visual themes: `supervisor` mode SHALL use light theme and `dev` mode SHALL use dark theme.

#### Scenario: Supervisor mode applies light theme
- **WHEN** the active mode is `supervisor`
- **THEN** the page MUST render using light-theme color tokens

#### Scenario: Dev mode applies dark theme
- **WHEN** the active mode is `dev`
- **THEN** the page MUST render using dark-theme color tokens

### Requirement: Theme switch coupled with mode switch
Switching audience mode MUST update both copy and theme in the same interaction.

#### Scenario: Switch from supervisor to dev on current slide
- **WHEN** a viewer switches mode from `supervisor` to `dev`
- **THEN** the current slide MUST remain active and both copy and theme MUST update together

#### Scenario: Switch from dev to supervisor on current slide
- **WHEN** a viewer switches mode from `dev` to `supervisor`
- **THEN** the current slide MUST remain active and both copy and theme MUST update together

### Requirement: Theme persistence follows stored mode
On reload, the page MUST restore theme based on the persisted mode value.

#### Scenario: Persisted dev mode restores dark theme
- **WHEN** stored mode is `dev` and the page loads
- **THEN** the presentation MUST initialize in dark theme

#### Scenario: Storage failure fallback
- **WHEN** mode persistence is unavailable
- **THEN** the presentation MUST default to `supervisor` mode with light theme without breaking navigation

### Requirement: Dark theme readability
Dark theme MUST preserve readable contrast for primary UI surfaces including slide copy, cards, navigation controls, and evidence text.

#### Scenario: Copy remains readable in dark theme
- **WHEN** `dev` mode is active
- **THEN** heading, body, and evidence text MUST remain clearly legible against dark surfaces

#### Scenario: Controls remain distinguishable in dark theme
- **WHEN** `dev` mode is active
- **THEN** mode toggle, navigation buttons, and progress indicator MUST remain visually distinguishable and usable

### Requirement: Narrative structure remains unchanged
Theme changes MUST NOT alter slide count, order, or workflow sequence.

#### Scenario: Slide count unchanged after theme switch
- **WHEN** viewer toggles between `supervisor` and `dev`
- **THEN** total slide count MUST remain 12

#### Scenario: Workflow order unchanged after theme switch
- **WHEN** viewer toggles modes while navigating workflow slides
- **THEN** Explore, Propose, Apply, and Archive order MUST remain unchanged
