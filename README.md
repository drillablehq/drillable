# drillable

**Ground your coding agent.** Install drillable and your agent *audits its own work against cited
sources* instead of guessing — reference claims (the MCP spec, agent & LLM practices, networking,
units, and ~100 more domains) get grounded against the corpus, and where there's no record it says
**"no record"** instead of bluffing.

```
/plugin marketplace add drillablehq/marketplace
/plugin install drillable@drillable
```

No account, no key — the reference corpus is a no-auth gateway. That's the whole install; your agent
is grounded.

## Two ways to use it — one command

drillable is an **audit** tool — check the work against an independent source. The **`/drill`**
command does both timings:

- **`/drill <task>`** — take on a task in **grounded mode**: the agent checks each checkable claim
  against drillable *as the solution emerges*. Use it when you're starting something technically tricky
  and want the solution to rest on cited sources, not recall.
- **`/drill`** (bare) — run a **post-hoc audit** on the answer already on the table: extract the
  checkable claims, verify each against drillable, and report what holds, what's **corrected**, and
  what's an unverified assumption to double-check.

## Optionally: ground your *project's own* facts

Point drillable at a folder of your markdown — docs, decisions, conventions — and it grounds your
project's facts the same way (stops the agent contradicting choices you've already made). Runs locally;
your files stay your source of truth:

```
claude mcp add drillable-context -- npx -y drillable-context --facts-dir /path/to/your/docs --name context
```

## Optionally: drill your own *session history*

Turn your own Claude Code sessions into a grounded, searchable record — *"what did I do about X", "when did
I last touch Y", "how did we decide Z"* — answered from the actual turn, not recall. One command reads
`~/.claude/projects`, indexes it locally, and prints the line to wire it in:

```
npx -y drillable-context sessions
```

Runs locally (your transcripts never leave your machine), converts incrementally, and stays current on its
own — new sessions are picked up automatically. Scoped to the current project by default; `project="all"`
spans every repo.

## Gate your dependencies in CI

The same grounding, enforced on every PR: **[drillable check](https://github.com/drillablehq/check)**
(`npx drillable-check` / `uses: drillablehq/check@v1`) audits your dependencies against the live
registry + OSV — the deterministic, team-wide version of what the plugin does live.

---

Operated by Drillable LLC. The reference corpus: <https://drillable.com>.
