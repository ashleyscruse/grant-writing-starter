# Grants

One folder per grant you are pursuing. Your `profile/` says who you are; each folder here holds everything specific to **one proposal**.

## Start a new grant

Copy the `_TEMPLATE/` folder and rename it for the opportunity (no spaces), e.g. `NSF-HBCU-EiR/`. Then:

1. Put the opportunity in `solicitation.md` (paste the text or a link; drop the original PDF in as `solicitation-reference.pdf` if you have it).
2. Run the **grant-analyzer** skill: it writes your fit analysis to `evaluation.md` and helps you decide go / no-go.
3. If you're a go, fill in `team.md` (who is on *this* proposal and their roles).
4. Draft in `proposal/` with the **grant-writing** skill, using the render / feedback / revise loop.

## What a grant folder looks like

```
grants/
  NSF-HBCU-EiR/
    solicitation.md          the opportunity (text or a link)
    solicitation-reference.pdf   the original PDF (optional)
    evaluation.md            fit analysis (from grant-analyzer)
    team.md                  who is on THIS proposal and their roles
    proposal/                your draft
      main.tex                 the live working draft
      versions/                rendered PDFs, one per round (v1.pdf, v2.pdf, ...)
      feedback/                your notes per round (v1-feedback.md, ...)
```

Your `profile/` (who you are) and `.claude/skills/` (how the AI works) are shared across every grant. Everything inside a grant folder is specific to that one proposal, so the AI never mixes up funders, teams, or requirements.

See `EXAMPLE-NSF-HBCU-EiR/` for a worked example, and `proposal/README.md` for the feedback loop.
