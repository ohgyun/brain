# Brain - Role-based Decision Making System

A decision-making system that helps Claude make consistent decisions aligned with your values and project-specific rules.

## Core Features

- **Role**: Define your core values and principles (e.g., Developer, Product Manager, Founder)
- **Project**: Store project-specific rules and context
- **Log**: Discover patterns from decision history and evolve the system

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

On first run, you'll be guided to create a Role and Project using `/brain-new-role` and `/brain-new-project` commands.

All data is stored as markdown files in the `~/.brain/` directory.

## Key Commands

| Command | Description |
|---------|-------------|
| `/brain` | Start session - Select Role and Project |
| `/brain-status` | Check current Role/Project |
| `/brain-log` | Save current conversation as log |
| `/brain-update` | Analyze logs and suggest rules/values updates |
| `/brain-new-role` | Create new Role |
| `/brain-new-project` | Create new Project |

## How It Works

```
1. Select Role and Project
   ↓
2. values/rules loaded into Claude's context
   ↓
3. Claude makes decisions based on them
   ↓
4. Record meaningful decisions as logs (/brain-log)
   ↓
5. Discover patterns and evolve rules/values (/brain-update)
```

## Data Structure

All data is stored in `~/.brain/`:

```
~/.brain/
├── roles/              # Role definitions
│   └── {role}/
│       └── values.md   # Core values and principles
│
├── projects/           # Project definitions
│   └── {project}/
│       ├── rules.md    # Decision-making rules
│       └── context.md  # Project background
│
└── logs/               # Session logs
    └── {project}/
        └── YYYY-MM-DD_NNN.md
```

### Role vs Project

| Layer | Meaning | Example |
|-------|---------|---------|
| **Role** | "Who I am" | Developer: "Practicality over perfection" |
| **Project** | "How I act in this context" | Brain project: "Minimize writing burden" |

## GitHub Backup (Optional)

To backup your `~/.brain/` data to GitHub:

```bash
# Navigate to ~/.brain directory
cd ~/.brain

# Initialize Git repository
git init
git add .
git commit -m "Initial brain data"

# Create GitHub repository and connect
git remote add origin git@github.com:yourusername/brain-data.git
git push -u origin main
```

**Template repository:** [brain-data](https://github.com/ohgyun/brain-data) - Reference example.

## Development

### Local Testing

```bash
# Run directly from plugin directory
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
