---
name: latex-assistant
description: "Sets up and runs the LaTeX toolchain for a proposal: scaffolds a compliant main.tex (margins, font, spacing per the solicitation), compiles to PDF, fixes LaTeX errors, and renders versioned PDFs into the proposal's versions/ folder. Use when the user asks to set up LaTeX, create or compile main.tex or budget-justification.tex, render or build the proposal PDF, or fix a LaTeX error. Also use when the user mentions 'set up latex,' 'compile,' 'render the pdf,' 'build the proposal,' 'latex error,' 'overfull hbox,' or 'main.tex.'"
---

# LaTeX Assistant

Own the document mechanics so the writing skills can stay focused on prose. Set up the LaTeX environment, scaffold compliant source, compile, troubleshoot errors, and render versioned PDFs. The researcher writes the argument; you make the document build and meet the funder's formatting rules.

## Scope and boundary

- **You do:** detect/set up the toolchain, scaffold `main.tex` and `budget-justification.tex`, enforce formatting compliance, compile, fix LaTeX errors, render and version PDFs.
- **You do NOT:** write proposal narrative (that is `grant-writing` and the `nsf-*` section skills) or judge fit (that is `grant-analyzer`). If the document fails to build, fix the LaTeX, not the argument.

## Toolchain

Detect what is installed and use the first available, in this order:
1. `tectonic` (self-contained, fetches packages automatically) — preferred when present.
2. `latexmk` (drives `pdflatex`/`bibtex` and reruns to resolve references) — the reliable default on TeX Live / MacTeX.
3. `pdflatex` directly (run twice if there are references/labels).

If none is installed, do not fake a build. Tell the researcher the one install step for their platform: macOS `brew install --cask mactex-no-gui` (or `brew install tectonic`), Linux `sudo apt-get install texlive-full` (or `tectonic`), then retry.

## Scaffolding a compliant main.tex

1. Read `grants/{name}/solicitation.md` (the parsed brief from `solicitation-review`) for the required formatting: margins, font family and size, line spacing, and the required components and their order.
2. If no rules are specified, default to **NSF PAPPG**: margins at least 1 inch on all sides, a readable font no smaller than 10 pt (11–12 pt for Computer Modern / Times-equivalent), single spacing, and no more than 6 lines of text per inch.
3. Write `proposal/main.tex` with: a `geometry` block for the margins, the font/size setup, and section headers that mirror the solicitation's required components (e.g., Project Summary, Project Description, References Cited). Use the worked example `grants/EXAMPLE-NSF-HBCU-EiR/proposal/main.tex` as a structural model.
4. Keep content out of it. Leave each section as a brief placeholder comment so the writing skills fill it in. Never invent narrative here.

## Budget justification

When asked, read `proposal/budget.xlsx` and render `proposal/budget-justification.tex` into the PDF. The numbers come from the spreadsheet; the prose comes from `grant-writing`. Your job is to make it typeset cleanly and stay within any page limit.

## Compiling and versioning

- Build from inside the grant's `proposal/` folder.
- Output the PDF to `proposal/versions/` as the next `vN.pdf`. **Never overwrite an older version.** If `v1.pdf` exists, write `v2.pdf`.
- After a successful build, report the page count and confirm it is within the solicitation's page limit. If it is over, say so plainly and point to the section to cut; do not silently shrink margins or font below the rules.

## Create a matching feedback file for every version

Every time you render `versions/vN.pdf`, also create `feedback/vN-feedback.md` if it does not already exist, pre-filled so the researcher only has to type their notes.

- Build it with one heading per section that the proposal actually contains, in order. Read the section structure from `proposal/main.tex` (its `\section`/`\section*` titles); if the draft has no sections yet, fall back to the required components in `solicitation.md`.
- Under each section heading, leave an empty bullet for the researcher's notes. Add a final **General / overall** heading and a **Compliance (page limit, formatting)** heading.
- Do not write feedback yourself; the file is the researcher's to fill in. Once they say there is feedback, read `feedback/vN-feedback.md`, carry every point through, and render the next `vN+1.pdf`.

Template shape:

```markdown
# Feedback on vN

> Fill in your notes under each section, then tell the AI "there's feedback on vN."

## <Section 1 title>
-

## <Section 2 title>
-

## General / overall
-

## Compliance (page limit, formatting)
-
```

## Fixing errors

- Read the actual log (`.log` file or compiler output), find the specific failing line, fix that, and recompile. Do not blanket-rewrite the file.
- Common cases: missing package (add `\usepackage` or let `tectonic` fetch it), undefined control sequence (typo or missing package), unbalanced braces, and **overfull `\hbox`** (note when it risks pushing text past the required margin, which is a compliance problem, not just cosmetic).

## What this skill does NOT do

- Write or edit proposal narrative content.
- Decide what the proposal says or which sections to include.
- Bypass page limits or formatting rules to make something fit.
