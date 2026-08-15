---
name: exc-capture
description: Capture a Executive Coordination noun into the shared second brain via the deterministic write helper.
---

# exc-capture

## Process

0. If more than one agent writes the shared brain, open an isolation session (`exc-session`) and export `SECOND_BRAIN_ROOT`.
   Claim identity `grok-bot/executive-coordination` (or `deep-agents/executive-coordination` on Deep Agents).
1. Identify the noun type from the allowed list (see README).
2. Collect title, status, author identity, and optional typed links.
3. Write with the helper — do not hand-author frontmatter unless the user insists:

```bash
python3 "${CLAUDE_PLUGIN_ROOT}/scripts/exc_common.py" write \
  --bundle knowledge \
  --type Priority \
  --folder priorities \
  --title "Example Priority" \
  --author "Grok Bot: Executive Coordination" \
  --tags "exc"
```

4. Add typed links in a follow-up edit if needed (`rel` values from `docs/typed-edges.md`).
5. Validate.

Allowed types: Priority, Decision, Blocker, Escalation, Handoff, DailyDigest, WeeklyDigest, AgendaItem, ActionItem, StatusUpdate, Risk, Dependency, MeetingNote, RoutingRule, CapacityNote.
