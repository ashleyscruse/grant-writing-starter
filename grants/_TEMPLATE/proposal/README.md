# Proposal

Your draft goes here.

```
proposal/
  main.tex                  the page-limited narrative
  budget-justification.tex  budget narrative, drafted from ../budget.xlsx
  versions/                 rendered PDFs, one per round
  feedback/                 your notes per round
```

Budget numbers live one level up, in the grant's `budget.xlsx` (next to `team.md`).

**The loop:** render the current draft to `versions/v1.pdf`; write notes in `feedback/v1-feedback.md`; ask the AI to revise (it reads the feedback and renders `versions/v2.pdf`). Old versions stay in `versions/`; the highest number is current.

**Budget:** keep numbers in the grant's `budget.xlsx` (one level up), words in `budget-justification.tex`; the AI drafts the justification from the sheet.

**Sources:** put papers and references in the grant's `literature/` folder so the AI grounds claims in real sources instead of guessing.

**Submission:** ask the AI to assemble the full submission into one PDF. It follows the solicitation, including the budget justification inside the body if it counts toward the page limit, or appended as a separate attachment if it does not.
