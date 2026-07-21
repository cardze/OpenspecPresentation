## ADDED Requirements

### Requirement: Adoption slide uses no jargon
The 導入策略 slide SHALL contain none of the following terms: "Pilot", "Team", "Org", "跨職能小隊", "review gate", "回灌".

#### Scenario: No jargon visible
- **WHEN** the 導入策略 slide is displayed
- **THEN** none of the banned jargon terms appear in any visible text

### Requirement: Adoption slide three steps are plain Chinese
The three stage cards SHALL use plain, self-explanatory Chinese titles that require no prior knowledge to understand.

#### Scenario: First card is plain
- **WHEN** the 導入策略 slide is displayed
- **THEN** the first card reads "先試一個專案" with description "用 OpenSpec 跑一次完整流程"

#### Scenario: Second card is plain
- **WHEN** the 導入策略 slide is displayed
- **THEN** the second card reads "推給組員一起用" with description "建立共同的提案與任務習慣"

#### Scenario: Third card is plain
- **WHEN** the 導入策略 slide is displayed
- **THEN** the third card reads "固定成小組標準" with description "每次交付都有規格可追溯"

### Requirement: Adoption slide heading is conversational
The `.copy` heading SHALL be updated to a plain conversational tone.

#### Scenario: Heading reads naturally
- **WHEN** the 導入策略 slide is displayed
- **THEN** the h2 heading reads "怎麼開始？三步走。"
