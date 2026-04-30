# Hillgate MiCAR – Task Tracker

Interactive tracker and visualization for the 77 questions in the AFM's request-for-information letter (DnGi-26041956, 28 April 2026).

## Run

No build step. Serve the folder over HTTP (because of `fetch`):

```
python3 -m http.server 8000
# open http://localhost:8000
```

## Files

- `tasks.json` — single source of truth (id, status, priority, section, topic, primary/secondary owner, notes). Edit this to update tasks.
- `index.html` — UI with two views:
  - **Graph** — force-directed network. Nodes = tasks, sized/colored by priority tier, ringed by status. Edges link tasks that share a section (grey), share an owner across sections (grey), or share a cross-cutting theme (orange: "Execution <> Exchange", "Website design topic", "Wessel").
  - **Table** — sortable list with the same filters.
- Sidebar filters: priority, status, owner, section, plus full-text search.
