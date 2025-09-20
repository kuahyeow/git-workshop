# Module 12: Useful Git Tools

This module covers a few powerful Git commands that can make your life easier.

## `git stash`

Have you ever been in the middle of working on something, but you need to suddenly switch branches to fix an urgent bug? Your working directory is messy, and you can't commit yet. `git stash` is the answer.

- **What it does:** It takes your modified tracked files (both staged and unstaged) and saves them away on a stack of unfinished changes that you can reapply at any time.

### Common Workflow

1.  **`git stash`**: Save your current work.
    ```bash
    git stash
    ```
2.  Your working directory is now clean (matching the `HEAD` commit). You can switch branches, pull changes, etc.

3.  **`git stash list`**: View your stashes.
    ```bash
    git stash list
    # stash@{0}: WIP on main: 1a2b3c4 Add initial file
    ```

4.  **`git stash pop`**: Reapply the most recently stashed changes and remove the stash from the list.
    ```bash
    git stash pop
    ```

## `git cherry-pick`

This command allows you to pick a single commit from one branch and apply it onto another.

- **Usage:** `git cherry-pick <commit-hash>`
- **Use Case:** Imagine you have a bug fix on a feature branch that hasn't been fully merged, but you need to apply that specific fix to your `main` branch immediately. You can cherry-pick just that one commit.

## `git reflog`

`git reflog` is your ultimate safety net. Git records almost every move you make (commits, resets, rebases, merges). The reflog tracks the history of where your `HEAD` pointer has been.

- **What it does:** It shows a log of your repository's `HEAD` history. This is invaluable if you think you've "lost" work.
- **Use Case:** You performed a `git reset --hard` and think you deleted a commit. Or you made a mistake during a rebase and commits have vanished.

**Example:**
```bash
# Run git reflog to see the history of your HEAD
git reflog
# 1a2b3c4 HEAD@{0}: reset: moving to 1a2b3c4
# 5d6e7f8 HEAD@{1}: commit: Add new feature
# 9g8h7i6 HEAD@{2}: commit: Add initial file
```
If you realize you accidentally reset away the "Add new feature" commit (`5d6e7f8`), you can restore it:

```bash
# You can use the reflog pointer
git reset --hard HEAD@{1}

# Or the commit hash itself
git reset --hard 5d6e7f8
```
