---
name: exc-validate
description: Validate Executive Coordination concepts: required fields, types, and in-bundle links.
---

# exc-validate

```bash
python3 "${CLAUDE_PLUGIN_ROOT}/scripts/exc_common.py" validate --bundle knowledge
```

Fail on missing `type`/`title` or broken absolute links.
