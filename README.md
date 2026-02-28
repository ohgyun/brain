# Brain

**Teach Claude how you think**

A Claude Code plugin that helps Claude make decisions the way you would—by learning your principles through conversation, not configuration.

## What & Why

Most decision-making principles are unconscious. You don't think "I'm applying my pragmatist principle"—you just naturally choose to ship with basic tests instead of comprehensive coverage. The principle exists in your actions, not your awareness.

Brain captures these patterns from your conversations and helps Claude learn how you think:
- As Developer vs. Founder (different roles, different values)
- On personal vs. client projects (different contexts, different priorities)
- Over time (your principles evolve as you grow)

You don't configure upfront. Principles emerge through practice.

**Read more:** [PHILOSOPHY.md](PHILOSOPHY.md) explains the design thinking behind Brain.

## Quick Start

**1. Install**

```bash
claude plugin marketplace add ohgyun/brain
claude plugin install brain
```

**2. First session**

```bash
claude

/brain
# Creates your first Role and Project (start minimal)
# Loads context into Claude
```

**3. Work**

Have your conversation. Make decisions. Your principles reveal themselves naturally.

**4. End session**

```bash
/brain-reflect
# Saves meaningful decisions as log
# Analyzes recent patterns
# Offers updates if patterns found
```

All data stored as markdown in `~/.brain/`.

## Commands

| Command | Purpose |
|---------|---------|
| `/brain` | Start session—load Role and Project |
| `/brain-reflect` | End session—save log and discover patterns |

## Data Structure

```
~/.brain/
├── roles/{role}/
│   └── values.md        # Your principles in this role
├── projects/{project}/
│   └── rules.md         # Rules for this context
└── logs/{project}/
    └── YYYY-MM-DD_NNN.md
```

**Role** = "Who I am" (Developer, Founder, etc.)
**Project** = "What matters here" (Client work, Personal project, etc.)

Same you, different roles, different values. Same role, different projects, different priorities.

Files are minimal markdown. Write in your native language. All sections optional.

## License

MIT
