# Milestone 5: Advanced Techniques Exercises

**Important:** For these exercises, let's create a temporary branch so we don't risk messing up our `main` branch history.

```bash
# Make sure you are on main and up to date
git switch main

# Create a new branch for the exercises
git switch -c advanced-practice
```

### Exercise 1: Amending a Commit

1.  Create a new file `temp.txt` with some text in it.
2.  Stage it and commit it with a typo in the message.
    ```bash
    echo "temporary file" > temp.txt
    git add temp.txt
    git commit -m "feat: Add temproary file"
    ```
3.  Use `git log --oneline` to see your commit.
4.  Now, let's fix the commit message.
    ```bash
    git commit --amend -m "feat: Add temporary file"
    ```
5.  Check the log again. The previous commit has been replaced by the amended one.
6.  Now, create another file `another.txt`, but forget to add it to the commit.
    ```bash
    echo "another file" > another.txt
    git commit -m "docs: Add documentation"
    ```
7.  Oh no, you forgot to `git add another.txt`! Let's amend it into the last commit.
    ```bash
    git add another.txt
    git commit --amend --no-edit
    ```
8.  Check the log. The `docs` commit now includes `another.txt`.

### Exercise 2: Stashing Changes

1.  Open `README.md` and add a new line like "-- In Progress --" but **do not** commit it.
2.  Check `git status`. You have uncommitted changes.
3.  You need to switch branches, so stash your changes.
    ```bash
    git stash
    ```
4.  Your working directory is now clean. Switch to the `main` branch and back.
    ```bash
    git switch main
    git switch advanced-practice
    ```
5.  Reapply your stashed changes.
    ```bash
    git stash pop
    ```
6.  The "-- In Progress --" line is back in your `README.md`.

### Exercise 3: Interactive Rebase (`squash`)

1.  Let's make a few messy commits.
    ```bash
    echo "wip1" >> work.log
    git add work.log
    git commit -m "WIP"

    echo "wip2" >> work.log
    git add work.log
    git commit -m "more work"

    echo "final" >> work.log
    git add work.log
    git commit -m "done now"
    ```
2.  Check your log. You have three messy commits at the top.
3.  Let's clean them up. Start an interactive rebase for the last 3 commits.
    ```bash
    git rebase -i HEAD~3
    ```
4.  Your editor will open. Change the file to `squash` the last two commits into the first one:
    ```
    pick <hash1> WIP
    squash <hash2> more work
    squash <hash3> done now
    ```
5.  Save and close the file. A new editor will open, prompting you to create a new, combined commit message. Enter a clean message like "feat: Add work log with progress".
6.  Save and close that file.
7.  Check your `git log --oneline`. The three messy commits have been replaced by a single, clean one.

### Cleanup

Once you are done, you can delete the practice branch.

```bash
git switch main
git branch -D advanced-practice
```
