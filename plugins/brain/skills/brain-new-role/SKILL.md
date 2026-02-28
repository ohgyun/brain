---
name: brain-new-role
description: Create a new Role
user-invocable: true
---

# Brain New Role Creation

Create a new Role.

## Execution Steps

1. Ask for new Role name
2. Ask for application domain (e.g., "code, architecture, technical decisions")
3. Ask for core values (can leave empty)
4. Create `~/.brain/roles/{role_name}/values.md`
5. Confirm created file

## File Creation Rules

- Create minimal structure only (title + application domain)
- **Write in the same language as the current conversation**
- Remove placeholders and guide text
- Reflect only user input
- Exclude sections if user chooses to leave empty
- Can expand later referring to `templates/role/values.md`

## Using Arguments

Name can be specified directly: `/brain-new-role {role_name}`
