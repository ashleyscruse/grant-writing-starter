---
name: grant-analyzer
description: "Analyzes grant opportunities against your professional profile to determine fit, eligibility, and strategic value. Produces structured evaluations with fit assessment, alignment analysis, gaps, and recommendations. Use when the user shares a grant solicitation, RFP, RFA, NOFO, or funding opportunity URL and wants to know if it's worth pursuing. Also use when the user mentions 'evaluate this grant,' 'is this a good fit,' 'should I apply,' 'analyze this opportunity,' 'grant fit,' or 'evaluate this RFP.'"
---

# Grant Analyzer

Evaluate grant opportunities against your profile to determine fit, strategic value, and whether the opportunity is worth the time investment.

## Before You Start

Load the profile from this project's `profile/` directory:
- `me/identity.md` -- positions, education, skills
- `me/research.md` -- research focus, publications, active agenda
- `me/teaching-mentoring.md` -- mentoring track record, programs, curricula
- `me/grant-history.md` -- past grants, strengths, known gaps
- `me/` -- also read any CV or biosketch documents dropped in this folder
- `institutions/` -- one folder per institution: read each `profile.md`, its strategic plan, and any facilities documents (skip `_TEMPLATE/`)
- `collaborators/` -- one folder per collaborator: read each `profile.md` and any CV/biosketch (skip `_TEMPLATE/`)

If any profile files are missing or still have blank template prompts, note it but proceed with what's available. Do not ask the user to provide information that should be in their profile -- tell them which profile file to fill in instead.

Also read the grant's `literature/` folder if it has any sources (papers, notes, references the researcher dropped in). Ground your analysis in those and in the profile. Never invent a statistic, citation, or result; if something is not supported by the profile or the literature, say so.

## Input

The user will provide one of:
- A URL to a funding opportunity / solicitation
- A PDF of an RFP/RFA/NOFO
- Pasted text from a solicitation
- A grant name to research

## Workflow

### 1. Extract Grant Requirements

From the solicitation, identify:
- Funder and program name
- Funding amount / range
- Eligibility requirements (PI status, institution type, research area)
- Submission deadlines
- Review criteria and priorities
- Required proposal components
- Any restrictions or exclusions

### 2. Assess Fit

Evaluate the PI's profile against the grant requirements across these dimensions:

**Eligibility (pass/fail):**
- PI qualifications (degree, career stage, role)
- Institution type (HBCU, MSI, PUI, R1, etc.)
- Research area alignment
- Any disqualifying restrictions

**Research Alignment:**
- How closely does the PI's research match the solicitation's scientific priorities?
- Can the PI's work be framed within the grant's scope without overreaching?
- Does the PI have publications in the relevant area?

**Track Record:**
- Prior grants in this area or from this funder
- Relevant publications and preliminary results
- Mentoring and broader impacts evidence
- Institutional resources (HPC, lab space, etc.)

**Strategic Value:**
- Does this advance the PI's research agenda?
- Does it match the institution's strategic plan (in its `institutions/` folder) and the funder's stated priorities?
- Does it complement or compete with active/planned grants?
- Is the funding level appropriate for the work proposed?
- Does the timeline align with PI's availability?

**Team Readiness:**
- Can the PI lead this alone, or are collaborators needed?
- Are the right collaborators already in the profile, or do gaps exist?
- Does the institution provide the necessary infrastructure?

### 3. Identify Gaps

Be honest about weaknesses. Common gaps to check:
- Missing preliminary results
- No publications in a required subfield
- Need for domain collaborators not yet identified
- Budget requirements beyond PI's experience
- Competing with R1 institutions for the same pool

### 4. Produce the Evaluation

Write the evaluation in markdown following the template in [evaluation-template.md](references/evaluation-template.md).

Save the evaluation to the grant's directory: `grants/{grant-name}/evaluation.md`

If the grant directory doesn't exist yet, create it with the evaluation file.

## Decision Framework

Use these categories for the final recommendation:

- **Strong fit. Pursue.** -- Eligible, research aligns well, track record supports it, strategic value is clear. Minor gaps are addressable.
- **Moderate fit. Worth exploring.** -- Eligible, meaningful alignment exists, but significant gaps need addressing. Worth a deeper look or conversation with program officer.
- **Weak fit. Skip unless circumstances change.** -- Eligible but major gaps in research alignment, track record, or team. Time is better spent elsewhere.
- **Not eligible. Do not pursue.** -- Fails eligibility requirements. No amount of framing fixes this.

## What This Skill Does NOT Do

- Does not write the proposal (use the `nsf-grant-writer` skill for that)
- Does not make budget projections
- Does not contact program officers
- Does not guarantee success

## References

- [evaluation-template.md](references/evaluation-template.md): Standard format for evaluation output