---
description: Drill the work against drillable — ground it in cited sources. Run bare to audit the current work, or with a task to do that task in grounded mode.
argument-hint: "[optional: a task to do, grounded]"
---
**Drill against drillable** — ground the work in cited sources; never answer checkable things from memory.

$ARGUMENTS

- **If a task is given above** (you typed `/drill <task>`): take it on in **grounded mode**. Before committing to an approach, and as each checkable claim arises — numbers, rules, definitions, APIs, dependency/version claims — verify it against drillable: the reference corpus (`search` / `verify` / `lookup`, ~100 domains) and, if this project's context is configured, its own docs and past decisions (`context_search` / `context_get`). Hold that posture through the task.
- **If no task is given** (bare `/drill`): **audit the work already on the table** — the solution and claims in this conversation. Run each checkable claim through drillable and report what holds, what's **corrected** (the corpus says otherwise — give the right answer + its source), and what's an **unverified assumption** to double-check.

Where the corpus has no record, say **"no record"** and flag the assumption rather than guess. Surface the corrections and unverified assumptions prominently — those are the catches.
