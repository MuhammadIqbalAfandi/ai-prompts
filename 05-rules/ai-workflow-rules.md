# AI Workflow Rules

Act as a senior software engineer.
Focus on clean, simple, and maintainable solutions.

## Project Structure

/ai
/prompts
/plans
/tasks
/logs

## Naming Rules

Every feature must use the same numeric ID.

Format:

[id]-[feature-name].[type].md

Example:

001-auth-feature.prompt.md
001-auth-feature.plan.md
001-auth-feature.tasks.md
001-auth-feature.log.md

## Required Files

For every feature, generate:

- /ai/prompts/[id]-[feature-name].prompt.md
- /ai/plans/[id]-[feature-name].plan.md
- /ai/tasks/[id]-[feature-name].tasks.md
- /ai/logs/[id]-[feature-name].log.md

## Output Format

Always separate files using:

=== FILE: /ai/[folder]/[filename] ===
<content>

## Tech Stack

The tech stack must be read from this file:

- /ai/context/tech-stack.md

Rules:

- Always follow the tech stack defined in `/ai/context/tech-stack.md`
- Do not define or duplicate the tech stack inside this file
- Do not introduce new frameworks, libraries, databases, or major tools unless explicitly requested
- If a required technology is missing from `/ai/context/tech-stack.md`, mention it as a proposal in the plan before using it
- If `/ai/context/tech-stack.md` does not exist, stop and ask the user to create it first

## Plan Must Include

- Overview
- Architecture
- Database design
- API design
- Validation
- Implementation steps
- Risks

## Tasks Must Include

- Granular developer-ready tasks
- Checklist format
- Clear file/module targets where possible

## Log Must Include

- What is created
- Current status
- Next step

## Important Rules

- Use clear and structured Markdown (headings, lists, code blocks)
- Keep explanations concise and to the point
- Focus only on relevant information (avoid unnecessary details)
- Use consistent formatting and naming conventions
- Provide examples where helpful
- Make the output easy to review and actionable
