# Proposal

Your actual draft lives here. The write / render / feedback / revise loop keeps a full history so you never lose a version and the AI revises from your written notes.

```
proposal/
  main.tex                  the live working draft (the page-limited narrative)
  budget.csv                the budget numbers (opens in Excel or Google Sheets)
  budget-justification.tex  the budget narrative, drafted from budget.csv
  versions/                 every rendered PDF, one per round (v1.pdf, v2.pdf, ...)
  feedback/                 your notes per round, in markdown (v1-feedback.md, ...)
```

## The loop

1. **Render.** Ask the AI to render the current draft. It saves the PDF as `versions/v1.pdf` (the next number).
2. **Read and respond.** Read that PDF. Write your notes in `feedback/v1-feedback.md` (plain language is fine: "Objective 2 is too vague," "add preliminary data here," "tighten the significance paragraph").
3. **Revise.** Ask the AI to revise. It reads your draft plus `feedback/v1-feedback.md`, updates the draft, and renders `versions/v2.pdf`.
4. **Repeat.** Every past version stays in `versions/`, and the newest number is always the current one.

You give feedback in writing once; the AI carries it through. The lineage in `versions/` is your record of how the proposal evolved.

## The budget

`budget.csv` holds your numbers, by category and year. Open and edit it in Excel or Google Sheets (it is a plain spreadsheet), or just ask the AI to fill it in with you. Because it is a simple sheet, the AI can read it directly and use it to draft `budget-justification.tex`, the narrative that explains every line. Keep the numbers in `budget.csv` and the words in `budget-justification.tex` in sync: change the sheet, ask the AI to update the justification.

## Assembling the submission PDF

When it is time to submit, ask the AI to render the full submission. It reads the solicitation and assembles the required pieces, in the required order, into **one PDF**. Two cases, handled the same way:

- **Budget justification is within the page limit** (counts toward the narrative): the AI includes it inside the body.
- **Budget justification is a separate attachment** (outside the page limit): the AI appends it as its own section after the narrative.

You do not restructure anything either way. The pieces stay in their files; the solicitation decides how they are arranged in the final PDF.

