# Brain - Role-based Decision Making System

Teach Claude how YOU make decisions—not just what you prefer, but your entire decision-making framework.

## What is Brain?

Brain helps Claude learn and replicate **your decision-making style** by:
- Capturing patterns from your conversations
- Discovering unconscious principles you didn't know you had
- Teaching Claude to think like you do in different roles and contexts

Your decision-making principles often exist in your actions, not your thoughts. Brain helps you discover them through practice, not introspection.

## Why Brain?

**The Problem:**
- Every Claude session starts from zero
- You re-explain preferences each time
- Your principles are mostly unconscious—hard to articulate upfront
- You make decisions differently as Developer vs. Founder, on personal vs. client projects

**Brain's Approach:**
- Principles emerge naturally in conversations
- Capture decisions as they happen
- Discover patterns over time
- Evolve your values and rules continuously
- Recognize you're multiple roles with different values

## Quick Start

### 1. Install Plugin

```bash
# Add marketplace
claude plugin marketplace add ohgyun/brain

# Install plugin
claude plugin install brain
```

### 2. Start Your First Session

```bash
# Launch Claude Code
claude

# Start Brain session
/brain
```

On first run, Brain guides you to create your first Role and Project. Start minimal—your principles will emerge through conversations.

All data is stored as markdown files in `~/.brain/`.

## Commands

Brain has just 2 commands:

| Command | When | What it does |
|---------|------|--------------|
| `/brain` | Session start | Load Role/Project context (creates them if needed) |
| `/brain-reflect` | Session end | Save log, discover patterns, offer updates |

**That's it.** Simple workflow: start → work → reflect.

## How It Works

### The Discovery Process

```
1. Start session (/brain)
   → Select Role and Project
   → Claude loads your decision-making context

2. Have conversations
   → Make decisions naturally
   → Your principles reveal themselves in choices

3. End session (/brain-reflect)
   → Meaningful decisions saved as log
   → Patterns analyzed (last 15 logs)
   → New patterns? "Would you like to update your values?"

4. Approve patterns
   → Unconscious habit → Conscious principle
   → Metacognitive moment: "Yes, that's who I am"

5. Claude evolves with you
   → Next session applies your principles
   → Decisions aligned with YOUR thinking
```

### From Tacit to Explicit

Brain follows a natural learning process:

**Tacit knowledge** (unconscious principles)
↓
**Socialization** (emerge through dialogue)
↓
**Externalization** (captured in logs)
↓
**Combination** (patterns → rules/values)
↓
**Internalization** (Claude applies them)

You don't declare principles upfront. You **discover** them through practice.

## Data Structure

All data in `~/.brain/`:

```
~/.brain/
├── roles/              # Role definitions
│   └── {role}/
│       └── values.md   # Core values and principles
│
├── projects/           # Project definitions
│   └── {project}/
│       └── rules.md    # Rules (with optional Context section)
│
└── logs/               # Session logs
    └── {project}/
        └── YYYY-MM-DD_NNN.md
```

**Files are minimal by design:**
- No placeholders or guide text
- Write in your native language
- All sections optional
- Start simple, evolve over time

### Role vs Project

| Layer | Question | Example |
|-------|----------|---------|
| **Role** | "Who am I?" | Developer: "Pragmatism over perfection"<br>Founder: "Speed over consensus" |
| **Project** | "What matters here?" | Personal project: "Learning over shipping"<br>Client work: "Reliability over speed" |

**Why both?**

Same you, different contexts, different decisions:
- Developer + Personal project: "Try experimental approach"
- Developer + Client project: "Use proven approach"

Context shapes decisions. Brain recognizes this.

## Key Principles

**1. Start Minimal**
You don't need to know all your values upfront. Create basic Role/Project, let principles emerge.

**2. Language Matters**
Write values/rules in your native language. "실용성" isn't quite "practicality"—nuance matters.

**3. Patterns Over Declarations**
Brain discovers patterns from your actual decisions, not forced introspection.

**4. Time-Dependent**
Your decision-making evolves. Brain analyzes recent context (last 15 logs), not entire history.

**5. User Approval**
When Brain suggests patterns, you approve them consciously. This metacognitive moment strengthens self-awareness.

**6. Conservative Merging**
"Ship fast" vs "Ship working code fast" may be similar but different. You decide.

## Philosophy

For deeper understanding of Brain's design philosophy, see [PHILOSOPHY.md](PHILOSOPHY.md):
- Why role-based decision-making
- The problem of tacit knowledge
- Discovery through dialogue
- Evolution over configuration
- Replicating your decision-making DNA

## Example Workflow

```bash
# Morning
claude
/brain
# Select: Developer role + Client Project
# Claude now knows: reliability > experimentation

> You: "Should I refactor before adding the feature?"
> Claude: "Based on your Developer values and this being a client project,
>         I'd suggest using the proven approach. Reliability matters more
>         than exploring new patterns here."

[Work on tasks...]

# End of day
/brain-reflect
# → Log saved
# → "Found pattern: You've prioritized reliability 3 times. Update values?"
# → You approve
# → Developer role evolves
```

## GitHub Backup (Optional)

To backup your `~/.brain/` data:

```bash
cd ~/.brain
git init
git add .
git commit -m "Initial brain data"
git remote add origin git@github.com:yourusername/brain-data.git
git push -u origin main
```

**Template repository:** [brain-data](https://github.com/ohgyun/brain-data)

## Development

### Local Testing

```bash
cd /path/to/brain
claude --plugin-dir .
```

### Validation

```bash
# Validate plugin
claude plugin validate plugins/brain/.claude-plugin/plugin.json

# Validate marketplace
claude plugin validate .claude-plugin/marketplace.json
```

## License

MIT
