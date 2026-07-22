## Context

The speech script was composed during an explore session, covering all 15 slides of the presentation in Traditional Chinese at approximately 12–14 minutes. It lives only in the conversation history. A persistent Markdown file makes it easy to print, share, or edit independently of the codebase.

## Goals / Non-Goals

**Goals:**
- Write the full script to `SPEECH.md` at the project root
- Structure by slide with clear headings so the presenter can navigate quickly during practice
- Include a timing note at the top

**Non-Goals:**
- Translating to other languages
- Embedding the script in the HTML presentation itself

## Decisions

**`SPEECH.md` at project root** — Easy to find, outside the `openspec/` directory so it reads as a human document rather than a workflow artifact. Alternative (`docs/speech.md`) was rejected as unnecessary extra nesting for a single file.

**Per-slide `###` headings** — Matches the slide kicker labels (e.g., `### Slide 4｜痛點`) so the presenter can find their place instantly.
