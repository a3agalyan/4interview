# 4interview

**Stop searching Blind, Glassdoor, and Reddit. One Claude Code command gives you a complete 3-day interview prep file — real candidate experiences, targeted Q&As, and a time-boxed study plan, all specific to your company and role.**

```
/4interview
```

> You have 3 days. Don't spend them tab-switching between forums.

---

## The problem

You have an interview at Google, Stripe, or Capital One in a few days. You:

- Open Blind, search your company + role, read 10 posts — half are 3 years old
- Open Reddit, find a thread, it's locked
- Open Glassdoor, hit a paywall
- Copy-paste notes into a doc, stare at it
- Still not sure what to study

That's 2 hours gone. You haven't prepared anything.

## What this does instead

Type `/4interview` in Claude Code. It asks you 5 questions (company, role, interview type, job description, HR notes). Then it:

1. Searches Reddit, Blind, Glassdoor, and Leetcode discussions for real candidate reports — calibrated to your exact company, role, and interview type
2. Extracts the topics that actually came up, not generic advice
3. Writes a single markdown file with everything: focus areas with study links, 3–4 real past candidate experiences with source URLs, a time-boxed 3-day plan, and 10–30 questions with full answers

**Output:** one `.md` file you open in VSCode or Obsidian and work through. No chat scrolling.

---

## Install

```bash
mkdir -p ~/.claude/skills/4interview
curl -fsSL https://raw.githubusercontent.com/armenag/4interview/main/SKILL.md \
  -o ~/.claude/skills/4interview/SKILL.md
```

Requires [Claude Code](https://claude.ai/code).

---

## Usage

In any Claude Code session:

```
/4interview
```

The skill walks you through inputs one at a time, confirms before running, then writes the file.

### Inputs

| Field | Required | What to put |
|---|---|---|
| `company` | Yes | Company name |
| `role` | Yes | Job title and level (e.g. "Senior SWE L5") |
| `interview` | Yes | Interview type: System Design, Behavioral, Coding, ML Design, Technical Screen |
| `job-description` | Optional | Paste the job posting — Claude extracts the tech stack and requirements |
| `hr-notes` | Optional | Anything the recruiter said — topics mentioned, format, scheduling emails |
| `additional-notes` | Optional | Your weak spots, anxieties, things you've heard |

### Output file

```
prep-{company}-{role}-{interview}-{date}.md
```

Sections:
- **What This Interview Is About** — specific to this company, not generic
- **Focus Areas** — extracted from your notes, each with a study resource and time estimate
- **Past Candidate Experiences** — 3–4 real accounts with source URLs, ranked by specificity
- **3-Day Prep Plan** — time-boxed checklist, specific tasks
- **Questions & Answers** — 10–30, calibrated to your interview type

---

## Examples

- `prep-google-staff-engineer-system-design-2026-05-22.md`
- `prep-stripe-senior-swe-coding-2026-05-22.md`
- `prep-capital-one-ml-engineer-ml-design-2026-05-22.md`

---

## Requirements

- [Claude Code](https://claude.ai/code) with WebSearch and WebFetch enabled
- Claude Sonnet 4+ (Opus recommended for richer output)

---

## License

MIT
