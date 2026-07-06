# Community workflows

Patterns that surfaced at Cursor Meetup Philadelphia — especially the June 30, 2026 participation night. Try these during open build time at Cafe Cursor.

---

## Grill Me

**What:** Before (or after) agent work, have the agent **interview you** until the plan is solid — not the other way around.

**Why:** Mentioned independently in **3 of 5 breakout groups**. Cuts token waste and prevents the agent from drifting off-goal.

**How:**

1. State the artifact — plan, PR summary, or "what the agent just built"
2. Say: *"Grill me on this plan before you build it."*
3. Answer pointed questions until the agent summarizes back and you confirm
4. Only then let the agent implement

**Drop-in skill:** Copy [`skills/grill-me/SKILL.md`](../skills/grill-me/SKILL.md) into your project's `.cursor/skills/grill-me/SKILL.md`.

---

## Approve the plan, not the PR

**What:** Review and sign off on the **plan** upfront. At merge time, check deviation from the plan instead of line-by-line review of generated code.

**Why:** AI-generated PRs are long and hard to review at human speed. Shift-left review catches wrong directions before code exists.

**How:**

1. Run Grill Me on the plan
2. Explicitly approve: "This plan is approved — build it"
3. When the PR lands, ask: "Does this match the approved plan? What drifted?"

---

## Plan before you prompt

**What:** Start with foundation — design system, monorepo, explicit spec — before prompting the agent.

**Why:** Without structure you're "prompt and pray." Multiple tables at the June meetup called this out.

**How:**

- Write a short `AGENTS.md` or rules file describing constraints
- For UI work: wireframes or tokens before codegen
- For features: bullet acceptance criteria before "build it"

---

## Token efficiency

**What:** Treat tokens as a scarce commodity. Front-load thinking so the agent doesn't burn context on the wrong problem.

**How:**

- Grill Me before big agent sessions
- Scope tasks narrowly ("add this one function" not "refactor everything")
- Use smaller models for exploration, larger for implementation

---

## Build something silly

**What:** Unrelated side project to explore tool limits and find your guardrails.

**Why:** YouTube won't teach you what 30 minutes of failing will. One group recommended hands-on play over passive tutorials.

**Try at Cafe Cursor:** Add a page to the [AR zine starter](https://github.com/luiscielak/ar-zine-starter) with a ridiculous AR layer — learn the pipeline without production pressure.

---

## Beyond Cursor

The room traded tools freely:

- **NotebookLM** — learning and synthesizing docs
- **PDF → text utilities** — feeding context into agents
- **Figma code layers** — design-to-code frontier

---

*Source: [Cursor Meetup Philadelphia — June 30, 2026](https://github.com/luiscielak/cursor-meetup/blob/main/events/2026-06-30/group-share-summary.md)*
