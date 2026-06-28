---
type: Playbook
title: Add a Task
description: Append a new open task to the tasks file.
tags: [playbook, tasks, write]
timestamp: 2026-06-28T10:05:00Z
---

# Add a Task

How an agent adds a new task to the [tasks file](/concepts/tasks-file.md). Fully
executable with file tools — no DB access.

## Steps

1. Read [/concepts/tasks-file.md](/concepts/tasks-file.md) to confirm the line
   format and where new tasks go (appended at the bottom).
2. Read `./data/tasks.md` and find the highest existing id `t<N>`.
3. Choose the next id `t<N+1>`.
4. Append one line:
   `- [ ] (t<N+1>) <the task title> — <today's date YYYY-MM-DD>`
5. Confirm to the user what was added.

## Examples

> User: "add a task to water the plants"

The agent sees the highest id is `t3`, so it appends:

```
- [ ] (t4) Water the plants — 2026-06-28
```
