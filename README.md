# Shared Todo List

A collaborative todo list with git-based synchronization.

## Setup

1. Clone this repo
2. Add the repo to your PATH or create an alias:
   ```bash
   alias todo='/path/to/shared-todos/todo'
   ```

## Usage

```bash
# List all todos
todo list

# Add a new task (priority 1-3, list: today|backlog)
todo add "Task description" 1 today "Optional context"

# Mark task as in progress
todo start <id>

# Mark task as complete
todo complete <id>

# Move between lists
todo move <id> today
todo move <id> backlog

# Edit a task
todo edit <id> text "New description"
todo edit <id> priority 2
todo edit <id> context "New context"

# Delete a task
todo delete <id>

# Manual sync
todo sync
```

## How it works

Every command automatically:
1. **Pulls** latest changes from remote (if configured)
2. Makes the requested change
3. **Commits** and **pushes** the change

This ensures everyone always has the latest version and conflicts are minimized.

## Setting up remote

```bash
cd /path/to/shared-todos
git remote add origin <your-git-repo-url>
git push -u origin main
```

Others can then clone and use the same todo list!
