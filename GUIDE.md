# How to use this workspace

A context-driven workspace for writing NSF proposals with AI. You set up your context once, and from then on the same workflow gives you grounded, honest help on every grant. This guide walks the whole loop.

## The idea: it is not the AI, it is the context

Most people use AI for grants by pasting into a chat box and getting generic help, because the AI does not know who they are. This workspace fixes that at the root. You fill in a short profile once (who you are, your institution, your record), and every evaluation and every draft after that is grounded in your real context instead of guessing. That is what makes the output good, and it is also what saves you money: less back-and-forth, fewer re-explanations, fewer wasted tokens.

You only ever touch two folders: `profile/` (your context) and `grants/` (your grants). Everything in `.claude/` and `CLAUDE.md` is machinery the AI loads on its own.

## Getting it open

1. On the repo's green **Code** button, choose **Download ZIP**, then unzip it.
2. Open the folder in **Claude Code** (or Cursor or VS Code).
3. In Claude Code, just say **hi**. You will meet **Sage**, your setup guide.

(A ZIP is a snapshot. To get materials added later, re-download.)

## Step 1: Build your context (your profile)

Say hi and Sage walks you through it, one file at a time. You are filling in:

- `profile/me/` -- who you are: `profile.md`, `profile.md`, `profile.md`, `profile.md`. Drop your CV or biosketch in this folder too.
- `profile/institutions/` -- one folder per institution. Fill its `profile.md`, and drop in the institution's strategic plan and facilities document. This sets eligibility and gives the AI what to align your proposals to.
- `profile/collaborators/` -- one folder per collaborator (add these when a specific grant needs them).

You fill this in once and reuse it on every proposal for years. Be specific: real numbers, full citations, honest gaps.

## Step 2: Find a grant

Paste a solicitation URL or PDF and say **"should I pursue this?"** The `grant-advisor` skill parses it, evaluates fit against your profile, decides **Pursue, Considering, or Don't Pursue**, logs it in your tracker, and creates a `grants/{name}/` folder with the parsed `solicitation.md` and an honest `evaluation.md`. It stops at the decision; it does not start writing.

If you want the AI to cite real sources when you draft, drop the papers into that grant's `literature/` folder.

## Step 3: Write it

Once you decide to pursue, fill in `grants/{name}/team.md` (who is on the proposal), then ask for a section: **"draft my Project Description"** (or Project Summary, Broader Impacts, Facilities, Data Management Plan, Budget Justification). The `nsf-grant-writer` skill drafts it to the NSF grant type and the review criteria, in your voice, grounded in your profile and your `literature/`. You own the argument; the AI accelerates the writing.

## Step 4: Build the PDF

Say **"render it."** The `latex-assistant` skill compiles the draft to `proposal/versions/v1.pdf` and creates a matching `feedback/v1-feedback.md` with a heading per section. Read the PDF, type your notes into that feedback file, and say **"there's feedback on v1."** It revises and renders `v2.pdf`.

## Step 5: Review it

When a version is ready, say **"review my draft"** or **"am I ready to submit?"** The `reviewer-builder` skill runs a panel built from the solicitation: a skeptic, a non-specialist, a subject matter expert, and the program officer. Each scores it, then the skill synthesizes their reads, runs a compliance check, and saves it all to `proposal/reviews/v1-review.md`.

## Track everything

`grants/grant-tracker.xlsx` logs every grant you review: agency, deadlines, whether you are PI, amount, fit, decision, and status. Ask **"what am I tracking?"** to see your pipeline. The AI fills the parts it can derive; you fill the operational calls (PI, routing, target submit).

## The skills, and what to say

You never open these; you trigger them by asking. In order of use:

- `setup-guide` (Sage): fills your profile. *"hi"*
- `grant-advisor`: URL or PDF to a go decision, a folder, and a tracker row. *"should I pursue this?"*
- `nsf-grant-writer`: drafts a section to the type and criteria. *"draft my Broader Impacts"*
- `latex-assistant`: compiles and versions the PDF. *"render it"*
- `reviewer-builder`: runs the review panel. *"review my draft"*
- `grant-organizer`: maintains the tracker. *"what am I tracking?"*

(Under the hood, `grant-advisor` uses `solicitation-review` and `grant-analyzer`, and `reviewer-builder` runs the four reviewer personas. You do not call those directly.)

## The two hard lines

- Do not start writing until fit is real and you have decided to pursue.
- Do not submit until you have done a review pass and a compliance check.
