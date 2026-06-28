---
type: Playbook
title: Complete a Task
description: Mark an existing task as done in the tasks file.
tags: [playbook, tasks, edit]
timestamp: 2026-06-28T10:06:00Z
---

# Complete a Task

How an agent marks a task done in the [tasks file](/concepts/tasks-file.md).
Fully executable with file tools — no DB access.

## Steps

1. Read [/concepts/tasks-file.md](/concepts/tasks-file.md) for the line format.
2. Read `./data/tasks.md` and locate the line whose id `(t<N>)` matches the
   target task. If the task is named instead of numbered, match on the title.
3. Change that line's `[ ]` to `[x]`. Leave the rest of the line unchanged.
4. If the task is already `[x]`, report that it was already done.
5. Confirm to the user which task was completed.

## Examples

> User: "mark t1 as done"

The agent changes:

```
- [ ] (t1) Buy milk — 2026-06-28
```

into:

```
- [x] (t1) Buy milk — 2026-06-28
```
