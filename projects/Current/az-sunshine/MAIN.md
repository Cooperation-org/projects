# AZ-Sunshine

Transparency Project: Arizona Sunshine aims to improve public transparency by aggregating, visualizing, and analyzing independent expenditures (IEs), contributions, and political actions by candidates and entities in Arizona elections.

**Team Lead:**
**Slack Channel:**

## Key Links

| Item | Link |
|------|------|
| Proposal | |
| Task Board | |
| Repo(s) | [Cooperation-org/Az-Sunshine](https://github.com/Cooperation-org/Az-Sunshine) |
| DevOps | |
| Demo | [167.172.30.134](http://167.172.30.134/) |
| Drive Folder | [Drive](https://drive.google.com/drive/folders/1UgxBFkkeB7T6_G9JAY7MgzDC2RpL9LfZ) |
| Client | |
| Start & End Dates | |
| Timeline, Budget & Contacts | |
| Calendar | |
| Use cases / Design docs | |
| Marketing Sharables | |

*All team members should be added to [hackers](https://github.com/orgs/Whats-Cookin/teams/hackers) team, to slack channel, and to taiga. If you do not have access please ask the lead to add you.*

## Getting Started / Background

See Project Notes below for phased plan and data sources.

---

## Project Notes

### Core Goals

1. Aggregate, visualize, and act on total IE spending for/vs candidates.

2. Track the flow of contributions through PACs to individuals.

3. Correlate contributions with legislative actions and public statements.

### Phased Plan

#### Phase 1 – Proof of Concept (6 weeks)

- Spider "Statements of Interest" from the AZ SOS site.

- Extract candidate emails and track outreach manually.

- Download static copy of the Independent Expenditure (IE) database.

- Build a Django-based transparency web app with data models for candidates, races, expenditure committees, and donor entities.

- Design and test public visualizations and dashboards with the client.

- Estimated Cost: $2,400 (may decrease with volunteer contributions).

- Deliverable: Working prototype of transparency dashboard + initial datasets.

#### Phase 2 – Automations

- Clean and normalize Phase 1 data.

- Automate database updates and duplicate removal.

- Add time-based visualizations.

- Automate email sending and tracking.

#### Phase 3 – Lobbyist, RTS, and Vote Correlations

- Integrate Lobbyist data, RTS (Request to Speak), and bill vote records.

- Correlate financial influence with legislative behavior.

- Develop influence scoring and trend visualization.

#### Phase 4 – Financial Disclosures & Long-Tail Data

- Parse PDF financial disclosures using NLP/LLM tools.

- Process campaign websites and social media for policy alignment.

- Enable trusted-user submissions for candidate social links and statements.

### Technical Specifications & Data Sources

| Area | Description | Key Data Sources |
| :---- | :---- | :---- |
| Candidate Tracking | Daily spider of AZ SOS Statements of Interest | https://azsos.gov/elections/candidates/statements-interest |
| Independent Expenditures | Full IE DB download and aggregation | https://seethemoney.az.gov/ |
| Donor + PAC Mapping | Donor relationships and aggregation by race/candidate | AZ SOS database purchase ($25) |
| Lobbyist Data | Expenditure and contact databases | https://apps.azsos.gov/files/lobbying/expenditure/ |
| Legislative Votes | Bill and vote tracking | https://www.azleg.gov/bills/ |
| Financial Disclosures | Candidate financial statements (PDF parsing) | https://apps.arizona.vote/electioninfo/assets/ |
| Social Media & Statements | AI/LLM-based extraction from public content | Various public campaign sources |

### Team Tasks (Phase 1 Priority)

- Golda Velez – Client communication, data architecture oversight

- Ben – Data sourcing & validation (candidate and expenditure data)

- Amos Mwangi – Project documentation, web app structure setup, onboarding interns

- Peter / Interns – Data collection, email extraction, initial visualization support

### Next Steps

1. Review and confirm scope and priorities in this document.

2. Set up shared Drive folder structure and link docs here.

3. Begin Phase 1 work (candidate spider + Django setup).

4. Hold 15-min sync with Adam.
