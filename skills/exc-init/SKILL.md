---
name: exc-init
description: Scaffold the Executive Coordination catalogs in a shared second-brain bundle.
---

# exc-init

Create the catalogs this plugin owns inside a shared knowledge root.

## Process

1. Confirm target (default `knowledge/`).
2. Run:

```bash
python3 "${CLAUDE_PLUGIN_ROOT}/scripts/exc_common.py" init-bundle \
  --bundle knowledge \
  --title "Executive Coordination" \
  --catalogs "priorities,decisions,blockers,escalations,handoffs,digests,action-items,risks,agenda-items,status-updates"
```

3. Point the user at `sample-knowledge/` for a fictional demo.

## Done when

- `knowledge/index.md` exists
- Each owned catalog has `index.md`
