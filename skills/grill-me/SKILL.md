---
name: grill-me
description: >-
  Interrogate the user before or after agent work to stress-test plans, catch
  edge cases, and verify understanding — reducing token burn and AI drift.
  Use when the user asks to grill them, stress-test a plan, validate intent
  before coding, review what was built, or mentions the Grill Me workflow from
  Cursor Philly meetups.
---

# Grill Me

The agent **interviews you** — not the other way around — until both sides have a complete, shared understanding of the goal, constraints, and edge cases.

Use this **before** submitting work to the agent (planning) or **after** the agent finishes (verification). The meetup room surfaced this independently in 3 of 5 groups as the best way to cut token waste and prevent drift.

## When to run

| Moment | Purpose |
|---|---|
| **Before coding** | Flesh out the plan; surface edge cases and ambiguities while tokens are cheap |
| **Before deploy/merge** | Confirm you understand what was built and why |
| **After a long agent session** | Verify nothing drifted from the original goal |

## How to run

1. **State the artifact** — plan, PR summary, feature spec, or "what the agent just built."
2. **Switch roles** — you are the interviewee; the agent asks questions only (no fixes yet).
3. **Grill until clear** — agent asks short, pointed questions one at a time or in small batches:
   - What is the user-facing outcome?
   - What must *not* change?
   - What breaks this? (edge cases, auth, empty states, rollback)
   - What did you trade off and why?
   - If this shipped wrong, how would you notice?
4. **Stop condition** — agent summarizes what it heard; you confirm or correct. Only then proceed to implementation, merge, or deploy.

## Agent behavior

- Ask **specific** questions, not generic "anything else?"
- Push on gaps: "You said X — what happens when Y?"
- Do **not** write code or edit files during the grill phase unless the user explicitly ends it
- Keep a running checklist of unresolved items; surface them at the end
- If the user can't answer, that's the signal — go research or revise the plan before burning tokens

## Example opener (user)

> Grill me on this plan before you build it.

> I just finished a feature with the agent — grill me so I actually understand what shipped.

## Example agent questions

- "What's the single success metric for this change?"
- "Who can trigger this path, and who should be blocked?"
- "What happens if the API returns 500 mid-flow?"
- "Which files did we touch, and what would regress if we reverted one of them?"

## Pair with

- **Approve the plan, not the PR** — sign off after the grill, then check deviation at merge time instead of line-by-line review of generated code.
- **Plan-first development** — design system, monorepo, or explicit spec before prompting.

Source: [Cafe Cursor inspiration/workflows.md](../../inspiration/workflows.md)
