# Brain

**Teach Claude how you think**

A Claude Code plugin that helps Claude make decisions the way you would—by learning your principles through conversation, not configuration.

## What is Brain?

Most of your decision-making principles are unconscious. You don't explicitly think "I'm applying my pragmatist principle." You just naturally choose to send a quick draft for feedback rather than perfecting it alone. The principle exists in your actions, not your awareness.

Brain captures these patterns from your conversations and helps Claude learn how you think:

**Different roles, different values**
- As an Individual Contributor: "Deep work over meetings"
- As a Manager: "Team consensus over quick decisions"

**Different contexts, different priorities**
- Personal project: "Try new things, learning matters"
- Client work: "Proven solutions, reliability matters"

**Over time**
- Your principles evolve as you grow
- Brain analyzes recent patterns (not your entire history)
- Focuses on who you are now

You don't configure values upfront. They emerge through practice, then Brain helps you recognize and formalize them.

**Want to understand the philosophy?** Read [PHILOSOPHY.md](PHILOSOPHY.md) for the thinking behind Brain's design.

## Quick Start

**Install the plugin:**

```bash
claude plugin marketplace add ohgyun/brain
claude plugin install brain
```

**Using Brain:**

Every time you start a conversation with Claude:

```bash
claude

/brain
# First time: Creates your first Role and Project (start simple)
# Subsequent times: Selects which Role and Project to use
# Loads your context so Claude knows how you think
```

Work on your task. Have conversations. Make decisions naturally.

When you're done with the conversation:

```bash
/brain-reflect
# Saves meaningful decisions as a log
# Analyzes your recent logs for patterns
# If patterns found: Asks if you want to update your values/rules
```

That's the workflow: `/brain` when you start, `/brain-reflect` when you finish.

## Commands

| Command | When to use | What it does |
|---------|-------------|--------------|
| `/brain` | Start of conversation | Load your Role and Project context into Claude |
| `/brain-reflect` | End of conversation | Save log and discover patterns from recent decisions |

## How Your Data is Stored

Brain stores everything as simple markdown files in `~/.brain/`:

```
~/.brain/
├── roles/
│   └── {role-name}/
│       └── values.md          # Your core principles for this role
│
├── projects/
│   └── {project-name}/
│       └── rules.md           # Decision-making rules for this project
│
└── logs/
    └── {project-name}/
        └── YYYY-MM-DD_NNN.md  # Daily decision logs
```

**Role** represents who you are in a conversation. For example: "Developer", "Manager", "Consultant". Each role has its own values.

**Project** represents the context. For example: "client-work", "personal-experiments", "open-source". Each project has its own rules.

**Why both?** Because the same you makes different decisions in different contexts:
- Developer + Personal project → "Experiment with new approaches"
- Developer + Client work → "Use proven, stable solutions"

All files are plain markdown. Write in your native language. Start minimal—you can always expand later.

## License

MIT
