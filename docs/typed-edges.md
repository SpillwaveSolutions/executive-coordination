# Typed edges — Executive Coordination

Direction matters. Packs follow outbound edges by default.

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

Unknown `rel` values are treated as `info` by validation. Do not invent new names in this plugin.
