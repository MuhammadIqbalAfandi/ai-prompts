# AI Workflow Command Prompts

This file contains reusable prompts to run the AI workflow.

Use these commands after creating or updating:

```txt
/ai/workflow-rules.md
/ai/context/tech-stack.md
```

Recommended workflow:

```txt
issue → prompt → plan → review → tasks → implementation → log
```

---

# 1. Generate Workflow Files From Feature Prompt

Use this when you already have a feature prompt file and want AI to generate the related plan, tasks, and log.

```md
Read these files:

- /ai/workflow-rules.md
- /ai/context/tech-stack.md
- /ai/prompts/[id]-[feature-name].prompt.md

Task:

Generate all required workflow files for this feature.

Required output files:

- /ai/plans/[id]-[feature-name].plan.md
- /ai/tasks/[id]-[feature-name].tasks.md
- /ai/logs/[id]-[feature-name].log.md

Rules:

- Follow `/ai/workflow-rules.md` strictly
- Follow the tech stack from `/ai/context/tech-stack.md`
- Use the same feature ID and feature name from the prompt file
- Do not implement code yet
- Do not modify unrelated files
- Output only using this format:

=== FILE: /ai/[folder]/[filename] ===
<content>
```

Example:

```md
Read these files:

- /ai/workflow-rules.md
- /ai/context/tech-stack.md
- /ai/prompts/001-digital-invitation.prompt.md

Task:

Generate all required workflow files for this feature.

Required output files:

- /ai/plans/001-digital-invitation.plan.md
- /ai/tasks/001-digital-invitation.tasks.md
- /ai/logs/001-digital-invitation.log.md

Rules:

- Follow `/ai/workflow-rules.md` strictly
- Follow the tech stack from `/ai/context/tech-stack.md`
- Use the same feature ID and feature name from the prompt file
- Do not implement code yet
- Do not modify unrelated files
- Output only using this format:

=== FILE: /ai/[folder]/[filename] ===
<content>
```

---

# 2. Generate Issue From Raw Idea

Use this when you only have a rough idea and want AI to turn it into a structured issue.

```md
Read these files:

- /ai/workflow-rules.md
- /ai/context/tech-stack.md

Raw idea:

[write your rough idea here]

Task:

Create an issue file for this feature.

Feature ID: [id]
Feature Name: [feature-name]

Required output file:

- /ai/issues/[id]-[feature-name].issue.md

The issue must include:

- Problem
- Goal
- User needs
- Main requirements
- Out of scope
- Notes

Rules:

- Keep the issue clear and concise
- Do not create plan, tasks, or code yet
- Output only using this format:

=== FILE: /ai/issues/[id]-[feature-name].issue.md ===
<content>
```

Example:

```md
Read these files:

- /ai/workflow-rules.md
- /ai/context/tech-stack.md

Raw idea:

I want to build a digital invitation feature.
Users can create invitations, publish them, share links, and collect RSVP responses.

Task:

Create an issue file for this feature.

Feature ID: 001
Feature Name: digital-invitation

Required output file:

- /ai/issues/001-digital-invitation.issue.md

The issue must include:

- Problem
- Goal
- User needs
- Main requirements
- Out of scope
- Notes

Rules:

- Keep the issue clear and concise
- Do not create plan, tasks, or code yet
- Output only using this format:

=== FILE: /ai/issues/001-digital-invitation.issue.md ===
<content>
```

---

# 3. Generate Prompt From Issue

Use this after creating an issue and before generating a plan.

```md
Read these files:

- /ai/workflow-rules.md
- /ai/context/tech-stack.md
- /ai/issues/[id]-[feature-name].issue.md

Task:

Create a feature prompt from the issue.

Required output file:

- /ai/prompts/[id]-[feature-name].prompt.md

The prompt must include:

- Feature overview
- Goal
- User flow
- Requirements
- Data needed
- API needed
- Validation rules
- Expected AI output

Rules:

- Keep the prompt structured and actionable
- Do not create plan, tasks, or code yet
- Output only using this format:

=== FILE: /ai/prompts/[id]-[feature-name].prompt.md ===
<content>
```

Example:

```md
Read these files:

- /ai/workflow-rules.md
- /ai/context/tech-stack.md
- /ai/issues/001-digital-invitation.issue.md

Task:

Create a feature prompt from the issue.

Required output file:

- /ai/prompts/001-digital-invitation.prompt.md

The prompt must include:

- Feature overview
- Goal
- User flow
- Requirements
- Data needed
- API needed
- Validation rules
- Expected AI output

Rules:

- Keep the prompt structured and actionable
- Do not create plan, tasks, or code yet
- Output only using this format:

=== FILE: /ai/prompts/001-digital-invitation.prompt.md ===
<content>
```

---

# 4. Review Plan And Tasks

Use this before implementation to check whether the plan and tasks are safe and complete.

```md
Read these files:

- /ai/workflow-rules.md
- /ai/context/tech-stack.md
- /ai/prompts/[id]-[feature-name].prompt.md
- /ai/plans/[id]-[feature-name].plan.md
- /ai/tasks/[id]-[feature-name].tasks.md

Task:

Review the plan and tasks before implementation.

Required output file:

- /ai/reviews/[id]-[feature-name].review.md

Review must include:

- Plan review
- Architecture review
- Database review
- API review
- Validation review
- Task order review
- Risks
- Recommended improvements

Rules:

- Do not implement code yet
- Do not modify the plan or tasks directly
- If changes are needed, list them as recommendations
- Output only using this format:

=== FILE: /ai/reviews/[id]-[feature-name].review.md ===
<content>
```

Example:

```md
Read these files:

- /ai/workflow-rules.md
- /ai/context/tech-stack.md
- /ai/prompts/001-digital-invitation.prompt.md
- /ai/plans/001-digital-invitation.plan.md
- /ai/tasks/001-digital-invitation.tasks.md

Task:

Review the plan and tasks before implementation.

Required output file:

- /ai/reviews/001-digital-invitation.review.md

Review must include:

- Plan review
- Architecture review
- Database review
- API review
- Validation review
- Task order review
- Risks
- Recommended improvements

Rules:

- Do not implement code yet
- Do not modify the plan or tasks directly
- If changes are needed, list them as recommendations
- Output only using this format:

=== FILE: /ai/reviews/001-digital-invitation.review.md ===
<content>
```

---

# 5. Update Plan And Tasks From Review

Use this after reviewing the plan and tasks.

```md
Read these files:

- /ai/workflow-rules.md
- /ai/context/tech-stack.md
- /ai/plans/[id]-[feature-name].plan.md
- /ai/tasks/[id]-[feature-name].tasks.md
- /ai/reviews/[id]-[feature-name].review.md

Task:

Update the plan and tasks based on the review recommendations.

Required output files:

- /ai/plans/[id]-[feature-name].plan.md
- /ai/tasks/[id]-[feature-name].tasks.md
- /ai/logs/[id]-[feature-name].log.md

Rules:

- Keep the same feature ID and feature name
- Apply only relevant review recommendations
- Keep the plan concise and actionable
- Keep tasks granular and developer-ready
- Update the log with what changed and the next step
- Do not implement code yet
- Output only using this format:

=== FILE: /ai/[folder]/[filename] ===
<content>
```

Example:

```md
Read these files:

- /ai/workflow-rules.md
- /ai/context/tech-stack.md
- /ai/plans/001-digital-invitation.plan.md
- /ai/tasks/001-digital-invitation.tasks.md
- /ai/reviews/001-digital-invitation.review.md

Task:

Update the plan and tasks based on the review recommendations.

Required output files:

- /ai/plans/001-digital-invitation.plan.md
- /ai/tasks/001-digital-invitation.tasks.md
- /ai/logs/001-digital-invitation.log.md

Rules:

- Keep the same feature ID and feature name
- Apply only relevant review recommendations
- Keep the plan concise and actionable
- Keep tasks granular and developer-ready
- Update the log with what changed and the next step
- Do not implement code yet
- Output only using this format:

=== FILE: /ai/[folder]/[filename] ===
<content>
```

---

# 6. Implement Feature From Plan And Tasks

Use this when the plan and tasks are ready.

```md
Read these files:

- /ai/workflow-rules.md
- /ai/context/tech-stack.md
- /ai/prompts/[id]-[feature-name].prompt.md
- /ai/plans/[id]-[feature-name].plan.md
- /ai/tasks/[id]-[feature-name].tasks.md
- /ai/logs/[id]-[feature-name].log.md

Task:

Implement this feature according to the plan and tasks.

Rules:

- Follow the task order
- Start from the first incomplete task
- Keep changes small and focused
- Do not modify unrelated files
- Use the tech stack from `/ai/context/tech-stack.md`
- After implementation, update:
  - `/ai/tasks/[id]-[feature-name].tasks.md`
  - `/ai/logs/[id]-[feature-name].log.md`
- Before coding, briefly state which task will be implemented first
```

Example:

```md
Read these files:

- /ai/workflow-rules.md
- /ai/context/tech-stack.md
- /ai/prompts/001-digital-invitation.prompt.md
- /ai/plans/001-digital-invitation.plan.md
- /ai/tasks/001-digital-invitation.tasks.md
- /ai/logs/001-digital-invitation.log.md

Task:

Implement this feature according to the plan and tasks.

Rules:

- Follow the task order
- Start from the first incomplete task
- Keep changes small and focused
- Do not modify unrelated files
- Use the tech stack from `/ai/context/tech-stack.md`
- After implementation, update:
  - `/ai/tasks/001-digital-invitation.tasks.md`
  - `/ai/logs/001-digital-invitation.log.md`
- Before coding, briefly state which task will be implemented first
```

---

# 7. Continue Implementation From Log

Use this when the feature was partially implemented and you want AI to continue.

```md
Read these files:

- /ai/workflow-rules.md
- /ai/context/tech-stack.md
- /ai/plans/[id]-[feature-name].plan.md
- /ai/tasks/[id]-[feature-name].tasks.md
- /ai/logs/[id]-[feature-name].log.md

Task:

Continue implementation from the latest unfinished task.

Rules:

- Do not repeat completed tasks
- Start from the next logical incomplete task
- Keep changes small and focused
- Do not modify unrelated files
- Update the task checklist after completing work
- Update the log with:
  - What was implemented
  - What files changed
  - Any issue found
  - Next step
```

Example:

```md
Read these files:

- /ai/workflow-rules.md
- /ai/context/tech-stack.md
- /ai/plans/001-digital-invitation.plan.md
- /ai/tasks/001-digital-invitation.tasks.md
- /ai/logs/001-digital-invitation.log.md

Task:

Continue implementation from the latest unfinished task.

Rules:

- Do not repeat completed tasks
- Start from the next logical incomplete task
- Keep changes small and focused
- Do not modify unrelated files
- Update the task checklist after completing work
- Update the log with:
  - What was implemented
  - What files changed
  - Any issue found
  - Next step
```

---

# 8. Update Log After Manual Work

Use this if you implemented something manually and want AI to update the log.

```md
Read these files:

- /ai/workflow-rules.md
- /ai/tasks/[id]-[feature-name].tasks.md
- /ai/logs/[id]-[feature-name].log.md

Manual work completed:

[write what you changed manually]

Task:

Update the task checklist and log based on the manual work.

Rules:

- Mark completed tasks only if they are actually done
- Add created or changed files
- Add decisions if any
- Add issues if any
- Add the next step
- Do not implement code
- Output only using this format:

=== FILE: /ai/tasks/[id]-[feature-name].tasks.md ===
<content>

=== FILE: /ai/logs/[id]-[feature-name].log.md ===
<content>
```

Example:

```md
Read these files:

- /ai/workflow-rules.md
- /ai/tasks/001-digital-invitation.tasks.md
- /ai/logs/001-digital-invitation.log.md

Manual work completed:

I created the invitations table migration and added the slug unique index.

Task:

Update the task checklist and log based on the manual work.

Rules:

- Mark completed tasks only if they are actually done
- Add created or changed files
- Add decisions if any
- Add issues if any
- Add the next step
- Do not implement code
- Output only using this format:

=== FILE: /ai/tasks/001-digital-invitation.tasks.md ===
<content>

=== FILE: /ai/logs/001-digital-invitation.log.md ===
<content>
```

---

# 9. Review Implemented Feature

Use this after implementation to check quality.

```md
Read these files:

- /ai/workflow-rules.md
- /ai/context/tech-stack.md
- /ai/prompts/[id]-[feature-name].prompt.md
- /ai/plans/[id]-[feature-name].plan.md
- /ai/tasks/[id]-[feature-name].tasks.md
- /ai/logs/[id]-[feature-name].log.md

Task:

Review the implemented feature.

Check:

- Whether implementation matches the plan
- Whether all completed tasks are actually done
- API consistency
- Validation correctness
- Database risks
- Security risks
- Missing tests
- Refactoring opportunities

Required output file:

- /ai/reviews/[id]-[feature-name].review.md

Rules:

- Do not implement code
- Provide actionable findings
- Output only using this format:

=== FILE: /ai/reviews/[id]-[feature-name].review.md ===
<content>
```

Example:

```md
Read these files:

- /ai/workflow-rules.md
- /ai/context/tech-stack.md
- /ai/prompts/001-digital-invitation.prompt.md
- /ai/plans/001-digital-invitation.plan.md
- /ai/tasks/001-digital-invitation.tasks.md
- /ai/logs/001-digital-invitation.log.md

Task:

Review the implemented feature.

Check:

- Whether implementation matches the plan
- Whether all completed tasks are actually done
- API consistency
- Validation correctness
- Database risks
- Security risks
- Missing tests
- Refactoring opportunities

Required output file:

- /ai/reviews/001-digital-invitation.review.md

Rules:

- Do not implement code
- Provide actionable findings
- Output only using this format:

=== FILE: /ai/reviews/001-digital-invitation.review.md ===
<content>
```

---

# 10. Simple Short Commands

## Generate workflow files

```md
Generate workflow files for feature [id]-[feature-name].

Read:

- /ai/workflow-rules.md
- /ai/context/tech-stack.md
- /ai/prompts/[id]-[feature-name].prompt.md

Generate:

- plan
- tasks
- log

Do not implement code yet.
```

## Implement next task

```md
Implement the next incomplete task for feature [id]-[feature-name].

Read:

- /ai/workflow-rules.md
- /ai/context/tech-stack.md
- /ai/plans/[id]-[feature-name].plan.md
- /ai/tasks/[id]-[feature-name].tasks.md
- /ai/logs/[id]-[feature-name].log.md

Update tasks and log after implementation.
```

## Continue from log

```md
Continue feature [id]-[feature-name] from the latest log.

Read:

- /ai/workflow-rules.md
- /ai/context/tech-stack.md
- /ai/tasks/[id]-[feature-name].tasks.md
- /ai/logs/[id]-[feature-name].log.md

Do the next logical task.
Update tasks and log.
```

---

# Recommended First Prompt For New Feature

Use this as your default prompt when starting a new feature.

```md
Read these files:

- /ai/workflow-rules.md
- /ai/context/tech-stack.md

Feature ID: [id]
Feature Name: [feature-name]

Raw idea:

[write your raw idea here]

Task:

Create the full AI workflow files for this feature.

Required output files:

- /ai/issues/[id]-[feature-name].issue.md
- /ai/prompts/[id]-[feature-name].prompt.md
- /ai/plans/[id]-[feature-name].plan.md
- /ai/tasks/[id]-[feature-name].tasks.md
- /ai/logs/[id]-[feature-name].log.md

Rules:

- Follow `/ai/workflow-rules.md` strictly
- Follow `/ai/context/tech-stack.md`
- Use clean and structured Markdown
- Keep explanations concise and actionable
- Do not implement code yet
- Output only using this format:

=== FILE: /ai/[folder]/[filename] ===
<content>
```

Example:

```md
Read these files:

- /ai/workflow-rules.md
- /ai/context/tech-stack.md

Feature ID: 001
Feature Name: digital-invitation

Raw idea:

I want to build a digital invitation feature.
Users can create invitations, edit event details, publish the invitation, share a public link, and collect RSVP responses from guests.

Task:

Create the full AI workflow files for this feature.

Required output files:

- /ai/issues/001-digital-invitation.issue.md
- /ai/prompts/001-digital-invitation.prompt.md
- /ai/plans/001-digital-invitation.plan.md
- /ai/tasks/001-digital-invitation.tasks.md
- /ai/logs/001-digital-invitation.log.md

Rules:

- Follow `/ai/workflow-rules.md` strictly
- Follow `/ai/context/tech-stack.md`
- Use clean and structured Markdown
- Keep explanations concise and actionable
- Do not implement code yet
- Output only using this format:

=== FILE: /ai/[folder]/[filename] ===
<content>
```
