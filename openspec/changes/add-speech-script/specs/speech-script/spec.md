## ADDED Requirements

### Requirement: Speech script file exists at project root
The project SHALL contain a `SPEECH.md` file at the repository root with the full Traditional Chinese presentation script.

#### Scenario: File is present
- **WHEN** a presenter opens the repository
- **THEN** `SPEECH.md` exists at the root level and is readable

### Requirement: Script covers all 15 slides
`SPEECH.md` SHALL contain a dedicated section for each of the 15 slides, headed with the slide number and section name.

#### Scenario: All slides represented
- **WHEN** `SPEECH.md` is opened
- **THEN** sections for all 15 slides (報告人 through 結語) are present in order

### Requirement: Script is written in Traditional Chinese
All spoken content in `SPEECH.md` SHALL be written in Traditional Chinese.

#### Scenario: Language check
- **WHEN** `SPEECH.md` is read
- **THEN** all body text uses Traditional Chinese characters and phrasing

### Requirement: Script includes timing estimate
`SPEECH.md` SHALL include a note at the top indicating the estimated total speaking time (~12–14 minutes).

#### Scenario: Timing note visible
- **WHEN** `SPEECH.md` is opened
- **THEN** a timing estimate appears near the top of the file
