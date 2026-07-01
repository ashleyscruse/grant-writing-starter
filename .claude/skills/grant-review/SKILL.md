---
name: grant-review
description: "Reviews a proposal draft the way an NSF panel would, then runs a compliance and formatting check against the solicitation, so problems get fixed before a panel finds them. Use when a draft is ready for a critical read, or when the user asks to review, critique, or check a proposal, or asks if it is ready to submit. Also use when the user mentions 'review my proposal,' 'read it as a reviewer,' 'reviewer perspective,' 'compliance check,' or 'ready to submit?'"
---

# Grant Review

Reviewing is a different job from writing. This skill reads a finished or near-finished draft with a skeptical reviewer's eye and checks it against the solicitation. It does not draft or rewrite; it finds what is weak, unsupported, missing, or noncompliant and reports it for the researcher and the `nsf-grant-writer` skill to fix.

## Before you start

Read the grant's context:
- `grants/{name}/solicitation.md` -- review criteria, required components, page limits, and formatting.
- `grants/{name}/proposal/` -- the current draft (`main.tex` and its rendered version).
- `grants/{name}/evaluation.md` and `profile/` -- to check claims against the record.

## Two passes

### 1. Reviewer perspective

Read as a skeptical NSF panelist. For what reviewers look for, the red flags, and common mistakes, see [reviewer-perspective.md](references/reviewer-perspective.md). Score the draft against each review criterion (Intellectual Merit, Broader Impacts, and any program-specific criteria) and say what you would mark down: unsupported claims, vague methods, thin Broader Impacts, missing criteria, overreach.

### 2. Compliance and formatting

Check the draft against the solicitation:
- Every required component is present and in the required order.
- Page limits, font, spacing, and margins meet the solicitation. A strong proposal that breaks a formatting rule gets returned unread.
- Every review criterion is addressed explicitly.
- Numbers, dates, and figures are consistent across sections; every narrative activity has a budget line and every line ties back to the narrative.
- Citations are grounded in the grant's `literature/` folder and the references are complete.

## Output

Report findings as a prioritized list: first what would sink the proposal (compliance failures, missing criteria), then what would lower the score (weak or unsupported sections), then smaller fixes. Point to the specific section. Hand the fixes off; the writing and rendering happen elsewhere.

## What this skill does NOT do

- Draft or rewrite sections (that is `nsf-grant-writer`).
- Render or format the document (that is `latex-assistant`).
- Judge whether to pursue the grant (that is `grant-analyzer`).
