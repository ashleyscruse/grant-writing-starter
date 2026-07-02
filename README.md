# Grant Writing Starter

An AI workspace for writing NSF proposals, where the AI does the heavy lifting and you make the calls. You set up a short profile about yourself once, built straight from your CV, and from then on the same workflow gives you honest, grounded help on every grant: sizing up opportunities, drafting sections to the review criteria, and running a mock review panel before you submit.

> The biggest difference between researchers who get a real speedup from AI and those who don't is rarely the AI. It's whether their context is organized so the AI can use it. This workspace does that from the first hour, which also means less back-and-forth and lower cost.

## Start here

1. **Open it.** [SETUP.md](SETUP.md) gets the folder onto your computer and open in Claude Code. Say hi, and you'll meet **Sage**, your guide.
2. **Build your profile.** Drop your CV in `profile/me/` and tell Sage *"build my profile."* Sage reads your CV and asks a couple of things a CV can't answer. A few minutes, and the AI knows who you are.
3. **Use it.** [GUIDE.md](GUIDE.md) walks the whole workflow: find a grant, draft it, render it, review it.

## What's inside

Two kinds of files: the **context you fill in** (folders you see and edit) and the **machinery** that makes the AI behave (loaded automatically; you never open it).

| Path | What's there | Yours to edit? |
|---|---|---|
| `profile/` | Who you are. Drop your CV in `me/` and Sage builds your `profile.md` from it. Add your institution in `institutions/`, and any collaborators (also from their CV) in `collaborators/`. | **Yes** |
| `grants/` | One folder per grant: the solicitation, your fit evaluation, the team, `budget.xlsx`, a `literature/` folder for your sources, and the `proposal/` draft. `grant-tracker.xlsx` logs them all. | **Yes** |
| `GUIDE.md` · `SETUP.md` | How to use it, and how to open it. | Read |
| `CLAUDE.md` · `.claude/skills/` | The context and skills the AI loads on its own. | Machinery |

## The workflow, at a glance

You bring the decisions and the evidence; the AI accelerates each step. Full detail in [GUIDE.md](GUIDE.md).

1. **Profile** — drop your CV, Sage builds it. Your reusable context.
2. **Find a grant** — paste a URL or PDF: *"should I pursue this?"* You get an honest fit decision, a grant folder, and a tracker row.
3. **Write** — *"draft my Project Description."* Sections written to the NSF grant type and review criteria, in your voice.
4. **Render** — *"render it."* A compliant PDF, plus a feedback file for your notes.
5. **Review** — *"review my draft."* A panel of reviewers scores it and checks compliance before you submit.

## The skills

Loaded automatically, you just talk in plain English:

- **Sage** — sets you up and builds your profile.
- **cv-import** — turns a CV into a profile (yours, or a collaborator's).
- **grant-advisor** — *"should I pursue this?"* from a URL or PDF, end to end.
- **solicitation-review · grant-analyzer · grant-organizer** — parse a solicitation, judge fit, log the tracker.
- **nsf-grant-writer** — draft and revise sections to the grant type and criteria.
- **reviewer-builder** (with its skeptic, generalist, subject-expert, and program-officer panel) — mock review and compliance check.
- **latex-assistant** — set up LaTeX, keep formatting compliant, render PDFs.

## Opening it

This is a folder of markdown. Open it in **Claude Code** (the desktop app). Claude Code reads `CLAUDE.md` and `.claude/skills/` on its own, so you only ever touch `profile/` and `grants/`.

---

## Credits

Created by **Ashley Scruse, Ph.D.** © 2026 Ashley Scruse. All rights reserved. See [NOTICE](NOTICE).
