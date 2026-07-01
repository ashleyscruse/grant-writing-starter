---
name: reviewer-builder
description: "Assembles the NSF review panel for a grant, runs the draft through each reviewer, synthesizes their reads, and saves the result. Use when a draft is ready for a critical read, or when the user asks to review, critique, or panel-test a proposal, or asks if it is ready to submit. Also use when the user mentions 'review my proposal,' 'reviewer panel,' 'mock panel,' or 'ready to submit?'"
---

# Reviewer Builder

Assemble a review panel for this grant, read the draft through each reviewer, then synthesize and save the result. Reviewing is a separate job from writing; this does not rewrite.

## Before you start

Read:
- `grants/{name}/solicitation.md` -- review criteria, program goals, required components, page limits, and formatting.
- `grants/{name}/proposal/` -- the current draft, and which version it is (`versions/vN.pdf`).
- `grants/{name}/evaluation.md` and `profile/` -- to check claims against the record.

## Run the panel

Run each of these reviewer skills on this grant. Each one grounds itself in `solicitation.md` and reviews the draft in its own lens, giving an NSF-style rating and comments tied to the review criteria.

- `reviewer-skeptic`
- `reviewer-generalist`
- `reviewer-subject-expert`
- `reviewer-program-officer`

For what reviewers look for, red flags, and common mistakes, see [reviewer-perspective.md](references/reviewer-perspective.md).

## Compliance check

Check the draft against the solicitation: required components present and in order, page limits and formatting met, numbers consistent across sections, and citations grounded in the `literature/` folder. A strong proposal that breaks a formatting rule gets returned unread.

## Synthesize and save

Combine the four reads into:
- Where they agree (fix these first).
- Where they conflict (the real tension to resolve).
- A prioritized list: what would sink it (compliance failures, missing criteria), then what lowers the score, then smaller fixes.

Save the whole panel review to `grants/{name}/proposal/reviews/vN-review.md`, matching the version reviewed. Never overwrite an earlier review; keep one per version so the researcher can see progress across rounds.

## What this skill does NOT do

- Draft or rewrite sections (that is `nsf-grant-writer`).
- Render or format the document (that is `latex-assistant`).
- Judge whether to pursue the grant (that is `grant-analyzer`).
