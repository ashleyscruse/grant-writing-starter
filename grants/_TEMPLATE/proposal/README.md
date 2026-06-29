# Proposal

Your draft goes here.

```
proposal/
  main.tex                  the page-limited narrative
  budget.csv                budget numbers (Excel / Google Sheets; the AI reads it)
  budget-justification.tex  budget narrative, drafted from budget.csv
  versions/                 rendered PDFs, one per round
  feedback/                 your notes per round
```

**The loop:** render the current draft -> `versions/v1.pdf`; write notes in `feedback/v1-feedback.md`; ask the AI to revise (it reads the feedback and renders `versions/v2.pdf`). Old versions stay in `versions/`; the highest number is current.

**Budget:** keep numbers in `budget.csv`, words in `budget-justification.tex`; the AI drafts the justification from the sheet.

**Submission:** ask the AI to assemble the full submission into one PDF. It follows the solicitation, including the budget justification inside the body if it counts toward the page limit, or appended as a separate attachment if it does not.
