---
name: grant-organizer
description: "Maintains a spreadsheet tracker of every grant reviewed, with funder, deadline, fit rating, go/no-go decision, and status, so the researcher can see their whole pipeline at a glance. Updates grants/grant-tracker.xlsx whenever a grant is evaluated or its status changes. Use when the user asks to log a grant, update the tracker, see their grant pipeline, or 'add this to my tracker.' Also use when the user mentions 'tracker,' 'log this grant,' 'grant pipeline,' 'what grants am I tracking,' 'update status,' or 'go/no-go list.'"
---

# Grant Organizer

Keep one source of truth for the researcher's grant pipeline in `grants/grant-tracker.xlsx`. Every opportunity they review lands here with its fit rating, decision, and current status, so they can see at a glance what is worth pursuing, what is in progress, and what deadlines are coming.

## The tracker

- **Location:** `grants/grant-tracker.xlsx`, sheet named `Grants`.
- **One row per grant.** Never create a second row for a grant that is already listed; update it in place.
- **Columns (in order):**
  1. `Grant / Opportunity`
  2. `Funder`
  3. `Program / Opportunity #`
  4. `Deadline`
  5. `Award Range`
  6. `Fit Rating` — Strong / Moderate / Weak / Not eligible
  7. `Decision` — Pursue / Considering / Don't Pursue
  8. `Status` — Reviewing / Drafting / Submitted / Awarded / Declined
  9. `Date Reviewed`
  10. `Folder` — `grants/{name}/`
  11. `Notes`

If the file does not exist, create it with the header row before adding data.

## When to run

- **After `grant-analyzer` writes an evaluation:** add or update that grant's row. Pull `Fit Rating` and `Decision` from the recommendation in `grants/{name}/evaluation.md`, and `Deadline` / `Award Range` from `grants/{name}/solicitation.md`.
- **When the researcher changes a decision or status** (e.g., "mark the NSF EiR as submitted").
- **When asked to show the pipeline:** read the tracker and present a quick markdown summary, sorted by nearest deadline.

## How to update (openpyxl)

Use `openpyxl`. Match on the `Folder` value (or `Grant / Opportunity` if no folder yet): if a matching row exists, update its cells; otherwise append a new row. Then save and show the researcher a short summary of what changed.

```python
from pathlib import Path
from openpyxl import load_workbook, Workbook

HEADERS = ["Grant / Opportunity","Funder","Program / Opportunity #","Deadline",
           "Award Range","Fit Rating","Decision","Status","Date Reviewed","Folder","Notes"]
path = Path("grants/grant-tracker.xlsx")

if path.exists():
    wb = load_workbook(path); ws = wb["Grants"]
else:
    wb = Workbook(); ws = wb.active; ws.title = "Grants"; ws.append(HEADERS)

row = {  # fill from solicitation.md + evaluation.md
    "Grant / Opportunity": "...", "Funder": "...", "Program / Opportunity #": "...",
    "Deadline": "...", "Award Range": "...", "Fit Rating": "...", "Decision": "...",
    "Status": "Reviewing", "Date Reviewed": "...", "Folder": "grants/.../", "Notes": "",
}

# update in place if the folder/name already exists, else append
match_col = HEADERS.index("Folder") + 1
target = None
for r in range(2, ws.max_row + 1):
    if ws.cell(r, match_col).value == row["Folder"]:
        target = r; break
if target is None:
    ws.append([row[h] for h in HEADERS])
else:
    for i, h in enumerate(HEADERS, start=1):
        ws.cell(target, i, row[h])

wb.save(path)
```

Do not hardcode the date; read it from the system or ask the researcher. Keep the column order fixed so the file stays consistent across updates.

## What this skill does NOT do

- Evaluate fit or recommend go/no-go (that is `grant-analyzer`).
- Write or render any proposal section (that is `grant-writing` / `latex-assistant`).
- It records and reports the pipeline; it does not judge.
