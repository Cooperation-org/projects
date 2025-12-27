# Intern Onboarding Program

Build a structured onboarding program for interns using GitHub Projects and issue templates, with LinkedTrust attestations on completion.

**Team Lead:** Golda  
**Slack Channel:** #internship-project

## Key Links

| Item | Link |
|------|------|
| GitHub Repo | https://github.com/Cooperation-org/onboarding |
| Taiga | N/A - using GitHub for this project |
| LinkedTrust | https://linkedtrust.us |
| LinkedCreds | https://linkedcreds.com |

## Goals

1. Interns complete onboarding tasks that demonstrate understanding of team patterns
2. Completion earns verifiable attestations via LinkedTrust
3. Peers can vouch for quality of work
4. Program itself is built with intern help (meta!)

## Current Intern

- Marketing/relations focus, not technical
- Interested in helping BUILD the internship program
- Should receive certificate after completing work + peer attestations

## Required Reading (Onboarding Content)

Interns must read and demonstrate understanding of:

1. [Playing on an Organic Team](https://www.whatscookin.us/playing-on-an-organic-team/)
2. [How to Jump on a Moving Project](https://www.whatscookin.us/how-to-jump-on-a-moving-project/)
3. ROLES.md in coop-projects repo
4. Project-specific MAIN.md for any project they join

---

## GitHub Setup Instructions (for Claude Code)

### Create Repo

```bash
gh repo create Cooperation-org/intern-onboarding --public --description "Onboarding program for LinkedTrust interns"
```

### Create Issue Templates

Create `.github/ISSUE_TEMPLATE/` directory with these templates:

#### 1. `reading-comprehension.yml`

For tasks where intern reads material and demonstrates understanding.

```yaml
name: Reading Comprehension Task
description: Read and demonstrate understanding of team materials
title: "[READ] "
labels: ["onboarding", "reading"]
body:
  - type: markdown
    attributes:
      value: |
        Complete this reading and demonstrate your understanding.
  - type: input
    id: material
    attributes:
      label: Material to Read
      placeholder: URL or document name
    validations:
      required: true
  - type: textarea
    id: summary
    attributes:
      label: Your Summary
      description: In your own words, what are the key takeaways?
    validations:
      required: true
  - type: textarea
    id: application
    attributes:
      label: How You'll Apply This
      description: Give a concrete example of how you'd use this in your work
    validations:
      required: true
```

#### 2. `deliverable.yml`

For tasks with concrete output.

```yaml
name: Deliverable Task
description: Create something concrete
title: "[DELIVER] "
labels: ["onboarding", "deliverable"]
body:
  - type: markdown
    attributes:
      value: |
        This task has a concrete deliverable. Link your work when complete.
  - type: input
    id: deliverable
    attributes:
      label: What to Deliver
      placeholder: Description of expected output
    validations:
      required: true
  - type: input
    id: link
    attributes:
      label: Link to Deliverable
      placeholder: URL to your completed work
    validations:
      required: true
  - type: textarea
    id: notes
    attributes:
      label: Notes
      description: Any context or questions
```

#### 3. `peer-review.yml`

For vouching/attesting to others' work.

```yaml
name: Peer Review
description: Review and vouch for a teammate's work
title: "[REVIEW] "
labels: ["onboarding", "peer-review"]
body:
  - type: markdown
    attributes:
      value: |
        Review a teammate's completed work and provide critical feedback.
  - type: input
    id: work-reviewed
    attributes:
      label: Work Being Reviewed
      placeholder: Link to issue or deliverable
    validations:
      required: true
  - type: dropdown
    id: quality
    attributes:
      label: Quality Assessment
      options:
        - Excellent - exceeds expectations
        - Good - meets expectations
        - Needs improvement - see feedback
        - Incomplete - not ready for review
    validations:
      required: true
  - type: textarea
    id: feedback
    attributes:
      label: Specific Feedback
      description: What worked well? What could be improved?
    validations:
      required: true
  - type: checkboxes
    id: vouch
    attributes:
      label: Attestation
      options:
        - label: I vouch for this work and am willing to have my name attached to this review
```

### Create Initial Issues

After templates exist, create starter issues:

```bash
gh issue create --title "[READ] Playing on an Organic Team" \
  --body "Read https://www.whatscookin.us/playing-on-an-organic-team/ and summarize the 10 principles. Give an example of how you'd apply 'Seek Critique' in your first week." \
  --label "onboarding,reading"

gh issue create --title "[READ] How to Jump on a Moving Project" \
  --body "Read https://www.whatscookin.us/how-to-jump-on-a-moving-project/ and summarize the 9 tips. Which 3 are most relevant to your role? Why?" \
  --label "onboarding,reading"

gh issue create --title "[READ] ROLES.md - Understand Team Roles" \
  --body "Read ROLES.md in coop-projects. Which role(s) fit you? What skills do you want to develop?" \
  --label "onboarding,reading"

gh issue create --title "[DELIVER] Draft Intern Welcome Message" \
  --body "Write a welcome message for future interns. What do they need to know in the first hour? First day? First week?" \
  --label "onboarding,deliverable"

gh issue create --title "[DELIVER] Improve Onboarding Docs" \
  --body "After completing onboarding, identify one thing that was confusing or missing. Create a PR or doc to fix it." \
  --label "onboarding,deliverable"

gh issue create --title "[REVIEW] Peer Review a Teammate's Work" \
  --body "Once another intern completes a deliverable, review their work using the peer review template." \
  --label "onboarding,peer-review"
```

### Create GitHub Project Board

```bash
gh project create --title "Intern Onboarding" --owner Cooperation-org
```

Add columns: Backlog, In Progress, In Review, Done

---

## Attestation Flow

When intern completes onboarding:

1. All issues closed with peer reviews
2. Lead reviews overall completion
3. LinkedTrust attestation issued:
   - Subject: Intern
   - Claim: "Completed LinkedTrust Onboarding Program"
   - Evidence: Link to closed GitHub issues
   - Signed by: Lead + peer reviewers

4. Intern can request attestations on LinkedCreds for specific skills demonstrated
