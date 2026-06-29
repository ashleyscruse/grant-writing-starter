# Grant Writing Starter

A starter workspace for finding, evaluating, and writing grant proposals with AI doing the heavy lifting. Clone it, fill in a short profile about yourself, and use AI tools (Claude Code, Cursor, Claude on the web) to evaluate opportunities honestly and draft proposal sections that map to the funder's review rubric.

> The biggest difference between researchers who get large speedups from AI and those who don't is rarely the AI. It's whether their context is organized so the AI can use it. This workspace solves that from the first hour.

## How to use this during the accelerator

1. **Make it yours.** On GitHub, **Fork** it (or **Use this template**) to create a copy under your own account. Your work lives in your repo.
2. **Want help?** Add `ashleyscruse` as a collaborator on your copy (Settings → Collaborators). That lets me look when you're stuck. Your work stays yours.
3. **Pull updates.** If shared materials get added during the week:
   ```bash
   git remote add upstream <starter-repo-url>
   git pull upstream main
   ```

**Start here:** [**SETUP.md**](SETUP.md) gets the repo onto your machine and open in your tool. Once it's open, say hi — you'll meet **Sage**, your guide, who walks you through filling in your profile.

## The workflow

Five stages. AI accelerates each one; you make every decision between them.

| Stage | You provide | The AI helps | Output |
|---|---|---|---|
| 1 · Foundation | your profile (`profile/`) | Sage interviews you and fills it in | a reusable knowledge base |
| 2 · Opportunity | a solicitation (RFP/NOFO) | `grant-analyzer`: honest fit, gaps, go/no-go | `grants/{name}/evaluation.md` |
| 3 · Strategy | the chosen grant + team | structure the project concept and aims | project concept + `team.md` |
| 4 · Drafting | your decisions and evidence | `grant-writing`: sections mapped to the rubric | drafted sections in `proposal/` |
| 5 · Review | the draft + the solicitation | reviewer-perspective + compliance check | submission-ready draft |

A typical loop:

1. Fill in your profile once (Sage helps).
2. Paste a solicitation: *"Evaluate this opportunity for me."* → honest evaluation.
3. If you're a go, set up a grant folder and a `team.md`.
4. *"Draft the Statement of Need for this grant using my profile and the team."* → section draft. You review and decide; the AI accelerates.

## Structure

There are two kinds of files: the **context you fill in** (visible folders you can see and edit) and the **machinery** that makes the AI behave (Claude Code loads it automatically; you never need to open it).

| Path | What's there | Yours to edit? |
|---|---|---|
| `profile/` | Who you are. `you/` (identity, research, teaching-mentoring, grant-history + your CV/biosketch), `collaborators/` (one folder per person), `institutions/` (one folder per institution). Sage helps you fill it. | **Yes** |
| `grants/` | One folder per grant: `solicitation.md`, `evaluation.md`, `team.md`, and `proposal/` (your draft, with `versions/` and `feedback/`). Copy `_TEMPLATE/` to start one; see the worked `EXAMPLE-` folder. | **Yes** |
| `README.md` | This file: how to use the workspace. | Read it |
| `CLAUDE.md` | Context the AI reads first. | Machinery |
| `.claude/skills/` | The AI's instructions: `setup-guide` (Sage), `grant-analyzer`, `grant-writing`. | Machinery |

## Works in any AI tool

This is just a folder of markdown. Open it in **Claude Code** (the desktop app or CLI), **Cursor**, **VS Code**, or point **Claude on the web / desktop** at it. Claude Code reads `CLAUDE.md` and `.claude/skills/` on its own, so you only ever touch `profile/` and `grants/`.

---

## Credits

Created by **Ashley Scruse, Ph.D.** — [ashleyscruse.com](https://ashleyscruse.com). © 2026 Ashley Scruse. All rights reserved. See [NOTICE](NOTICE).
