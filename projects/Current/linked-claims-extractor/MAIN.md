# Linked Claims Extractor

AI-powered claim extraction from PDFs and text. Uses Claude/OpenAI to identify claims, then publishes to LinkedTrust.

**Team Lead:**
**Slack Channel:**

## Key Links

| Item | Link |
|------|------|
| Proposal | |
| Task Board | |
| Repo(s) | |
| DevOps | |
| Demo | |
| Drive Folder | |
| Client | Internal (LinkedTrust ecosystem) |
| Start & End Dates | |
| Timeline, Budget & Contacts | |
| Calendar | |
| Use cases / Design docs | |
| Marketing Sharables | |

*All team members should be added to [hackers](https://github.com/orgs/Whats-Cookin/teams/hackers) team, to slack channel, and to taiga. If you do not have access please ask the lead to add you.*

## Getting Started / Background

Local codebase: `parent/linked-trust/linked-claims-extractor/`

**Components:**
- `claim_extractor/` - Python library for extraction (published to PyPI)
- `pdf_parser/` - Flask web app for uploading PDFs
- `service/` - API service (separate deployment)

**Tech Stack:**
- Python, Flask
- Claude/OpenAI for extraction
- Publishes to LinkedTrust API
