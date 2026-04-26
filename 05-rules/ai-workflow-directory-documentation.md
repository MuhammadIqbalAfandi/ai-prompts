# AI Workflow Directory Documentation

## Overview

The `/ai` directory is used to manage AI-assisted software development workflows.

This directory stores project context, issues, prompts, plans, reviews, tasks, and implementation logs.

The goal is to make AI work more consistently, traceably, and safely.

---

## Recommended Directory Structure

```txt
/ai
  /context
  /issues
  /prompts
  /plans
  /reviews
  /tasks
  /logs
```

Recommended order:

```txt
context → issue → prompt → plan → review → task → log
```

---

## Folder Descriptions

## `/context`

Contains global project information used by AI before planning or implementation.

This folder should include stable project rules and technical context.

Example files:

```txt
/ai/context/tech-stack.md
/ai/context/project-context.md
/ai/context/coding-standards.md
```

Use this folder for:

- Tech stack
- Project overview
- Coding standards
- API conventions
- Database conventions
- Naming conventions
- Architecture principles

Example:

```md
# Tech Stack

## Backend

- Bun
- Elysia
- PostgreSQL
- Zod
```

---

## `/issues`

Contains problem statements, feature requests, bugs, or improvement ideas.

An issue explains **what problem needs to be solved** before turning it into a prompt or plan.

Example file:

```txt
/ai/issues/001-digital-invitation.issue.md
```

Use this folder for:

- Feature requests
- Bug reports
- Product problems
- User pain points
- Improvement ideas
- Business requirements

Example:

```md
# Issue: Digital Invitation

## Problem

Users need a way to create and share digital invitations online.

## Goal

Allow users to create, edit, publish, and share event invitations.

## Notes

The feature should support RSVP and guest management.
```

---

## `/prompts`

Contains raw instructions or feature prompts written for AI.

A prompt is the input given to AI to generate plans, tasks, reviews, or implementation.

Example file:

```txt
/ai/prompts/001-digital-invitation.prompt.md
```

Use this folder for:

- Raw feature ideas
- AI instructions
- Feature goals
- User flow
- Initial requirements

Example:

```md
# Prompt: Digital Invitation

Create a digital invitation feature.

The user can:

- Create invitation
- Edit invitation
- Publish invitation
- Share invitation link
- Receive RSVP responses
```

---

## `/plans`

Contains technical planning documents generated from prompts and issues.

A plan explains **how the feature should be built**.

Example file:

```txt
/ai/plans/001-digital-invitation.plan.md
```

Use this folder for:

- Architecture plan
- Database design
- API design
- Validation strategy
- Implementation steps
- Risk analysis

Example sections:

```md
# Plan: Digital Invitation

## Overview

## Architecture

## Database Design

## API Design

## Validation

## Implementation Steps

## Risks
```

---

## `/reviews`

Contains review documents for plans, tasks, or implemented code.

A review is used to check quality before or after implementation.

Example file:

```txt
/ai/reviews/001-digital-invitation.review.md
```

Use this folder for:

- Plan review
- Architecture review
- Database review
- API review
- Security review
- Code review
- Risk review

Example sections:

```md
# Review: Digital Invitation

## Plan Review

## Architecture Review

## Database Review

## API Review

## Validation Review

## Risks

## Recommended Improvements
```

---

## `/tasks`

Contains granular developer-ready task breakdowns.

Tasks should be small, clear, and executable step by step.

Example file:

```txt
/ai/tasks/001-digital-invitation.tasks.md
```

Use this folder for:

- Implementation checklist
- Development steps
- Testing tasks
- Migration tasks
- API tasks
- Validation tasks

Example:

```md
# Tasks: Digital Invitation

## Database

- [ ] Create invitations table
- [ ] Add unique slug column
- [ ] Add status column

## API

- [ ] Create POST /invitations endpoint
- [ ] Create GET /invitations/:slug endpoint
- [ ] Create PATCH /invitations/:id endpoint

## Validation

- [ ] Create invitation Zod schema
- [ ] Validate slug format
- [ ] Validate event date
```

---

## `/logs`

Contains progress logs during implementation.

A log explains **what has been done**, **what changed**, and **what should happen next**.

Example file:

```txt
/ai/logs/001-digital-invitation.log.md
```

Use this folder for:

- Implementation progress
- Created files
- Changed files
- Technical decisions
- Issues found
- Next steps

Example:

```md
# Log: Digital Invitation

## Created

- Created invitations table migration
- Created invitation API routes
- Created Zod validation schema

## Changed

- Added invitation module
- Added database query helper

## Decisions

- Invitation slug must be unique
- Published invitations are public

## Issues

- Image upload is not implemented yet

## Next Step

- Implement RSVP endpoint
```

---

# Naming Convention

Every feature should use the same numeric ID across all related files.

Format:

```txt
[id]-[feature-name].[type].md
```

Example:

```txt
001-digital-invitation.issue.md
001-digital-invitation.prompt.md
001-digital-invitation.plan.md
001-digital-invitation.review.md
001-digital-invitation.tasks.md
001-digital-invitation.log.md
```

Recommended style:

```txt
lowercase
kebab-case
same feature ID
same feature name
```

Good:

```txt
001-digital-invitation.plan.md
```

Avoid:

```txt
001_DigitalInvitation_Plan.md
001 digital invitation plan.md
DigitalInvitation.md
```

---

# Recommended Workflow

## 1. Define Context

Create or update global context files:

```txt
/ai/context/tech-stack.md
/ai/context/project-context.md
/ai/context/coding-standards.md
```

---

## 2. Create Issue

Write the problem or feature request:

```txt
/ai/issues/001-digital-invitation.issue.md
```

---

## 3. Create Prompt

Turn the issue into an AI instruction:

```txt
/ai/prompts/001-digital-invitation.prompt.md
```

---

## 4. Generate Plan

Ask AI to generate:

```txt
/ai/plans/001-digital-invitation.plan.md
```

---

## 5. Review Plan

Ask AI to review the plan:

```txt
/ai/reviews/001-digital-invitation.review.md
```

---

## 6. Generate Tasks

Ask AI to create granular tasks:

```txt
/ai/tasks/001-digital-invitation.tasks.md
```

---

## 7. Implement

Ask AI to implement according to:

```txt
/ai/plans/001-digital-invitation.plan.md
/ai/tasks/001-digital-invitation.tasks.md
```

---

## 8. Update Log

After implementation, update:

```txt
/ai/logs/001-digital-invitation.log.md
```

---

# Practical Flow

```txt
issue
  ↓
prompt
  ↓
plan
  ↓
review
  ↓
tasks
  ↓
implementation
  ↓
log
```

---

# Simple Rule

Use each folder like this:

```txt
/context = project knowledge
/issues  = problem or request
/prompts = instruction for AI
/plans   = technical solution
/reviews = quality check
/tasks   = developer checklist
/logs    = progress history
```

---

# Notes

For small features, the `/reviews` folder can be optional.

Simple workflow:

```txt
issues → prompts → plans → tasks → logs
```

For larger or risky features, use the full workflow:

```txt
issues → prompts → plans → reviews → tasks → logs
```
