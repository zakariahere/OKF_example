# Task Tracker Knowledge Bundle

> A tiny, hand-written OKF bundle for a **local task tracker**. Every concept's
> knowledge is fully **executable with file tools only** — no database, no
> network. Built to learn OKF v0.1 in a live Claude Code session.

`index.md` is a **reserved** file: the table of contents for this directory. It
is not a concept document, so it carries no `type`.

## Concepts in this bundle

| Concept | Type | Description |
|---------|------|-------------|
| [tasks-file](/concepts/tasks-file.md) | Local File | The real markdown checklist at `./data/tasks.md` |
| [add-task](/playbooks/add-task.md) | Playbook | Append a new open task |
| [complete-task](/playbooks/complete-task.md) | Playbook | Mark a task done |

## The concept graph

```
add-task (Playbook) ──────▶ tasks-file (Local File) ──┐
                                                       │  ./data/tasks.md
complete-task (Playbook) ─▶ tasks-file (Local File) ──┘
```

The `resource` of `tasks-file` points at a real file in the repo, so following
the knowledge leads to something an agent can actually open and edit.

## How to use this bundle

1. Launch a Claude Code session in this repo.
2. Ask something like *"add a task to call the bank"* or *"mark t1 as done"*.
3. Claude consults this bundle (see `../CLAUDE.md`), follows the matching
   playbook, and edits `./data/tasks.md` — start to finish, no DB.

Change history lives in [log.md](/log.md).
