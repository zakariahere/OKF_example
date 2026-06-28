---
type: Local File
title: Tasks File
description: A plain-markdown checklist of tasks, stored in the repo.
resource: file://./data/tasks.md
tags: [tasks, local, markdown, executable]
timestamp: 2026-06-28T10:00:00Z
---

# Tasks File

The single source of truth for the task tracker. It is a real file at
`./data/tasks.md`, so any agent with file tools can read and edit it directly —
no database or network required.

## Schema

Each task is one markdown checklist line with this exact shape:

```
- [ ] (t<N>) <title> — <YYYY-MM-DD>
```

| Part | Meaning |
|------|---------|
| `[ ]` / `[x]` | open / done |
| `(t<N>)` | unique id, `t` + an integer (e.g. `t4`) |
| `<title>` | free text describing the task |
| `— <YYYY-MM-DD>` | the date the task was added |

The file always starts with a `# Tasks` heading. New tasks are appended at the
bottom.

## Examples

```
- [ ] (t1) Buy milk — 2026-06-28
- [x] (t2) Send the invoice to Acme — 2026-06-27
```

## Citations

- Operated on by the [add-task](/playbooks/add-task.md) and
  [complete-task](/playbooks/complete-task.md) playbooks.
