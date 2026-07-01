# Grant Writing Starter

A context-driven workspace for writing NSF proposals with AI doing the heavy lifting. You set up a short profile about yourself once, and from then on the same workflow gives you honest, grounded help on every grant: evaluating opportunities, drafting sections to the review criteria, and running a mock review panel before you submit.

> The biggest difference between researchers who get large speedups from AI and those who do not is rarely the AI. It is whether their context is organized so the AI can use it. This workspace solves that from the first hour, which also means less back-and-forth and lower token cost.

## Start here

1. **Get it open:** [**SETUP.md**](SETUP.md) gets the folder onto your machine and open in your tool, then you say hi and meet **Sage**, your guide.
2. **Use it:** [**GUIDE.md**](GUIDE.md) walks the whole workflow: build your profile, find a grant, draft it, render it, review it.

## What is inside

There are two kinds of files: the **context you fill in** (folders you can see and edit) and the **machinery** that makes the AI behave (loaded automatically; you never open it).

| Path | What is there | Yours to edit? |
|---|---|---|
| `profile/` | Your context. `me/` (identity, research, teaching-mentoring, grant-history, plus your CV or biosketch), `institutions/` (one per institution: profile, strategic plan, facilities), `collaborators/` (one per person). Sage helps you fill it. | **Yes** |
| `grants/` | One folder per grant: `solicitation.md`, `evaluation.md`, `team.md`, `budget.xlsx`, a `literature/` folder for your sources, and `proposal/` (the draft, with `versions/`, `feedback/`, and `reviews/`). `grant-tracker.xlsx` logs every grant. Copy `_TEMPLATE/` to start one, or let `grant-advisor` create it. | **Yes** |
| `GUIDE.md` | How to use the workspace, step by step. | Read it |
| `SETUP.md` | How to get it open. | Read it |
| `CLAUDE.md` | Context the AI reads first. | Machinery |
| `.claude/skills/` | The AI's skills: Sage, `grant-advisor`, `nsf-grant-writer`, `reviewer-builder`, `latex-assistant`, and more. | Machinery |

## The workflow, at a glance

You provide the decisions and the evidence; the AI accelerates each step. Full detail is in [GUIDE.md](GUIDE.md).

1. **Profile** -- fill it in once (Sage helps). Your reusable context.
2. **Find a grant** -- paste a URL or PDF: *"should I pursue this?"* You get an honest fit decision, a grant folder, and a tracker row.
3. **Write** -- *"draft my Project Description."* Sections drafted to the NSF grant type and review criteria, in your voice.
4. **Render** -- *"render it."* A PDF plus a feedback file for your notes.
5. **Review** -- *"review my draft."* A panel of reviewers scores it and checks compliance before you submit.

## Works in any AI tool

This is a folder of markdown. Open it in **Claude Code** (the desktop app or CLI), **Cursor**, or **VS Code**. Claude Code reads `CLAUDE.md` and `.claude/skills/` on its own, so you only ever touch `profile/` and `grants/`.

---

## Credits

Created by **Ashley Scruse, Ph.D.**, [ashleyscruse.com](https://ashleyscruse.com). © 2026 Ashley Scruse. All rights reserved. See [NOTICE](NOTICE).
