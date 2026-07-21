## ADDED Requirements

### Requirement: Presentation describes apply resume continuity
The presentation MUST explain that after implementation has started for an OpenSpec change, work continuity SHALL come from persisted change artifacts and task state, so a later session can continue with `opsx-apply`.

#### Scenario: Supervisor mode explains continuity as a governance benefit
- **WHEN** the viewer is in `supervisor` mode and reads the relevant presentation section
- **THEN** the presentation MUST communicate that work can resume after a session stops because progress is captured in the change workflow, not only in the prior conversation

#### Scenario: Dev mode explains continuity as artifact-backed resume behavior
- **WHEN** the viewer is in `dev` mode and reads the relevant presentation section
- **THEN** the presentation MUST communicate that `opsx-apply` can resume from current change state using proposal, design, specs, tasks, and completion status

### Requirement: Resume message preserves current presentation structure
Adding the resume continuity message MUST NOT require a new HTML file or a second presentation flow.

#### Scenario: Existing deck structure remains the same
- **WHEN** the resume continuity message is added to the presentation
- **THEN** the presentation MUST continue using the existing single-file deck, current audience mode toggle, and current slide navigation model

### Requirement: Resume message avoids implying chat-memory dependency
The presentation MUST frame continuation as workflow-state continuity rather than generic chat-memory persistence.

#### Scenario: Continuity wording stays artifact-centered
- **WHEN** the presentation describes resuming work after a session interruption
- **THEN** the wording MUST anchor the explanation in change artifacts, task state, or apply state instead of implying that continuation depends only on remembering prior chat text
