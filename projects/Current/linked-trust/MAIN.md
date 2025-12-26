# LinkedTrust

Decentralized trust platform based on LinkedClaims specification. Enables creating, validating, and connecting cryptographically signed claims to build webs of trust.

**Team Lead:** Gitonga
**Slack Channel:** #c-linked-trust

## Key Links

| Item | Link |
|------|------|
| Proposal | |
| Task Board | [Taiga](https://taiga.whatscookin.us/project/linkedtrust-1/timeline) |
| Repo(s) | [trust_claim](https://github.com/Whats-Cookin/trust_claim), [trust_claim_backend](https://github.com/Whats-Cookin/trust_claim_backend) |
| DevOps | |
| Demo | [live.linkedtrust.us](https://live.linkedtrust.us), [dev.linkedtrust.us](https://dev.linkedtrust.us) |
| Drive Folder | [Drive](https://drive.google.com/drive/folders/1SYmtkNzkTAUAVr-efP7HqeYNeVM4D5iI) |
| Client | Internal (flagship) |
| Start & End Dates | 2022 - ongoing |
| Timeline, Budget & Contacts | [Spreadsheet](https://docs.google.com/spreadsheets/d/10bkKePnTb22s-G7XYV7Ah3ntO5yPlMdPC1QPXMrwA0A/edit) |
| Calendar | [Calendar](https://calendar.google.com/calendar/u/0?cid=NGIxMDQ4NTFiZTQ5YWVlYjM2YzNiMDNlMTVjM2I5YTdmNjc4NTE1ZTg4NDMwMWM5NDk2OWZlY2MwNjgyNGY3N0Bncm91cC5jYWxlbmRhci5nb29nbGUuY29t) |
| Use cases / Design docs | [User Stories](https://docs.google.com/document/d/1qH0m67yMChDbhq-rtPQqszwuK1VYVOLRU2FKHpgLXGw/edit), [Architecture](https://docs.google.com/document/u/0/d/1vh2d3BRR9VpwmUJctO9vCGUXjrOWG6e9ZDCM5kHf7eQ/edit) |
| Marketing Sharables | [Capability Deck](https://docs.google.com/presentation/d/1tEDL4_QTAjMtxn9Bk1BC_uStEHq77oP0hrPISZ3dx6U/edit) |

*All team members should be added to [hackers](https://github.com/orgs/Whats-Cookin/teams/hackers) team, to slack channel, and to taiga. If you do not have access please ask the lead to add you.*

## Getting Started / Background

Local codebase: `parent/linked-trust/`

Key docs in that repo:
- `project-summary.md` - Overview
- `ECOSYSTEM_GUIDE.md` - SDK and patterns
- `linked-claims-spec.md` - The specification

---

## Project Notes (optional)

### Ecosystem Components

| Component | Description | Location |
|-----------|-------------|----------|
| **Core** | | |
| trust_claim | Frontend (React) | live.linkedtrust.us |
| trust_claim_backend | API (Node.js, Prisma, PostgreSQL) | api.linkedtrust.us |
| LinkedClaims SDK | TypeScript SDK | @cooperation/linked-claims |
| linked-claims-spec.md | The specification | |
| trust-claim-data-pipeline | Python pipeline for nodes/edges | |
| site-linkedtrust-us | Marketing site | linkedtrust.us |
| **Separate Projects** | | |
| linked-claims-extractor | AI extraction from PDFs/text | *should be own project* |
| certify | Volunteer badge platform | certify-platform.vercel.app |
| talent | Professional credentials | talent.linkedtrust.us |
| trustClip | Bookmarklet tools | @linked-claims/trustclip |
| claim-lexicon | ATProto integration | |
| **Other** | | |
| create-trust-app | CLI scaffolding | |
| fundraiser-trust-app | | |
| esg-demo | Demo app | |
