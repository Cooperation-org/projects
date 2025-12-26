# CivicSky

Civic engagement bridge connecting independent publishers (Ghost CMS) to Bluesky social network, embedding actionable civic opportunities directly into content.

**Team Lead:** Sahda Samier ("Sia")
**Slack Channel:** #civworks-atproto

## Key Links

| Item | Link |
|------|------|
| Proposal | [SOW](https://docs.google.com/document/d/13NjGfi4OO5L3QCJxvxDtfyk0LibDAZ4LiS4Wpxt48pk/edit?tab=t.0#heading=h.nti8hm67kwqm) |
| Task Board | [Taiga](https://taiga.linkedtrust.us/project/civicsky/kanban) |
| Repo(s) | [ghost-atproto](https://github.com/Cooperation-org/ghost-atproto), [koenig-civic-action-card](https://github.com/Cooperation-org/koenig-civic-action-card) (npm package) |
| DevOps | |
| Demo | [bridge.linkedtrust.us](https://bridge.linkedtrust.us/) (malware alert - investigating) |
| Drive Folder | [Drive](https://drive.google.com/drive/u/0/folders/1BKXQh5MEmYkLG8i9bJt-4ukP5WN30oOk) |
| Client | George Polisner |
| Start & End Dates | 24/9/2025 to |
| Timeline, Budget & Contacts | [Spreadsheet](https://docs.google.com/spreadsheets/d/1nEm9scS9wEzF3w5CKXfIOgOI-vHSbQoKeifrvOdgNd4/edit#gid=0) |
| Calendar | [Calendar](https://calendar.google.com/calendar/u/0?cid=NGIxMDQ4NTFiZTQ5YWVlYjM2YzNiMDNlMTVjM2I5YTdmNjc4NTE1ZTg4NDMwMWM5NDk2OWZlY2MwNjgyNGY3N0Bncm91cC5jYWxlbmRhci5nb29nbGUuY29t) |
| Use cases / Design docs | |
| Marketing Sharables | |

*All team members should be added to [hackers](https://github.com/orgs/Whats-Cookin/teams/hackers) team, to slack channel, and to taiga. If you do not have access please ask the lead to add you.*

## Getting Started / Background

See repo READMEs for setup.

**Components:**
- [ghost-atproto](https://github.com/Cooperation-org/ghost-atproto) - Bridge (Express backend + Next.js frontend + Prisma/PostgreSQL)
- [koenig-civic-action-card](https://github.com/Cooperation-org/koenig-civic-action-card) - npm package for civic action cards in Ghost editor, includes installer scripts to recompile Ghost assets
- Ghost Shim - sidecar on Ghost site to integrate bridge comments back into Ghost
