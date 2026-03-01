---
name: brain-sync
description: Sync ~/.brain data to GitHub
user-invocable: true
---

# Brain Sync

Synchronize your `~/.brain` data with a GitHub repository.

**Why sync?** Your Brain data (roles, projects, logs) is personal and evolves over time.
Keeping it on GitHub lets you restore it on any machine and never lose your principles.

## Execution Steps

### 1. Check Git Initialization

Check if `~/.brain/.git` exists:
- **Not initialized** → proceed to Step 2 (Initial Setup)
- **Initialized, no remote** → proceed to Step 3 (Add Remote)
- **Initialized, remote exists** → proceed to Step 4 (Sync)

---

### 2. Initialize Git Repository

Run:
```bash
git -C ~/.brain init
git -C ~/.brain symbolic-ref HEAD refs/heads/main
```

Create `~/.brain/.gitignore` if it doesn't exist:
```
# OS generated files
.DS_Store
.DS_Store?
._*
.Spotlight-V100
.Trashes
ehthumbs.db
Thumbs.db
```

Then proceed to Step 3.

---

### 3. Configure Remote Repository

Ask the user how they want to set up the remote:

**Option A: Create with gh CLI (automatic)**
- Check if `gh` is installed: `which gh`
- If not installed: inform user to install GitHub CLI (`brew install gh` on macOS) and fall back to Option B
- If installed:
  - Ask for repository name (default: `brain-data`)
  - Make an initial commit so there's something to push:
    ```bash
    git -C ~/.brain add -A
    git -C ~/.brain commit -m "brain sync: initial commit"
    ```
  - Run: `gh repo create {name} --private --source ~/.brain --push`
  - This creates a private repo, sets the remote, and pushes in one step
  - Skip to Step 5

**Option B: Enter URL manually**
- Ask user to provide the GitHub repository URL
- Suggest creating a **private** repository (personal data)
- Run:
  ```bash
  git -C ~/.brain remote add origin {url}
  ```
- Proceed to Step 4

---

### 4. Sync

#### 4-1. Pull remote changes

```bash
git -C ~/.brain fetch origin main 2>/dev/null
git -C ~/.brain rebase origin/main 2>/dev/null || true
```

Handle pull results:
- **Success or up to date**: proceed normally
- **Conflict detected** (rebase fails):
  - Abort rebase: `git -C ~/.brain rebase --abort`
  - Notify user: "Sync conflict detected. Please resolve manually in ~/.brain before syncing again."
  - Exit

#### 4-2. Commit local changes

```bash
git -C ~/.brain add -A
git -C ~/.brain commit -m "brain sync: $(date '+%Y-%m-%d %H:%M')"
```

- If nothing to commit: note it and continue to push (remote may have been pulled)

#### 4-3. Push to remote

```bash
git -C ~/.brain push -u origin main
```

Handle push results:
- **Success**: proceed to Step 5
- **Rejected (diverged)**: notify user to resolve manually

---

### 5. Confirm

Show a brief summary:
- Sync timestamp
- Files changed (if any)
- Remote URL

Example:
```
Brain synced at 2024-03-01 14:32
Remote: https://github.com/ohgyun/brain-data
3 files updated
```

## Notes

- **Private repository recommended**: Your Brain data contains personal principles and decisions
- **Frequency**: Run `/brain-sync` anytime — after `/brain-reflect` is a natural moment
- **No automatic sync**: Sync is always intentional, triggered by you
