# Use Drillable

A Claude Code plugin that makes your **coding agent ground reference claims** in a real,
[Drillable](https://drillable.com)-cited source instead of answering from memory — the MCP spec,
agent & LLM practices, networking, units, and dozens more. So you stop prefixing prompts with
"use drillable to…".

This plugin is **reach only.** Claim *verification* is a separate product — **Drillable Check** —
because Check is a service consumed from many surfaces (CLI, CI, IDEs, web), most of which aren't
Claude Code. You don't bundle a service into a plugin; you call it. (Repo: `drillablehq/drillable-check`.)

## What it installs

| Component | Job |
| --- | --- |
| MCP connection (`.mcp.json`) | makes `verify` / `search` / `lookup` available to your agent |
| Reach skill (`skills/drillable-reach`) | a model-invoked nudge: ground a reference claim before asserting it |

That's the whole job — a *trigger* (the skill) + the *target* (the corpus connection). The skill is
discretionary: it nudges a model that's willing to look something up. It deliberately does **not**
try to catch confident-wrong claims — that needs Drillable Check's deterministic hook, which lives
with that product.

## Install

```
/plugin marketplace add drillablehq/use-drillable
/plugin install use-drillable@drillable
```

Ships **disabled** (`defaultEnabled: false`): it connects to an external service and your queries
are logged as demand signal, so enabling it is an explicit choice.

## Before publishing

```
claude plugin validate ./ --strict
```

Confirm the root-as-plugin `source: "./"` in `marketplace.json` and the remote MCP `type`/`url` in
`.mcp.json`.
