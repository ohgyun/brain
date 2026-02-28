---
name: brain-new-project
description: Create a new Project
user-invocable: true
---

# Brain New Project Creation

Create a new Project.

**Philosophy**: Start with minimal context. Your project's rules and priorities
will become clearer as you work, and can be refined over time.

## Execution Steps

1. Ask for new Project name
2. Ask for project overview (can leave empty)
3. Ask for key rules (can leave empty)
4. Create new Project folder:
   - `~/.brain/projects/{project_name}/rules.md`
   - `~/.brain/projects/{project_name}/context.md`
5. Confirm created files

## File Creation Rules

- Create minimal structure only (title only)
- **Write in the same language as the current conversation**
- Remove placeholders and guide text
- Reflect only user input
- Exclude sections if user chooses to leave empty
- Can expand later referring to `templates/project/`

## Using Arguments

Name can be specified directly: `/brain-new-project {project_name}`
