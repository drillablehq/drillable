# drillable

**Ground your coding agent.** Install drillable and your agent *audits its own work against cited
sources* instead of guessing — reference claims (the MCP spec, agent & LLM practices, networking,
units, and ~100 more domains) get grounded against the corpus, and where there's no record it says
**"no record"** instead of bluffing.

```
/plugin marketplace add drillablehq/marketplace
/plugin install drillable@dev
/plugin enable drillable@dev        # then /reload-plugins
```

No account, no key — the reference corpus is a no-auth gateway. That's the whole install; your agent
is grounded.

## The two ways to use it

drillable is an **audit** tool — check the work against an independent source. Two timings:

- **`/with-drillable`** — turn on **grounded mode**: the agent continuously checks its work against
  drillable *as a solution emerges*. Use it when you're starting something technically tricky and want
  the solution to rest on cited sources, not recall. You ignite it; the agent sustains it.
- **`/audit`** — run a **post-hoc audit** on the solution it just produced: extract the checkable
  claims, verify each against drillable, and report what holds, what's **corrected**, and what's an
  unverified assumption to double-check.

## Optionally: ground your *project's own* facts

Point drillable at a folder of your markdown — docs, decisions, conventions — and it grounds your
project's facts the same way (stops the agent contradicting choices you've already made). Runs locally;
your files stay your source of truth:

```
claude mcp add drillable-context -- npx -y drillable-context --facts-dir /path/to/your/docs --name context
```

## Gate your dependencies in CI

The same grounding, enforced on every PR: **[drillable check](https://github.com/drillablehq/check)**
(`npx drillable-check` / `uses: drillablehq/check@v1`) audits your dependencies against the live
registry + OSV — the deterministic, team-wide version of what the plugin does live.

---

Operated by Drillable LLC. The reference corpus: <https://drillable.com>.
