# Module 11: Rewriting History

> **WARNING:** Never rewrite history that has been pushed to a shared branch that other people are working on. Amending or rebasing commits that others have based their work on will cause serious problems for collaboration. These tools are best used for cleaning up your local commits **before** you push them for the first time.

## `git commit --amend`

This command is a convenient way to modify your most recent commit.

- **Usage:** `git commit --amend`
- **What it does:** It lets you combine staged changes with the previous commit instead of creating a new one. It also gives you an opportunity to re-word the previous commit's message.

**Common Use Cases:**
- You forgot to add a file to your last commit.
- You made a typo in your last commit message.

**Example:**
```bash
# Make a commit
git commit -m "Add feature x"

# Realize you forgot a file
git add forgotten_file.txt

# Amend the previous commit to include the new file
git commit --amend --no-edit
```
`--no-edit` amends the commit without changing its message.

## Interactive Rebase: `git rebase -i`

Interactive rebase is a powerful tool that allows you to alter a series of commits in various ways. You can reorder, edit, combine, or delete commits.

- **Usage:** `git rebase -i HEAD~<number>` (e.g., `HEAD~3` to edit the last 3 commits).
- **What it does:** It opens a text editor with a list of the commits you're about to rebase, providing a script of what to do with each one.

### The Interactive Rebase Screen

You will see something like this:

```
pick 1a2b3c4 Add initial file
pick 5d6e7f8 Add feature
pick 9g8h7i6 Fix typo
```

You can change the command (`pick`) for each commit:

- `pick`: Use the commit as-is.
- `reword` (or `r`): Change the commit message.
- `edit` (or `e`): Stop to amend the commit's changes.
- `squash` (or `s`): Combine this commit's changes into the previous one and be prompted for a new commit message.
- `fixup` (or `f`): Like `squash`, but discard this commit's message entirely.
- `drop` (or `d`): Delete the commit.

After you save and close the file, Git will perform your requested actions. This is an incredibly powerful way to clean up your local history before sharing it with others.
