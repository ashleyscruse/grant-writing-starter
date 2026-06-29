---
name: grant-advisor
description: "End-to-end intake for a grant opportunity: takes a solicitation URL or PDF, parses it, evaluates fit against your profile, decides whether to pursue, logs it to your tracker, and saves everything to a grant folder. Use when the user shares a solicitation (URL, PDF, or pasted text) and wants a go decision. Also use when the user says 'evaluate this grant,' 'should I apply,' 'should I pursue this,' 'is this worth it,' 'triage this opportunity,' or pastes a funding opportunity link and asks what to do with it."
---

# Grant Advisor

One command from a solicitation to a decision. Give it a URL or a PDF and it parses the opportunity, evaluates fit against the researcher's profile, decides whether to pursue, records the decision in the tracker, and saves everything into a grant folder. The researcher makes the final call; this does the legwork and writes it all down.

This skill orchestrates three others in order: `solicitation-review`, `grant-analyzer`, and `grant-organizer`. Run them as steps; do not duplicate their logic here.

## Input

One of:
- A URL to a funding opportunity or program page
- A PDF of an RFP / RFA / NOFO
- Pasted solicitation text
- A program name to look up

## Workflow

### 1. Ingest and name
Read the solicitation in full (fetch the URL, read the PDF, or use the pasted text). Derive a short, readable slug from the funder and program, for example `nsf-hbcu-eir` or `nih-r15`. Use that slug for the folder.

### 2. Create the grant folder
If `grants/{slug}/` does not exist, copy `grants/_TEMPLATE/` to `grants/{slug}/`.

### 3. Parse the solicitation (solicitation-review)
Follow the `solicitation-review` skill to extract the structured requirements brief and write it to `grants/{slug}/solicitation.md`: funder and program, key dates, eligibility, award size, review criteria (quoted), required components with page limits, and formatting rules.

### 4. Evaluate fit (grant-analyzer)
Follow the `grant-analyzer` skill. Read the `profile/` files plus the parsed `solicitation.md`, and write `grants/{slug}/evaluation.md`: fit by dimension, the gaps a reviewer would flag, and a recommendation. Be honest; a flattering evaluation wastes months.

### 5. Decide
From the evaluation, set one decision and put it at the very top of `evaluation.md`:

- **Pursue** — eligible, fit is real, and the gaps are addressable before the deadline.
- **Considering** — eligible with meaningful alignment, but significant gaps remain or it warrants a closer look or a conversation with the program officer.
- **Don't Pursue** — not eligible, or the fit and gaps make it a poor use of time.

### 6. Log it (grant-organizer)
Follow the `grant-organizer` skill to add or update this grant's row in `grants/grant-tracker.xlsx`: opportunity, funder, program, deadline, award range, fit rating, **decision** (Pursue / Considering / Don't Pursue), status (`Reviewing`), date reviewed, the `grants/{slug}/` folder, and a one-line note.

### 7. Report
Tell the researcher, briefly:
- The **decision** in one line.
- The **why** in two sentences.
- If Pursue or Considering, the **top gaps** to address.
- The **folder path** where everything was saved.

Then stop.

## The hard line

- **Stop at the decision.** Do not draft any proposal section here. Drafting is a separate, deliberate step (the `grant-writing` and `nsf-*` skills) the researcher chooses after a Pursue decision.
- **Be honest about fit and gaps.** Surface what a reviewer would mark down.
- **Never fabricate** requirements, dates, award amounts, or profile details. If the solicitation or profile does not say it, it stays unknown.

## What this skill does NOT do

- Write or render proposal sections (that is `grant-writing`, the `nsf-*` skills, and `latex-assistant`).
- Submit anything or contact a program officer.
- Decide *for* the researcher; it recommends and records. The researcher owns the go.
