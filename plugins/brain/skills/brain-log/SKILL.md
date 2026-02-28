---
name: brain-log
description: Summarize and save meaningful parts of the current conversation as a log
user-invocable: true
---

# Brain Log Save

Summarize meaningful decisions and insights from the current conversation and save as a log.

## Execution Steps

1. Check current session's Project (ask if not set)
2. Check current session's Role(s) (record all if multiple)
3. Analyze conversation, extract meaningful decisions
4. Draft log based on `templates/log/session.md`
   - **Write in the same language as the current conversation**
   - This preserves natural context and authentic expression
5. AI Self-Review
   - If sufficient → auto-save
   - If insufficient → skip with notice

## AI Self-Review Criteria

Brain's philosophy: Principles emerge through decisions, not introspection.
Only log sessions where meaningful decisions revealed unconscious principles.

Evaluate with these questions:
- Does it capture **core insights** from the session?
- Did decisions reveal **unconscious principles** worth making explicit?
- Is there content **worth evolving** into values/rules?
- Can the next session **grasp the essence** from this log alone?
- Does it **reveal what truly matters**? (repeated patterns or singular discoveries)

Skip if: simple Q&A, routine tasks, no meaningful discoveries → omit log

## Log Location

`~/.brain/logs/{project}/YYYY-MM-DD_NNN.md` (NNN: sequence number for the date)

## Template

Use `templates/log/session.md`. Focus on "What We Discovered This Session" section:
- Repeated principles
- New insights
- Candidates for values/rules
