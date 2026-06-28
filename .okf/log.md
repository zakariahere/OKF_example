# Change Log

`log.md` is a **reserved** file recording the change history of this bundle. It
is not a concept document and needs no `type`. Newest entries first.

## 2026-06-28

- Replaced the bookstore/BigQuery example with a **local task tracker** whose
  knowledge is executable with file tools only (no DB access).
- Added concepts: `tasks-file` (Local File), `add-task` (Playbook),
  `complete-task` (Playbook).
- Created the backing data file `./data/tasks.md` with three sample tasks.
- Concept graph: `add-task` → `tasks-file` ← `complete-task`.
