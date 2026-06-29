---
name: grant-organizer
description: "Maintains a spreadsheet tracker of every grant reviewed: agency, program, PI role, deadlines, routing, amount, fit, decision, and status, so the researcher sees their whole pipeline at a glance. Updates grants/grant-tracker.xlsx whenever a grant is evaluated or its status changes. Use when the user asks to log a grant, update the tracker, see their grant pipeline, or 'add this to my tracker.' Also use when the user mentions 'tracker,' 'log this grant,' 'grant pipeline,' 'what grants am I tracking,' 'update status,' or 'routing.'"
---

# Grant Organizer

Keep one source of truth for the researcher's grant pipeline in `grants/grant-tracker.xlsx`. Every opportunity they review lands here, so they can see at a glance what is worth pursuing, what is routing, and what deadlines are coming.

## The tracker

- **Location:** `grants/grant-tracker.xlsx`, sheet named `Grants`.
- **One row per grant.** Never create a second row for a grant already listed; update it in place.
- **Columns (in order):**
  1. `Name` (the opportunity title; this is the match key)
  2. `Agency`
  3. `Program`
  4. `Website`
  5. `I'm PI?` (Yes / No)
  6. `Co-PIs / Lead`
  7. `Amount`
  8. `LOI Date`
  9. `Due Date`
  10. `Route By`
  11. `Target Submit`
  12. `Routed?` (Yes / No)
  13. `Previously Submitted?` (Yes / No)
  14. `Fit Rating` (Strong / Moderate / Weak / Not eligible)
  15. `Decision` (Pursue / Considering / Don't Pursue)
  16. `Status` (Reviewing / Drafting / Submitted / Awarded / Declined)
  17. `Notes`

Columns 14, 15, 16 and the three Yes/No columns are dropdowns (data validation). Use the exact allowed values so the dropdowns stay valid.

## Who fills what

- **You (the AI) fill** the fields you can derive: `Name`, `Agency`, `Program`, `Website`, `Amount`, `LOI Date`, `Due Date`, `Fit Rating`, `Decision`, `Status`. Pull `Fit Rating` / `Decision` from `evaluation.md`, and dates / amount from `solicitation.md`.
- **The researcher fills** the operational calls: `I'm PI?`, `Co-PIs / Lead`, `Route By`, `Target Submit`, `Routed?`, `Previously Submitted?`. **Never overwrite a value the researcher already entered.** When updating a row, only write cells you have a new value for; leave the rest untouched.

## When to run

- **After a grant is evaluated** (`grant-advisor` / `grant-analyzer`): add or update that grant's row.
- **When the researcher changes a status or detail** (e.g., "mark the NSF EiR as routed," "we submitted it").
- **When asked to show the pipeline:** read the tracker and present a short markdown summary, sorted by nearest `Due Date`.

## How to update (openpyxl)

Match on `Name`. If a matching row exists, update only the cells you have values for; otherwise append. If the file does not exist, create it with the header row and the dropdowns.

```python
from pathlib import Path
from openpyxl import load_workbook, Workbook
from openpyxl.styles import Font
from openpyxl.worksheet.datavalidation import DataValidation

HEADERS = ["Name","Agency","Program","Website","I'm PI?","Co-PIs / Lead","Amount",
           "LOI Date","Due Date","Route By","Target Submit","Routed?","Previously Submitted?",
           "Fit Rating","Decision","Status","Notes"]
LISTS = {  # column letter -> dropdown values
    "E": ["Yes","No"], "L": ["Yes","No"], "M": ["Yes","No"],
    "N": ["Strong","Moderate","Weak","Not eligible"],
    "O": ["Pursue","Considering","Don't Pursue"],
    "P": ["Reviewing","Drafting","Submitted","Awarded","Declined"],
}
path = Path("grants/grant-tracker.xlsx")

if path.exists():
    wb = load_workbook(path); ws = wb["Grants"]
else:
    wb = Workbook(); ws = wb.active; ws.title = "Grants"
    ws.append(HEADERS)
    for c in ws[1]: c.font = Font(bold=True)
    for col, opts in LISTS.items():
        dv = DataValidation(type="list", formula1='"%s"' % ",".join(opts), allow_blank=True)
        dv.add("%s2:%s500" % (col, col)); ws.add_data_validation(dv)

# Only include keys you actually have a value for (so you never blank the researcher's fields).
row = {"Name": "...", "Agency": "...", "Fit Rating": "...", "Decision": "...", "Status": "Reviewing"}

match_col = HEADERS.index("Name") + 1
target = None
for r in range(2, ws.max_row + 1):
    v = ws.cell(r, match_col).value
    if v and v.strip().lower() == row["Name"].strip().lower():
        target = r; break
if target is None:
    ws.append([row.get(h, "") for h in HEADERS])
else:
    for i, h in enumerate(HEADERS, start=1):
        if h in row:                      # update only provided fields; leave the rest
            ws.cell(target, i, row[h])

wb.save(path)
```

Do not hardcode dates; read them from the system or the solicitation. Keep the column order fixed.

## What this skill does NOT do

- Evaluate fit or recommend a decision (that is `grant-analyzer` / `grant-advisor`).
- Write or render any proposal section (that is `grant-writing` / `latex-assistant`).
- It records and reports the pipeline; it does not judge.
