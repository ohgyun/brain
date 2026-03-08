---
name: brain
description: Start Brain session - Load Role and Project context
user-invocable: true
---

# Brain Session Start

Load your decision-making context into Claude by selecting Role and Project.

This teaches Claude how YOU think in this specific context—not generic advice,
but decisions aligned with your values and this project's constraints.

## Execution Steps

### 1. Check Session State

If a session is already active:
- Show current Role(s) and Project
- Ask "Would you like to add or change your selection?"
- Options: Add Role, Change Role, Change Project, Keep current
- If "Keep current", exit

### 2. Check Brain Data Existence

Use the `Glob` tool to check if `~/.brain/` exists:
- Pattern: `~/.brain/**`
- If no matches: Run `mkdir -p ~/.brain` and proceed to initial setup
- If matches found: check for roles and projects

### 3. Handle Missing Data

**If no Roles exist:**
- "No Roles found. Let's create your first Role."
- Ask for Role name
- Ask for application domain (e.g., "code, architecture, technical decisions")
- Ask for core values (can leave empty)
- Create `~/.brain/roles/{role_name}/values.md`
  - Minimal structure: title + application domain
  - Write in conversation language
  - Remove placeholders and guide text
  - Reflect only user input

**If no Projects exist:**
- "No Projects found. Let's create your first Project."
- Ask for Project name
- Ask for project overview (can leave empty)
- Ask for key rules (can leave empty)
- Create `~/.brain/projects/{project_name}/rules.md`
  - Minimal structure: title only
  - Write in conversation language
  - Can include Context section if needed

**Philosophy**: You don't need to know all your values upfront. Start minimal—
your principles will emerge through conversations and can be discovered later.

### 4. Select Role and Project

**Role Selection:**
- List available Roles from `~/.brain/roles/`
- Allow multiple selection
- Allow "Create new Role" option
- Can skip (no Role)

**Project Selection:**
- List available Projects from `~/.brain/projects/`
- Single selection
- Allow "Create new Project" option
- Can skip (no Project)

**If "Create new" selected:**
- Follow same creation flow as step 3

### 5. Load Context

- Read `values.md` from selected Role(s)
- Read `rules.md` from selected Project
- Apply context to current session

### 6. Summarize and Confirm

Display loaded context:
- Active Role(s) (with application domains if multiple)
- Active Project
- Brief summary of key values and rules

"Brain session started. I'll make decisions aligned with your values and this project's constraints."

## Multiple Role Application

When multiple Roles are selected:
- Check "Application Domain" in each values.md
- Each Role applies to decisions within its domain
- Example: Developer (code) + Founder (product decisions)

## Name Normalization

Role and Project names are used as directory names and identifiers, so they must be normalized:
- English letters and numbers only (no non-ASCII characters)
- Lowercase only
- Spaces, underscores, and other separators → `-`
- Remove any remaining characters that are not letters, numbers, or `-`
- Examples: `My Project` → `my-project`, `Dev_Role` → `dev-role`, `개발자` → ask user for an English name

If the user provides a non-English name, ask them to provide an English equivalent.

Apply the normalized name to both:
- Directory name: `~/.brain/roles/{normalized-name}/`
- File title: `# {normalized-name}` inside `values.md` or `rules.md`

This ensures consistent lookup without needing to read file contents to resolve the display name.

All other content (values, rules, descriptions) should be written in the language of the current conversation.

## File Creation Rules

When creating Role or Project files:
- Create minimal structure only
- **Write in the same language as the current conversation**
- Remove placeholders and guide text
- Reflect only user input
- Exclude sections if user chooses to leave empty
- Can expand later referring to templates

## Using Arguments

Direct creation:
- `/brain {role_name}` - Create or select specific Role
- Useful for quick setup
