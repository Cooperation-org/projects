# CLAUDE.md

This repo is the **team playbook** for What's Cookin' / LinkedTrust projects.

## Purpose

- Define HOW the team works (roles, skills, patterns)
- Provide templates for project documentation
- Store project-level goals, guidance, and context
- Replace Google Drive as the source of truth for project info
- Give AI assistants context when working on any project

## Structure

```
coop-projects/
├── ROLES.md              # Team roles and responsibilities
├── skills/               # Competencies and learning materials
│   ├── base/             # Core skills (communication, clarity)
│   ├── leading/
│   ├── engineering/
│   ├── marketing/
│   ├── relations/
│   ├── design/
│   └── learning/
├── templates/            # Copy these into projects
│   └── MAIN.md           # Project template
└── projects/             # Active project folders
    └── {project-name}/
        └── MAIN.md       # Project goals, links, guidance
```

## What belongs here

- Roles, skills, how-we-work documentation
- Project goals, stakeholders, key links, technical context
- Onboarding materials and learning paths
- Templates

## What does NOT belong here

- Day-to-day tasks (use Taiga or GitHub Issues)
- Status updates or standups
- Meeting notes
- Anything that changes frequently

## For AI assistants

When helping on a specific project, load:
1. This file (CLAUDE.md)
2. ROLES.md
3. Relevant skills/ docs
4. The project's MAIN.md in projects/{project-name}/
5. Any other files in the project folder (technical specs, design docs, etc.)
