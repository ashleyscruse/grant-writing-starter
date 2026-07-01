---
name: grant-writing
description: "Writes grant proposals, narratives, and supporting documents in a structured, criteria-aligned format. Produces needs statements, project descriptions, evaluation plans, budget narratives, sustainability plans, logic models, letters of support drafts, and executive summaries. Use when the user asks to write, draft, revise, or improve any grant proposal section, respond to an RFP/RFA/NOFO, prepare a letter of inquiry, or develop any funding application narrative. Also use when the user mentions 'grant,' 'proposal,' 'funding application,' 'RFP response,' 'needs statement,' 'budget narrative,' 'logic model,' 'evaluation plan,' 'letter of support,' 'sustainability plan,' 'appropriations request,' or 'community project funding.'"
---

# Grant Writing

Write grant proposals that score well by mapping directly to funder review rubrics, using evidence-based claims, and maintaining internal consistency across all sections.

## Workflow

### 1. Load the Context (do not re-gather it)

The intake is already done by `solicitation-review` and `grant-analyzer`, so read what they wrote; do not interrogate the researcher for it. Before drafting, read:
- `grants/{name}/solicitation.md` -- the NSF program, the grant type, review criteria, required components, page limits, and formatting.
- `grants/{name}/evaluation.md` -- the fit and the decision. Only draft if the decision was to pursue.
- `grants/{name}/team.md` -- who is on this proposal (personnel and roles).
- `profile/` -- the researcher, their `me/` files, and the institution and its strategic plan.
- the grant's `literature/` folder -- the sources to cite.

Confirm the grant type (it drives step 2). If `solicitation.md` is missing or lacks the type or criteria, stop and run `solicitation-review` (or `grant-advisor`) first. Do not draft on assumptions.

### 2. Match the Grant Type

Identify the NSF grant type from the solicitation, then draft to that type's rules. The type changes which sections carry the weight, the focus of the prose, and what reviewers score. Every NSF proposal still addresses Intellectual Merit and Broader Impacts. See [grant-types.md](references/grant-types.md) for the full per-type rules.

- **Research**: the research plan, methodology, objectives, and preliminary results; reviewers weight Intellectual Merit and the rigor of the approach.
- **Planning**: the plan, the team and partners convened, milestones, and the larger effort it leads to; not written as a research proposal.
- **Program / education**: program design, participants and recruitment, activities, evaluation plan, sustainability, and broadening participation.
- **Conference / workshop**: the topic's significance, organizers, participants and broadened participation, agenda, dissemination, and outcomes.
- **Equipment / instrumentation**: the instrument, the research it enables, the need, shared multi-user access, and a management and maintenance plan.

### 3. Draft the Section

For section-specific structure, required components, and common mistakes, see [proposal-sections.md](references/proposal-sections.md). This covers:
- Executive Summary / Abstract
- Statement of Need
- Goals, Objectives, and Outcomes
- Project Description / Methodology
- Logic Model
- Evaluation Plan
- Organizational Capacity
- Sustainability Plan
- Budget and Budget Narrative
- Letters of Support and Partnerships

### 4. Review Against the Rubric

After drafting, verify:
- Every evaluation criterion is addressed explicitly
- Section headers match the funder's criteria or RFP structure
- Every narrative activity has a corresponding budget line (and vice versa)
- Goals, methods, evaluation, and budget are internally consistent
- Numbers, dates, and figures match across all sections
- Page limits and formatting requirements are met

For what reviewers look for and common mistakes, see [reviewer-perspective.md](references/reviewer-perspective.md).

---

## Working in a grant folder

Each grant lives in `grants/{name}/`. When drafting:

- The narrative draft is `proposal/main.tex` (or the equivalent `.docx` / `.md` the researcher uses).
- **Budget:** the numbers live in the grant's `budget.xlsx` at the grant root, next to `team.md` (a spreadsheet the researcher edits in Excel or Google Sheets). Read it directly and draft `proposal/budget-justification.tex` from it, explaining every line. Keep the two in sync: if the sheet changes, update the justification, and make sure every narrative activity has a budget line and vice versa.
- **Sources:** before drafting, read the grant's `literature/` folder (papers, notes, references the researcher dropped in). Cite only what is in `literature/` and the `profile/`, and never invent a citation, statistic, or result. If a claim is unsupported, flag it. Only when `literature/` is empty or the researcher asks you to find literature may you propose real, DOI-linked references, clearly flagged for the researcher to verify and add to the folder.
- **Rendering versions:** when asked to render, output the PDF to `proposal/versions/` as the next `vN.pdf`. Never overwrite an old version. Whenever a version is rendered, also create a matching `proposal/feedback/vN-feedback.md` with one empty heading per proposal section (plus General and Compliance) so the researcher only fills in notes; see the `latex-assistant` skill for the template. When revising, read the matching `proposal/feedback/vN-feedback.md` and carry every point through.
- **Assembling the submission PDF:** read the solicitation to determine the required components and their order, and produce a single combined PDF. Place the budget justification **inside the body** if it counts toward the page limit, or **appended as a separate attachment** if it falls outside the page limit. Do not ask the researcher to restructure files; the pieces stay put and you arrange them at render time per the solicitation.

---

## Voice and Style Rules

These rules apply to all grant writing output. No exceptions.

### Structure and Evidence
- Write in a structured, criteria-aligned format that maps directly to funder review rubrics
- Frame problems using data, citations, and documented need
- Translate abstract ideas into concrete goals, objectives, and measurable outcomes
- Use clear logic models linking inputs, activities, outputs, and impacts
- Prioritize specificity over general language: numbers, dates, deliverables, timelines
- Use SMART objectives (Specific, Measurable, Achievable, Relevant, Time-bound)
- Distinguish outputs (what you do) from outcomes (what changes) explicitly
- Support every claim with evidence: data, citations, prior results, or documented community input

### Compliance and Consistency
- Maintain compliance with sponsor guidelines, formatting rules, and page limits
- Align narrative with budget justification and evaluation plan
- Ensure internal consistency across all proposal sections
- Every narrative activity must have a budget line; every budget line must connect to the narrative
- Spell out all acronyms on first use in every major section

### Audience and Tone
- Anticipate reviewer questions and address feasibility, capacity, and risk
- Balance technical credibility with clarity for mixed review audiences
- Use confident, evidence-supported claims without exaggeration
- Avoid jargon unless required for disciplinary accuracy
- Use active voice at least 90% of the time
- Write with concise, directive language under space constraints
- Avoid emotional, hyperbolic, or unsupported claims

### Equity and Framing
- Center the community, not the organization, in the needs statement
- Use asset-based, strengths-based language; never portray communities as broken or helpless
- Use person-first language and community-preferred terminology
- Include community voice: direct quotes, survey results, beneficiary perspectives
- Address accessibility and structural barriers to participation

### Sustainability and Impact
- Integrate sustainability and long-term impact planning into the narrative
- Show that sustainability planning begins at project launch, not the final year
- Include diversified revenue strategies, not just "seek additional grants"

### Funder Alignment
- Read the institution's strategic plan (in its `profile/institutions/` folder) and match the framing to it, alongside the funder's priorities
- Mirror the funder's own language, priorities, and strategic plan
- Customize every proposal to the specific funder; never submit generic text
- Reference the funder's RFP language, prior awards, and stated interests

### Formatting
- Defer to the solicitation for all formatting: font size, line spacing, margins, and page limits. Do not impose a house style; follow what the funder requires. The `latex-assistant` skill applies it.
- Write each proposal section as a LaTeX `\section` (and `\subsection` where the solicitation names subsections) so headers are generated automatically when the document is formatted. Do not hand-format headers in bold.
- Write in prose paragraphs. No bullet-point lists.
- Use tables and logic models where they carry the content better than prose, and a Gantt chart for a timeline when one helps.

### NSF prose directives
- Write without adjectives unless one is explicitly requested.
- Write in paragraphs, never lists.
- Avoid participial phrases.
- Within a section, write flowing prose, not fragmented labels. Make the first sentence of each paragraph its main idea, so the first sentences read together as an abstract of the section.
- Cite only the sources in the grant's `literature/` folder; do not cite anything that is not there. If that folder is empty, or the researcher asks you to help find literature, then find real references, flag them as suggestions to verify and add to `literature/`, and give every reference as a hyperlink to its known DOI.
- Never use these words: Delve, Tapestry, Vibrant, Landscape, Realm, Embark, Excels, Vital, Weave, Intertwined, Truly, Fleeting, Enchanting, Amidst, Portrayal, Artful, Painted, Seizing, Trusted, Vision, Unfolding, Strive, Ever-evolving, Seamless, Compelling, Marveled, Subtlest, Transcends, Unlock, Unleash, Unveiling, Vast.

### Absolute Prohibitions
- No em dashes, ever. Use commas, colons, periods, or parentheses instead.
- No bullet-point lists in the narrative. Use prose, and tables, logic models, or a Gantt chart when a visual carries it better.
- No "It is not [X], it is [Y]" sentence structures or similar contrastive constructions that signal AI-generated text
- No deficit-based framing of communities
- No unsourced statistics or fabricated data
- No emotional appeals or hyperbolic language
- No passive voice unless the actor is genuinely unknown or irrelevant
- Zero tolerance for typos, grammatical errors, or inconsistent terminology

---

## References

- [proposal-sections.md](references/proposal-sections.md): Detailed guidance for each proposal section (needs statement, goals/objectives, methodology, evaluation, budget, sustainability, letters of support, logic models)
- [grant-types.md](references/grant-types.md): Conventions for federal, foundation, corporate, and congressional grants
- [reviewer-perspective.md](references/reviewer-perspective.md): What reviewers look for, red flags, common mistakes, and scanability strategies
