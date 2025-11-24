# Cooperation Toolkit - Initial Thoughts

## Vision

Enable any team to share ownership equitably through earned governance.

Traditional corporations fail to truly empower employees and are vulnerable to hostile takeover that subverts original purpose. Even without takeover, pressures mount to abandon principles.

This toolkit provides the "DNA" for teams who want:
- Fairness to contributors working with limited funding
- Trust, accountability, and authentic power-sharing
- Anti-capture design - governance earned through contributions, not purchased
- Transparency over permission - visibility into decisions without voting delays

## Target Users

Any team that wants to share ownership - tech startups, construction companies, nonprofits, cooperatives. Not all are technical. Many work from mobile devices in the field.

## Core Flow

```
Task Created
    ↓
Value Assigned (points, $, hours)
    ↓
Work Done
    ↓
Peer Reviewed
    ↓
Completed → Earnings Recorded
    ↓
Attestation Issued (LinkedTrust)
    ↓
Equity Updated (SlicingPie, Fairmint, etc.)
```

## Pluggable Components

### Equity/Earnings Backend
- SlicingPie (simpler, spreadsheet-friendly)
- Fairmint (tokenized cap table, liquidity without exit)
- Custom ledger / database
- Crypto tokens

### Task Backend
- Taiga (we have working earnings aggregation code)
- GitHub Issues/Projects
- Linear, Asana
- Simple database for non-technical teams

### Interface Layer
- Slack bot (universal - everyone uses chat)
- Web UI (future)
- Mobile-first (field workers, global teams)

## What the Toolkit Provides

### For Teams
- Adapter interfaces for any task + equity backend combination
- Slack bot that works across backends
- Governance playbook docs (roles, processes, decision-making)
- Onboarding templates and flows
- Attestation integration for verifiable work history

### For Interns/Contributors
- Clear pathway: intern → contributor → founder
- Portable credentials proving real contributions
- Peer vouching and critical feedback
- Earned equity from day one (if team chooses)

## Principles from LinkedTrust Experience

- **Transparency not permission** - "With enough eyes, all bugs are shallow" applies to more than code
- **Earned governance** - those doing valuable work get say, without overhead
- **Work-weighted voting** - when votes happen, weighted by contribution
- **Opportunity to object** - baked into process, not afterthought
- **Cultural technology** - documenting practices in repo with AI helpers creates living DNA

## AI Integration

- AI assistants load team playbook as context
- AI can help draft tasks, never create busywork for humans
- Slack bot powered by AI for natural language task creation
- AI helps with peer review, retrospectives, documentation

## Open Questions

- Minimum viable version for non-technical teams?
- Teams without Slack - SMS? WhatsApp? Email?
- How lightweight can "simple database" backend be?
- Pricing/licensing - open source core? Hosted service?
- How to bootstrap adoption without dedicated sales?

## Existing Assets

- Taiga earnings aggregation scripts (Python/PostgreSQL)
- LinkedTrust/LinkedCreds attestation infrastructure
- coop-projects repo as example playbook
- Case study and presentation materials
