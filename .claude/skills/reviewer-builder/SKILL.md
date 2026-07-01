---
name: reviewer-builder
description: "Builds a panel of NSF-style reviewers from the solicitation and reads a proposal draft through each, then synthesizes what to fix before submission. Use when a draft is ready for a critical read, or when the user asks to review, critique, or panel-test a proposal, or asks if it is ready to submit. Also use when the user mentions 'review my proposal,' 'reviewer panel,' 'mock panel,' 'read it as a reviewer,' or 'ready to submit?'"
---

# Reviewer Builder

Build a panel from the solicitation, not a generic reviewer, and read the draft through each one. Reviewing is a separate job from writing: this finds what is weak, unsupported, missing, or noncompliant and reports it. It does not rewrite.

## Before you start

Read:
- `grants/{name}/solicitation.md` -- review criteria, program goals, required components, page limits, and formatting. The panel is built from this.
- `grants/{name}/proposal/` -- the current draft.
- `grants/{name}/evaluation.md` and `profile/` -- to check claims against the record.

## Build the panel

Create these four reviewers, each grounded in the solicitation. Give each the actual review criteria (Intellectual Merit, Broader Impacts, and any program-specific criteria) and have each score and comment in its own voice.

1. **Skeptic** -- reads to refute. Hunts unsupported claims, overreach, vague methods, and hand-waving. Defaults to "not convinced" and makes the draft earn it.
2. **Gen pop** -- a smart reader with no expertise in this subfield (a real NSF panel includes one). Tests clarity: can they follow the significance, the plan, and the Broader Impacts without jargon? Flags anything only an insider would understand.
3. **Subject matter expert** -- deep in the field. Tests rigor, methodology, and novelty, whether it advances the field, and flags missing prior work.
4. **Program officer** -- reads for fit to the program's mission and goals, taken from the solicitation's Introduction and Program Description. Does this advance what the program funds? (Optional: the researcher can drop recent awards or program priorities into the grant folder to sharpen this read; it is not required.)

## Run and synthesize

Each reviewer gives an NSF-style rating and specific comments tied to the criteria. Then synthesize:
- Where they agree (fix these first).
- Where they conflict (the real tension to resolve).
- A prioritized list: what would sink it (compliance failures, missing criteria), then what lowers the score, then smaller fixes.

Also run the compliance check against the solicitation: required components present and in order, page limits and formatting met, numbers consistent across sections, and citations grounded in the `literature/` folder. A strong proposal that breaks a formatting rule gets returned unread.

For what reviewers look for, red flags, and common mistakes, see [reviewer-perspective.md](references/reviewer-perspective.md).

## Output

Report the panel: each reviewer's rating and key points, then the synthesis and the prioritized fixes, each pointed to a specific section. Hand the fixes off; `nsf-grant-writer` rewrites and `latex-assistant` renders.

## What this skill does NOT do

- Draft or rewrite sections (that is `nsf-grant-writer`).
- Render or format the document (that is `latex-assistant`).
- Judge whether to pursue the grant (that is `grant-analyzer`).
