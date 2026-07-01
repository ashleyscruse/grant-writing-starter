# Skills

Reusable `SKILL.md` instructions, one per task. A skill packages a repeatable job once so you can use it in any tool that reads this folder (Claude Code, Cursor, VS Code, or Claude on the web). When you name a skill or ask for a task one covers, the AI reads the matching `SKILL.md` and follows it.

| Skill | What it does | When it runs |
|---|---|---|
| `setup-guide` | **Sage** — onboards you and fills in your profile | First contact, or "help me get set up" |
| `grant-advisor` | **End-to-end intake.** Takes a URL or PDF, parses it, evaluates fit, decides (Pursue / Considering / Don't Pursue), logs the tracker, and saves a grant folder | You paste a solicitation and ask "should I pursue this?" |
| `solicitation-review` | Parses a solicitation into a structured requirements brief (dates, eligibility, criteria, page limits) | You paste an RFP/NOFO and want it broken down |
| `grant-analyzer` | Evaluates a solicitation against your profile: fit, eligibility, gaps, recommendation | You ask for a fit assessment |
| `grant-organizer` | Logs every reviewed grant to `grants/grant-tracker.xlsx` so you see your pipeline at a glance | You evaluate a grant or ask "what am I tracking?" |
| `nsf-grant-writer` | Drafts and revises NSF proposal sections, to the review criteria and the grant type's rules | You ask to write/revise any NSF proposal section |
| `reviewer-builder` | Builds a panel from the solicitation (skeptic, non-expert, subject expert, program officer), reads the draft through each, then checks compliance | You ask to review a draft or "am I ready to submit?" |
| `latex-assistant` | Sets up LaTeX, scaffolds a compliant `main.tex`, compiles, and renders versioned PDFs | You ask to set up, compile, or render the proposal |

## Adding your own

Create a folder with a `SKILL.md` that has YAML frontmatter (`name`, `description`) and instructions in the body. Put any supporting files in a `references/` subfolder. Keep one skill per task.
