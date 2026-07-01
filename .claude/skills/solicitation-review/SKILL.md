---
name: solicitation-review
description: "Parses a grant solicitation (RFP/RFA/NOFO/program page) into a structured requirements brief: funder and program, key dates, eligibility, award size, review criteria, required components, page limits, and formatting rules. Use when the user shares a solicitation and wants it broken down, summarized, or turned into a requirements checklist, or before evaluating fit or drafting. Also use when the user mentions 'review this solicitation,' 'break down this NOFO,' 'what does this RFP require,' 'summarize this opportunity,' 'requirements,' 'page limits,' 'review criteria,' or 'submission requirements.'"
---

# Solicitation Review

Turn a raw solicitation into a clean, structured requirements brief that the rest of the workflow runs on. This is the first step in the Opportunity stage, before fit analysis and well before drafting. Get the requirements right once, and every later step (fit, drafting, compliance) has a reliable source to check against.

## When to run

- The researcher pastes or links a solicitation and wants to understand what it asks for.
- Before `grant-analyzer` (fit) or `nsf-grant-writer` (drafting): both work better against a parsed brief than against raw solicitation text.

## Input

One of:
- A URL to a funding opportunity / program page
- A PDF of an RFP/RFA/NOFO
- Pasted solicitation text
- A program name to look up

Read the source in full before extracting. If a section is unclear or missing from the source, note it as an open question rather than guessing.

## Workflow

1. **Read the whole solicitation.** Do not summarize from the abstract alone; requirements hide in the middle.
2. **Extract into the requirements brief** (fields below). Quote the review criteria and page limits verbatim; paraphrasing loses points later.
3. **Flag gaps and ambiguities.** Anything not stated becomes an "open question for the program officer," not an assumption.
4. **Save** the brief to `grants/{name}/solicitation.md`. If the grant folder does not exist, copy `grants/_TEMPLATE/` to `grants/{name}/` and write the brief into its `solicitation.md`.

## The requirements brief

Capture all of these that the solicitation specifies:

- **Funder and program** — agency/foundation, program name, division
- **Opportunity number / cycle** — solicitation number, fiscal year, recurring vs one-time
- **Key dates** — LOI/preliminary deadline, full proposal deadline, anticipated award date, project start
- **Eligibility** — PI status and career stage, institution type (HBCU, MSI, PUI, R1), citizenship/residency, limits on number of proposals per PI/institution
- **Award information** — award size or range, project duration, expected number of awards, cost-share/match requirements
- **Review criteria** — quote each criterion and its weight or scoring; note any agency-specific criteria (for NSF: Intellectual Merit and Broader Impacts)
- **Required components** — every required document, each with its page limit and who prepares it (e.g., Project Summary 1 pg, Project Description 15 pg, DMP 2 pg, Biosketch, Budget Justification, Current & Pending, Facilities, letters)
- **Formatting rules** — margins, font family and size, line spacing, citation style (cite the source: NSF PAPPG, agency guide, or the solicitation itself)
- **Submission mechanics** — Research.gov / Grants.gov / agency portal, registration requirements, who submits (PI vs SPO)
- **Restrictions and exclusions** — disqualifying conditions, prohibited costs, scope limits
- **Open questions** — anything the solicitation does not resolve, to confirm with the program officer

## Hand off

- To **grant-analyzer** to judge fit against the profile.
- To **grant-organizer** to log the opportunity in the tracker.
- To **nsf-grant-writer** to draft each required component against the quoted review criteria and page limits.

## What this skill does NOT do

- Judge fit or recommend go/no-go (that is `grant-analyzer`).
- Draft any proposal section (that is `nsf-grant-writer`).
- Invent requirements the solicitation does not state. Unknown stays unknown until confirmed.
