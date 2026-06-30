---
name: grant-writing
description: "Writes grant proposals, narratives, and supporting documents in a structured, criteria-aligned format. Produces needs statements, project descriptions, evaluation plans, budget narratives, sustainability plans, logic models, letters of support drafts, and executive summaries. Use when the user asks to write, draft, revise, or improve any grant proposal section, respond to an RFP/RFA/NOFO, prepare a letter of inquiry, or develop any funding application narrative. Also use when the user mentions 'grant,' 'proposal,' 'funding application,' 'RFP response,' 'needs statement,' 'budget narrative,' 'logic model,' 'evaluation plan,' 'letter of support,' 'sustainability plan,' 'appropriations request,' or 'community project funding.'"
---

# Grant Writing

Write grant proposals that score well by mapping directly to funder review rubrics, using evidence-based claims, and maintaining internal consistency across all sections.

## Workflow

### 1. Gather Context Before Writing

Before drafting any section, confirm:
- Who is the funder? (federal agency, foundation, corporation, congressional office)
- What is the RFP/RFA/NOFO or funding opportunity?
- What are the evaluation criteria and scoring rubric?
- What are the page limits, font, margin, and formatting requirements?
- What is the project, who does it serve, and where?
- What data, prior results, or preliminary evidence is available?

If any of these are missing, ask. Do not draft with assumptions about funder priorities or compliance requirements.

### 2. Match the Grant Type

Adjust tone, structure, and evidence standards to the funder type:

- **Federal**: Mirror RFP language exactly. Use section headers from the evaluation criteria. Heavy on data, citations, validated instruments, and scored rubric alignment. See [grant-types.md](references/grant-types.md) for federal conventions.
- **Foundation**: Lead with mission alignment and narrative. More conversational, shorter, story-driven with data support. See [grant-types.md](references/grant-types.md) for foundation conventions.
- **Corporate**: Concise, business-oriented, mutual benefit framing. See [grant-types.md](references/grant-types.md) for corporate conventions.
- **Congressional/Appropriations**: Community support documentation, federal authorization alignment, local economic impact. See [grant-types.md](references/grant-types.md) for congressional conventions.

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
- **Sources:** before drafting, read the grant's `literature/` folder (papers, notes, references the researcher dropped in). Ground claims and citations in those sources and in the `profile/`. If a claim is not supported by something there, flag it for the researcher to confirm; never invent a citation, statistic, or result.
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

### Formatting and Scanability
- Use strategic formatting: white space, bold key phrases, headers, bulleted lists
- Keep paragraphs to 3 to 5 sentences
- Use topic sentences that state the point, then provide evidence
- Include figures, tables, and diagrams to summarize data and timelines when appropriate
- Design every section so a scanning reviewer grasps the key points from headers, bold text, and first sentences alone

### Absolute Prohibitions
- No em dashes, ever. Use commas, colons, periods, or parentheses instead.
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
