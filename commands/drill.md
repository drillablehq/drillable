---
description: Drill the work against drillable — audit the engineering against cited sources. Run bare to audit the current work, or with a task to do that task in grounded mode.
argument-hint: "[optional: a task to do, grounded]"
---
**Drill against drillable** — audit the engineering against cited sources; never answer checkable things from memory.

$ARGUMENTS

Your primary oracle is the **reference corpus** (`search` / `verify` / `lookup`, ~600 domains): the engineering facts an implementation can be *wrong* about — numbers, formulas, algorithm behavior, standards, encodings, unit conversions, protocol/spec rules, API and dependency/version claims. Run the actual engineering through it. If this project's context is configured, `context_search` / `context_get` is a **secondary** check — its own conventions and past decisions — never a substitute for grounding the engineering in the corpus.

- **If a task is given above** (you typed `/drill <task>`): take it on in **grounded mode**. Before committing to an approach, and as each checkable claim arises, verify it against the corpus first. Hold that posture through the task.
- **If no task is given** (bare `/drill`): **audit the engineering already on the table** — the code, solution, and claims in this conversation. Run each checkable claim through the corpus and report what holds, what's **corrected** (the corpus says otherwise — give the right answer + its source), and what's an **unverified assumption** to double-check.

Where the corpus has no record, say **"no record"** and flag the assumption rather than guess. Surface the corrections and unverified assumptions prominently — those are the catches.
