# AI Workflow Command Prompts

## Recommended Commands

Use these commands to keep the workflow consistent from planning, implementation, review, and future enhancements.

---

### 1. Create an Issue from a Raw Idea

Use this when the idea is still rough and has not been converted into a structured issue file.

```txt
Read this file first:

- /ai/context/project-rules.md

Your task:

Create a new issue file:

- /ai/issues/[id]-[feature-name].issue.md

Based on this raw idea:

[write the raw idea here]

Rules:

- Do not write code.
- Do not create a plan yet.
- Convert the raw idea into a clear and structured issue.
- Include background, goal, scope, out of scope, expected behavior, and notes.
- Use the required output format.
```

---

### 2. Create Planning Files from an Issue

Use this after the issue file already exists.

```txt
Read these files first:

- /ai/context/tech-stack.md
- /ai/context/project-rules.md
- /ai/issues/[id]-[feature-name].issue.md

Your task:

Create or update these files:

- /ai/prompts/[id]-[feature-name].prompt.md
- /ai/plans/[id]-[feature-name].plan.md
- /ai/tasks/[id]-[feature-name].tasks.md
- /ai/logs/[id]-[feature-name].log.md
- /ai/reviews/[id]-[feature-name].review.md

Rules:

- Do not write code yet.
- Focus only on preparing the feature workflow.
- Convert the issue into a refined prompt.
- Create a clear implementation plan.
- Break the plan into small actionable tasks.
- Initialize the log file.
- Initialize the review file.
- Follow the tech stack from /ai/context/tech-stack.md.
- Use the required output format.
```

---

### 3. Execute the Next Task

Use this when planning files already exist and you want AI to work on the next task.

```txt
Read these files first:

- /ai/context/tech-stack.md
- /ai/context/project-rules.md
- /ai/issues/[id]-[feature-name].issue.md
- /ai/prompts/[id]-[feature-name].prompt.md
- /ai/plans/[id]-[feature-name].plan.md
- /ai/tasks/[id]-[feature-name].tasks.md
- /ai/logs/[id]-[feature-name].log.md

Your task:

Implement the code required to complete only the next unchecked task in:

- /ai/tasks/[id]-[feature-name].tasks.md

This is the only step where code changes are allowed.

Rules:

- Follow the instruction from /ai/prompts/[id]-[feature-name].prompt.md.
- Do not work on other tasks.
- Do not refactor unrelated code.
- Do not introduce new dependencies unless already approved in the plan.
- Follow the existing project structure.
- Follow the tech stack from /ai/context/tech-stack.md.
- After finishing, update the completed task checkbox.
- Update /ai/logs/[id]-[feature-name].log.md.
- Explain all changed files.
- Stop after this task is done.
```

---

### 4. Execute a Specific Task

Use this when you do not want AI to pick the next unchecked task automatically.

```txt
Read these files first:

- /ai/context/tech-stack.md
- /ai/context/project-rules.md
- /ai/issues/[id]-[feature-name].issue.md
- /ai/prompts/[id]-[feature-name].prompt.md
- /ai/plans/[id]-[feature-name].plan.md
- /ai/tasks/[id]-[feature-name].tasks.md
- /ai/logs/[id]-[feature-name].log.md

Your task:

Implement the code required to complete only the next unchecked task in:

[write the selected task here]

This is the only step where code changes are allowed.

Rules:

- Follow the instruction from /ai/prompts/[id]-[feature-name].prompt.md.
- Do not work on other tasks.
- Do not change unrelated files.
- Do not refactor unrelated code.
- Do not introduce new dependencies unless already approved in the plan.
- After finishing, update the related task checkbox.
- Update /ai/logs/[id]-[feature-name].log.md.
- Explain all changed files.
- Stop after this task is done.
```

---

### 5. Fix an Error from the Current Task

Use this when the task implementation has an error or failed test.

```txt
Read these files first:

- /ai/context/tech-stack.md
- /ai/context/project-rules.md
- /ai/issues/[id]-[feature-name].issue.md
- /ai/prompts/[id]-[feature-name].prompt.md
- /ai/plans/[id]-[feature-name].plan.md
- /ai/tasks/[id]-[feature-name].tasks.md
- /ai/logs/[id]-[feature-name].log.md

Your task:

Implement the code required to complete only the next unchecked task in:

[paste the error message here]

This is the only step where code changes are allowed.

Rules:

- Follow the instruction from /ai/prompts/[id]-[feature-name].prompt.md.
- Do not work on new tasks.
- Do not refactor unrelated code.
- Do not change unrelated files.
- Explain the root cause.
- Explain changed files.
- Update /ai/logs/[id]-[feature-name].log.md.
```

---

### 6. Review a Completed Feature

Use this after all tasks for a feature are completed.

```txt
Read these files first:

- /ai/context/tech-stack.md
- /ai/context/project-rules.md
- /ai/issues/[id]-[feature-name].issue.md
- /ai/prompts/[id]-[feature-name].prompt.md
- /ai/plans/[id]-[feature-name].plan.md
- /ai/tasks/[id]-[feature-name].tasks.md
- /ai/logs/[id]-[feature-name].log.md

Your task:

Review the completed feature and write the result to:

- /ai/reviews/[id]-[feature-name].review.md

Check:

- Bugs
- Security issues
- Validation issues
- Edge cases
- Duplicate code
- Naming consistency
- Missing tests
- Maintainability problems
- Future improvements

Rules:

- Do not change code.
- Keep findings specific and actionable.
- Mention the related file or area when possible.
- Separate critical issues, improvements, and optional suggestions.
- Use the required output format.
```

---

### 7. Create an Enhancement from an Existing Feature

Use this when you want to add a future improvement to an existing completed feature.

```txt
Read these files first:

- /ai/context/tech-stack.md
- /ai/context/project-rules.md
- /ai/issues/[old-id]-[old-feature-name].issue.md
- /ai/prompts/[old-id]-[old-feature-name].prompt.md
- /ai/plans/[old-id]-[old-feature-name].plan.md
- /ai/tasks/[old-id]-[old-feature-name].tasks.md
- /ai/logs/[old-id]-[old-feature-name].log.md
- /ai/reviews/[old-id]-[old-feature-name].review.md

Enhancement request:

[write the enhancement idea here]

Your task:

Create a new feature workflow for this enhancement:

- /ai/issues/[new-id]-[enhancement-name].issue.md
- /ai/prompts/[new-id]-[enhancement-name].prompt.md
- /ai/plans/[new-id]-[enhancement-name].plan.md
- /ai/tasks/[new-id]-[enhancement-name].tasks.md
- /ai/logs/[new-id]-[enhancement-name].log.md
- /ai/reviews/[new-id]-[enhancement-name].review.md

Rules:

- Use a new feature ID for major enhancements.
- Do not modify code yet.
- Keep the enhancement scope clear.
- Mention how this enhancement relates to the old feature.
- Follow the tech stack from /ai/context/tech-stack.md.
- Use the required output format.
```
