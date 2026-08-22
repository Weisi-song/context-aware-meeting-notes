# Context-Aware Meeting Notes

> A sanitized portfolio case study. No real transcripts, customer names, sales records, or internal documents are included.

I built a more reliable weekly meeting-minutes workflow by grounding transcript processing in the team's CRM sales reports.

## The problem

Generic AI summarization could preserve a meeting format, but it often misspelled unfamiliar customer, project, and school names or assigned work to the wrong salesperson. Manual cross-checking erased much of the efficiency gain.

## What I changed

- Standardized the minutes structure with a reusable skill
- Added CRM sales reports as organization-specific context
- Cross-checked extracted entities against known customers and projects
- Validated the mapping between salespeople and reported work
- Produced submission-ready minutes with much less manual correction

## Workflow

```text
Meeting transcript ─┐
                    ├→ Context validation → Structured weekly minutes
CRM sales reports ──┘
```

## My role

I identified the missing-context problem, coordinated access to the regional CRM export, designed the cross-validation workflow, and iterated the skill around real weekly usage.

## Public portfolio scope

This repository currently documents the case. Synthetic transcript and CRM examples plus a sample generated report are planned.

