---
name: cv-import
description: Builds a profile from a CV, for the researcher themselves or for a collaborator. Reads a CV, resume, or biosketch and writes it into a profile.md, then asks the few questions a CV cannot answer. Use when the researcher says "build my profile," "import my CV," "add <person> as a collaborator," "read this CV," or drops a CV and wants it turned into a profile.

---

# CV Import

Turn a CV into a ready profile so the researcher never fills a blank template by hand. Works two ways: their **own** profile, and a **collaborator's**.

## When to use

- **Own profile:** they drop a CV (or resume / biosketch) in `profile/me/` and say "build my profile," "import my CV," or "read my CV."
- **A collaborator:** they hand you someone else's CV and say "add this person as a collaborator" or "bring <name> into my ecosystem."

## A. The researcher's own profile

Steps

1. **Find the CV.** Look in `profile/me/` for a `.pdf`, `.docx`, `.md`, or `.tex` (named cv, resume, or biosketch). If there is none, ask them to drop it in `profile/me/` and stop until they do.
2. **Read it and extract** into the sections of `profile/me/profile.md`:
   - **Identity** — name, positions, education, research areas, technical skills
   - **Research** — core focus, active agenda, publications (keep citations exactly as written)
   - **Teaching and Mentoring** — programs, courses, mentoring counts and outcomes, outreach
   - **Grant History** — grants and fellowships received, proposals in progress
   - **Strengths** — what the CV shows that reviewers would find compelling
   Only write what the CV actually says. Do not invent numbers, publications, awards, or dollar amounts.
3. **Write `profile/me/profile.md`,** filling those sections. Keep figures and citations exactly as the CV states them.
4. **Fill the gaps a CV cannot.** Ask, one at a time, in plain language, and write each answer into the file:
   - **Honest gaps** — "What's missing that would weaken a proposal?" (no PI grant yet, thin preliminary data, need a collaborator, budgets under a certain size). Press gently; this is the point.
   - **Current priorities** — "What are you actively trying to fund right now?" (the program, agency, or deadline).
   - **Their edge** — "What's your honest strength a reviewer would find compelling?"
5. **Read it back.** Show the filled `profile.md`, invite corrections, fix what they flag.

## B. A collaborator

Same idea, for someone the researcher wants in their ecosystem.

1. **Make the folder.** Copy `profile/collaborators/_TEMPLATE/` to a folder named for the person (e.g. `taylor-james/`) and drop their CV inside it.
2. **Read the CV and write** that folder's `profile.md`: name and credentials, position, expertise (methods, domains, or resources they bring), and 1-3 key publications. Keep everything exactly as the CV states it; invent nothing.
3. **Ask the two things a CV can't tell you** (a collaborator profile needs these, not gaps):
   - **Relationship** — "How do you know them, and have you worked together before?"
   - **Why them** — "What do they bring that you don't have?" (the expertise or resource that makes them worth adding)
4. **Read it back,** invite corrections, fix.

Skip the `_TEMPLATE/` folder itself.

## Boundaries

- Never fabricate. If the CV doesn't say it and they didn't tell you, leave it out.
- The gaps section is the whole reason this matters. Don't let them skip it, but stay kind.
- You build the profile only. Fit analysis (`grant-analyzer`) and drafting (`nsf-grant-writer`) come after.
