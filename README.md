# Executive Coordination

Chief-of-staff ContentPack: priorities, decisions, blockers, escalations, digests, handoffs, and action items. Writes into a shared second brain.

MIT. Dual-host: **Claude Code**, **Grok Build**, and **Codex** (Agent Skill Standard). Writes OKF Markdown + YAML into a shared second-brain bundle so other agents and local jobs can read the same graph.

## Install

```bash
# Claude Code
/plugin marketplace add SpillwaveSolutions/executive-coordination
/plugin install executive-coordination@SpillwaveSolutions

# Skilz CLI
skilz install SpillwaveSolutions/executive-coordination
```

Point the plugin at a shared knowledge root (default `knowledge/`). All sibling ContentPack plugins write into the same tree.

## Skills

| Skill | What it does |
|-------|----------------|
| `/exc-init` | Scaffold the catalogs this plugin owns |
| `/exc-capture` | Capture a noun into the shared second brain (deterministic write) |
| `/exc-pack` | Build a bounded ContextPack from a root concept |
| `/exc-validate` | Validate frontmatter, types, and links |
| `/exc-session` | Open or close an isolated write session (worktree + PR) |
| `/exc-doctor` | Health check of the bundle this plugin owns |

## Nouns this plugin may write

| Type | Meaning |
|------|---------|
| `Priority` | Ranked current focus item |
| `Decision` | Settled choice with rationale |
| `Blocker` | Something preventing progress |
| `Escalation` | Issue raised to a higher owner |
| `Handoff` | Work transferred between agents |
| `DailyDigest` | Morning coordination brief |
| `WeeklyDigest` | Weekly rollup |
| `AgendaItem` | Meeting or standup item |
| `ActionItem` | Assigned next step with due date |
| `StatusUpdate` | Snapshot of current state |
| `Risk` | Potential future problem |
| `Dependency` | Work that must complete first |
| `MeetingNote` | Captured meeting record |
| `RoutingRule` | How work is assigned |
| `CapacityNote` | Who has slack this week |

## Relationships

| `rel` | Meaning |
|-------|---------|
| `blocks` | Source blocks target |
| `depends_on` | Source depends on target |
| `escalates_to` | Raised to owner |
| `assigned_to` | Owner of the action |
| `decides` | Decision governs target |
| `originates_from` | Came from meeting or digest |
| `related_to` | Soft association |
| `supersedes` | Replaces older priority or decision |

## Catalogs

- `priorities/`
- `decisions/`
- `blockers/`
- `escalations/`
- `handoffs/`
- `digests/`
- `action-items/`
- `risks/`
- `agenda-items/`
- `status-updates/`

## Deterministic write boundary

The model proposes. Schema-enforced scripts commit:

```bash
python3 scripts/exc_common.py write \
  --bundle knowledge \
  --type Priority \
  --folder priorities \
  --title "Example" \
  --author "Grok Bot: Executive Coordination"
```

Never invent `rel` values. Never write types owned by another plugin.



## Related plugins

- [second-brain-core](https://github.com/SpillwaveSolutions/second-brain-core) — shared pack engine and typed-edge conventions
- [project-knowledge-capture](https://github.com/SpillwaveSolutions/project-knowledge-capture) — the “why” second brain
- [system-architecture-capture](https://github.com/SpillwaveSolutions/system-architecture-capture) — the “what is running” second brain
- [wiki_ticket_sdd](https://github.com/SpillwaveSolutions/wiki_ticket_sdd) — visible work log

## Multi-host

Works with Claude Code, Grok Build, Codex, Agent Plugins 1.0 clients, Grok Bot, and LangChain Deep Agents.

| Host | How to load |
|------|-------------|
| Claude Code | marketplace + plugin install |
| Grok Build | zero-config Claude plugin |
| Codex | Agent Skills / `hooks/hooks.json` |
| Agent Plugins clients | root `plugin.json` + `skills/` |
| Grok Bot | [docs/GROK_BOT.md](docs/GROK_BOT.md) |
| LangChain Deep Agents | [docs/LANG_CHAIN_DEEP_AGENTS.md](docs/LANG_CHAIN_DEEP_AGENTS.md) |

Write isolation (worktree + PR) lives in second-brain-core: [docs/ISOLATION.md](https://github.com/SpillwaveSolutions/second-brain-core/blob/main/docs/ISOLATION.md). Point `SECOND_BRAIN_ROOT` at the session bundle. Never hard-code a private remote.

Eight job-function plugins plus core. Knowledge root is always a local path or env the human already owns.

## License

MIT. Copyright 2026 Rick Hightower / contributors.
