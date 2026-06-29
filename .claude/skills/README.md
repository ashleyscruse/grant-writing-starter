# Skills

Reusable `SKILL.md` instructions, one per task. A skill packages a repeatable job once so you can use it in any tool that reads this folder (Claude Code, Cursor, VS Code, or Claude on the web). When you name a skill or ask for a task one covers, the AI reads the matching `SKILL.md` and follows it.

| Skill | What it does | When it runs |
|---|---|---|
| `setup-guide` | **Sage** — onboards you and fills in your profile | First contact, or "help me get set up" |
| `solicitation-review` | Parses a solicitation into a structured requirements brief (dates, eligibility, criteria, page limits) | You paste an RFP/NOFO and want it broken down |
| `grant-analyzer` | Evaluates a solicitation against your profile: fit, eligibility, gaps, go/no-go | You ask "should I apply?" |
| `grant-organizer` | Logs every reviewed grant to `grants/grant-tracker.xlsx` so you see your pipeline at a glance | You evaluate a grant or ask "what am I tracking?" |
| `grant-writing` | Drafts and revises proposal sections, mapped to the funder's review rubric | You ask to write/revise any proposal section |
| `latex-assistant` | Sets up LaTeX, scaffolds a compliant `main.tex`, compiles, and renders versioned PDFs | You ask to set up, compile, or render the proposal |
| `nsf-broader-impacts` | Drafts a scored-well NSF Broader Impacts section from your real mentoring/outreach record | You ask to write/improve NSF Broader Impacts |

## Adding your own

Create a folder with a `SKILL.md` that has YAML frontmatter (`name`, `description`) and instructions in the body. Put any supporting files in a `references/` subfolder. Keep one skill per task.
