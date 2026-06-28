# OKF Learning Sandbox

A hands-on sandbox for learning **[Open Knowledge Format](https://github.com/scaccogatto/okf)** (OKF v0.1) — a lightweight convention for storing durable, executable knowledge alongside your code as plain markdown files.

The bundle in [`.okf/`](.okf/index.md) describes a tiny **local task tracker** backed by [`data/tasks.md`](data/tasks.md). Every piece of knowledge is executable with file tools only — no database, no network, no extra infrastructure.

---

## What's inside

```
.okf/
  index.md                 # table of contents (reserved)
  log.md                   # change history (reserved)
  concepts/
    tasks-file.md          # describes data/tasks.md and its line schema
  playbooks/
    add-task.md            # step-by-step: append a new task
    complete-task.md       # step-by-step: mark a task done
data/
  tasks.md                 # the actual task list
CLAUDE.md                  # wires the bundle into Claude Code
```

## How it works

An OKF bundle is a directory of markdown files. Each file (except the two reserved ones) carries YAML frontmatter with a `type` field:

```yaml
---
type: Playbook
title: Add a Task
description: Append a new open task to the tasks file.
tags: [playbook, tasks, write]
timestamp: 2026-06-28T10:05:00Z
---
```

Relationships between concepts are encoded as ordinary markdown links — the knowledge graph emerges from the links you'd write anyway. No adjacency list, no graph database.

When `CLAUDE.md` tells the agent to consult the bundle before touching tasks, the agent reads the index, follows the matching playbook, and acts — start to finish, no extra prompting.

## Try it in Claude Code

Open this repo in a Claude Code session and try:

```
add a task to call the bank
```

```
mark t1 as done
```

The agent will consult `.okf/`, follow the playbook, and edit `data/tasks.md` directly.

## OKF skills

If you have the [OKF plugin](https://github.com/scaccogatto/okf-skills) installed:

| Command | What it does |
|---------|--------------|
| `/okf:validate .okf --strict` | Conformance check — every non-reserved file must have a `type` |
| `/okf:visualize` | Generates a self-contained `viz.html` interactive graph |

## Conformance

A bundle is conformant when every non-reserved `.md` file has parseable YAML frontmatter with a non-empty `type`. Quick check:

```bash
grep -rL "^type:" .okf --include="*.md"
# Only index.md and log.md should appear
```

## Learn more

- [OKF spec](https://github.com/scaccogatto/okf) — the full format reference
- [Blog post](https://blog.zakaria.lu/okf-open-knowledge-format-guide) — write-up from this session
