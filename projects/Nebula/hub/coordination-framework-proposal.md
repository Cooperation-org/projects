# Coordination Framework Proposal

Expand slack-helper into a coordination hub that reads from multiple sources of truth and acts via Slack.

## Approach

**Don't reinvent sources of truth. Read from them.**

| Source of Truth | What it holds |
|-----------------|---------------|
| `projects/` repo | Project metadata, team, which tools used where |
| Taiga | Tasks, milestones, earnings/tokens |
| GitHub Issues | Tasks, PRs |
| Slack | Conversations |
| LinkedTrust | Attestations |

**Hub's job:**
- Parse `projects/` repo to know which adapters to use for each project
- Read from Taiga, GitHub, Slack
- Aggregate, search, report
- Send nudges and summaries via Slack
- Serve dashboards (later)

## Why Expand slack-helper

The slack-helper repo already has:
- Clean FastAPI structure
- Working Slack integration with rate limiting
- ChromaDB + PostgreSQL hybrid pattern
- Multi-tenant workspace isolation
- Q&A and newsletter services

Kene's commits are preserved. We rename and expand, not rewrite.

## Key Constraint: Hub is One Participant Among Many

**We don't control people. We help them.**

Hub reads and writes to the same systems everyone else uses:
- **Slack**: read messages, write nudges/summaries
- **Taiga**: read tasks, write new tasks or update status
- **GitHub**: read issues/PRs, write comments or create issues
- **projects repo**: read config, write updated goals/docs

Hub has no special authority. It's one actor among many - people, Claude Code, Cursor, other bots all interact with these same systems.

If people prefer other tools, that's fine. Hub is optional and additive.

## How projects/ repo configures hub

Option A: **Structured YAML frontmatter** (parseable, less error-prone)

```markdown
---
slack_channel: "#c-myproject"
taiga_board: "myproject"
github_repo: "Cooperation-org/myproject"
---

# My Project

Human-readable description...
```

Option B: **Separate config file** per project

```
projects/SomeProject/
├── MAIN.md          # human-readable, freeform
├── config.yaml      # machine-readable, structured
└── CLAUDE.md
```

Option C: **Central registry** (single file, all projects)

```yaml
# projects/registry.yaml
projects:
  myproject:
    slack: "#c-myproject"
    taiga: "myproject"
    github: "Cooperation-org/myproject"
```

The projects repo remains the source of truth for *project configuration*. Hub reads it but doesn't write to it. Other tools (Claude Code, Cursor, human editors) can also read/modify it.

## Expanded slack-helper Structure

```
hub/                              # renamed from slack-helper
├── backend/
│   ├── src/
│   │   ├── adapters/             # NEW - read from sources of truth
│   │   │   ├── __init__.py
│   │   │   ├── base.py           # adapter interface
│   │   │   ├── projects_repo.py  # parse MAIN.md files from git
│   │   │   ├── taiga.py          # tasks, earnings, tokens
│   │   │   └── github.py         # issues, PRs
│   │   │
│   │   ├── collector/            # EXISTING - slack
│   │   │   ├── slack_client.py   # already done
│   │   │   └── processors/
│   │   │
│   │   ├── services/             # EXISTING + NEW
│   │   │   ├── qa_service.py           # existing
│   │   │   ├── newsletter_service.py   # existing
│   │   │   ├── query_service.py        # existing
│   │   │   ├── earnings_service.py     # NEW - aggregate from taiga
│   │   │   └── nudge_service.py        # NEW - find stale/blocked
│   │   │
│   │   ├── bots/                 # NEW - proactive behaviors
│   │   │   ├── __init__.py
│   │   │   ├── nudge.py          # remind blocked tasks
│   │   │   ├── standup.py        # collect/summarize standups
│   │   │   └── onboard.py        # guide interns
│   │   │
│   │   ├── api/                  # EXISTING
│   │   │   ├── main.py
│   │   │   └── routes/
│   │   │
│   │   └── db/                   # EXISTING
│   │       ├── chromadb_client.py
│   │       ├── connection.py
│   │       └── repositories/
│   │
│   └── scripts/                  # EXISTING
│
└── frontend/                     # EXISTING (dashboards later)
```

## What We Add to slack-helper

slack-helper already has working:
- Slack integration (read/write messages)
- ChromaDB (semantic search)
- PostgreSQL (metadata)
- Q&A service (RAG)
- Newsletter generation

We add:

1. **Taiga adapter** - read/write tasks, aggregate earnings
2. **GitHub adapter** - read/write issues and PRs
3. **projects repo adapter** - read config, write updates
4. **Bots** - proactive nudges, standup collection, onboarding guidance

## Implementation Phases

### Phase 1: Taiga Integration
- Read tasks and user stories
- Aggregate earnings/tokens per person
- Report on project progress

### Phase 2: GitHub Integration
- Read issues and PRs
- Post comments, create issues
- Track stale PRs

### Phase 3: Projects Repo Integration
- Parse project config (however we decide to structure it)
- Know which Slack/Taiga/GitHub to use per project
- Maybe write updates to goals/docs

### Phase 4: Bots
- Nudge bot (blocked tasks, stale PRs)
- Standup bot (collect/summarize)
- Onboard bot (guide interns through tasks)

## Future Possibilities

- **Event bus** - if we need loose coupling between adapters/bots
- **ATProto integration** - decentralized social, Bluesky
- **More chat adapters** - Discord, Telegram, SMS
- **Dashboards** - the frontend/ directory is already there

## Secrets Management

Hub needs credentials for Slack, Taiga, GitHub, etc. If compromised, all are exposed.

Keep it simple:
- Env file for dev
- Secrets manager (Doppler, AWS, etc.) for production
- Use minimal scopes on all tokens
- Consider: should this run on its own isolated server?

## Open Questions

1. How to structure project config in projects repo? (YAML frontmatter, separate file, central registry?)
2. What's the first useful thing we can demo with Taiga integration?
3. Should bots run as separate processes or all-in-one?
4. Is hub critical enough to warrant split servers for isolation?

---

*Proposal based on analysis of hub, slack-helper, and projects repos. December 2025.*
