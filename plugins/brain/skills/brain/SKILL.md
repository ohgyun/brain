---
name: brain
description: Start session - Load context by selecting Role and Project
user-invocable: true
---

# Brain Session Start

Select Role and Project to load your decision-making context into Claude.

This teaches Claude how YOU think in this specific context—not generic advice,
but decisions aligned with your values and this project's constraints.

## Execution Steps

1. If a session is already active:
   - Show current Role/Project
   - Ask "Would you like to select additional ones?"
   - Keep existing selection if "None" is chosen
2. Check lists from `~/.brain/roles/` and `~/.brain/projects/`
3. Ask user to select Role(s) (multiple selection allowed, can skip)
4. Ask user to select Project (can skip)
5. Read `values.md` from selected Role(s)
6. Read `rules.md` and `context.md` from selected Project
7. Summarize applied context

## Multiple Role Application

- When multiple Roles are selected, check "Application Domain" in values.md
- Each Role applies to decisions within its domain
