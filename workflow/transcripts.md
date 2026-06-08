---
status: draft
scope: transcript
sources:
  - ../templates/distilled-transcript.md
last_verified: 2026-06-08
confidence: low
---

# Transcript Distillation

Raw transcripts are not the knowledge base. They are evidence.

## Process

1. Store the raw transcript under `transcripts/raw/`.
2. Create a summary under `transcripts/distilled/` using `templates/distilled-transcript.md`.
3. Extract facts, decisions, preferences, unresolved claims, and pages to update.
4. Mark confidence for each extracted claim.
5. Promote only verified or user-confirmed facts into active KB pages.
6. Add uncertain claims to `decisions/open-questions.md`.

## Distilled Summary Must Include

- new facts
- decisions made
- user preferences or conventions
- claims needing verification
- KB pages to update
- source confidence

## Do Not

- Treat transcript wording as verified architecture.
- Index raw transcript text as if it were canonical documentation.
- Copy long conversational fragments into overview pages.
