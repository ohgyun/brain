---
name: brain-reflect
description: End session - Save log and discover patterns for evolution
user-invocable: true
---

# Brain Session Reflection

Reflect on the current conversation to capture decisions and discover patterns.

**Philosophy**: Principles emerge through decisions, not introspection.
This command helps you discover unconscious principles revealed in conversations,
then evolve your values and rules over time.

## Execution Steps

### 1. Check Session Context

- Check current session's Project (ask if not set)
- Check current session's Role(s) (record all if multiple)
- If no context: Ask user to run `/brain` first

### 2. Analyze Conversation

Analyze the current conversation for meaningful decisions:
- What decisions were made?
- What trade-offs were considered?
- What values were revealed in choices?
- Were there repeated patterns?

### 3. AI Self-Review

Brain's philosophy: Principles emerge through decisions, not introspection.
Only log sessions where meaningful decisions revealed unconscious principles.

Evaluate with these questions:
- Does it capture **core insights** from the session?
- Did decisions reveal **unconscious principles** worth making explicit?
- Is there content **worth evolving** into values/rules?
- Can the next session **grasp the essence** from this log alone?
- Does it **reveal what truly matters**? (repeated patterns or singular discoveries)

**If insufficient** (simple Q&A, routine tasks, no meaningful discoveries):
- Notify user: "No meaningful decisions to capture. Skipping log."
- Exit

**If sufficient**:
- Proceed to log creation

### 4. Create and Save Log

Draft log based on `templates/log/session.md`:
- **Write in the same language as the current conversation**
- This preserves natural context and authentic expression
- Focus on "What We Discovered This Session" section:
  - Repeated principles
  - New insights
  - Candidates for values/rules

Save to: `~/.brain/logs/{project}/YYYY-MM-DD_NNN.md` (NNN: sequence number for the date)

Confirm: "Session log saved to {filename}"

### 5. Analyze Patterns

Read logs from `~/.brain/logs/{project}/`:

**Scope: Last 15 logs** (or all if fewer)
- Provides consistent, recent context window
- Captures current decision-making patterns (not historical)
- Your decision-making evolves over time—focus on who you are now

**Extract patterns:**
- From "What We Discovered This Session" section
- Look for principles repeated 2+ times
- Prioritize recent, consistent patterns

**Filter duplicates:**
- Compare candidates with existing rules.md and values.md
- Obvious duplicates: auto-filtered
- Similar items: presented for user decision
- Only suggest genuinely new or evolved patterns

**If no new patterns found:**
- Exit silently

**If patterns found:**
- Proceed to step 6

### 6. Offer Pattern Update (Conditional)

Present findings to user:
- "I've found repeated patterns in your recent decisions:"
- List patterns with:
  - Repetition count
  - Source logs
  - Example decisions
- Ask: "Would you like to update your values/rules with these patterns?"

**If user declines:**
- Exit (will offer again next time)

**If user accepts:**
- Proceed to step 7

### 7. Prepare Update Suggestions

For each pattern candidate:

**Detect similar items:**
- Read existing rules.md and values.md
- Compare new candidates with existing items
- If similar items found, offer merge options:
  - Keep both items
  - Add/extend to existing item
  - Ignore new candidate
  - Modify existing item

**Conservative merge principle:**
- "Ship fast" vs "Ship working code fast" may seem similar but could be different
- Only you can judge if two principles are truly the same
- Obvious duplicates auto-detected, similarities require user decision

### 8. User Selection and Approval

Present all candidates with merge suggestions.

User selects which patterns to elevate:
- Check each candidate
- Make merge decisions
- Approve final additions

**Important**: This isn't just a safety check—it's a metacognitive process.
- When you approve a pattern, you're consciously recognizing your own thinking
- You transform an unconscious habit into a deliberate principle
- This moment strengthens self-awareness

### 9. Update Files

For approved patterns:
- Update rules.md and/or values.md
- **Preserve the language from source logs**
- Do not add comments/metadata
- Keep minimal structure

Confirm: "Updated {role/project} with {N} new principles"

## Important Principles

- **Log first, analyze always**: Save meaningful logs, then check for patterns every time
- **Recent context matters**: Analyzes last 15 logs—your decision-making evolves, focus on who you are now
- **User confirmation required**: Never auto-modify files
  - This isn't just safety—it's a metacognitive process
  - When you approve a pattern, you're consciously recognizing your own thinking
  - You transform an unconscious habit into a deliberate principle
- **Conservative merge**: Detect only obvious duplicates; user decides on similarities
- **Prioritize repetition**: Present patterns repeated 2+ times first
  - Repeated patterns are more likely to be genuine principles

## Usage Notes

**Typical workflow:**
```
/brain          - Start session
[work on tasks]
/brain-reflect  - End session
  → Log saved
  → Patterns analyzed (last 15 logs)
  → If found: "Would you like to update?"
  → If not: silently exits
```

**You don't need to reflect every conversation:**
- Only meaningful sessions with decisions
- AI will auto-skip if nothing to capture
- No pressure to log everything

**Pattern discovery is continuous:**
- Analyzes patterns every reflection
- Offers updates only when new patterns found
- Gradually evolves your values/rules
- Recent patterns reflect current you
