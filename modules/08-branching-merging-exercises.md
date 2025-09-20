# Milestone 2: Branching & Merging Exercises

These exercises build on the `my-first-repo` project from the previous milestone.

### Exercise 1: Create and Work on a Feature Branch

1.  Navigate to your `my-first-repo` directory.
2.  Create a new branch called `add-license`.
    ```bash
    git branch add-license
    ```
3.  Switch to your new branch.
    ```bash
    git switch add-license
    ```
4.  Create a new file named `LICENSE` and add some text (e.g., "MIT License").
    ```bash
    echo "MIT License" > LICENSE
    ```
5.  Stage and commit the new file to the `add-license` branch.
    ```bash
    git add LICENSE
    git commit -m "Add LICENSE file"
    ```
6.  Switch back to the `main` branch.
    ```bash
    git switch main
    ```
7.  Notice that the `LICENSE` file is no longer in your directory. Don't worry, it's safe in the `add-license` branch!

### Exercise 2: Fast-Forward Merge

1.  While on the `main` branch, merge your `add-license` branch.
    ```bash
    git merge add-license
    ```
2.  You should see a "fast-forward" message. The `LICENSE` file is now on your `main` branch.
3.  View the history to see the new commit is now at the tip of `main`.
    ```bash
    git log --oneline
    ```
4.  It's good practice to delete the feature branch after it has been merged.
    ```bash
    git branch -d add-license
    ```

### Exercise 3: Induce and Resolve a Merge Conflict

1.  First, let's create a new branch to work on.
    ```bash
    git branch update-readme
    ```
2.  Switch to the `update-readme` branch.
    ```bash
    git switch update-readme
    ```
3.  Open `README.md` and change the first line to: `A repository for the official Git Workshop.` Commit this change.
    ```bash
    # (Edit the file, then...)
    git add README.md
    git commit -m "Update README title on feature branch"
    ```
4.  Now, switch back to `main` to simulate a co-worker's change.
    ```bash
    git switch main
    ```
5.  Open `README.md` on the `main` branch and change the *same first line* to: `# My First Git Repository`. Commit this change.
    ```bash
    # (Edit the file, then...)
    git add README.md
    git commit -m "Update README title on main"
    ```
6.  Now, try to merge the `update-readme` branch into `main`.
    ```bash
    git merge update-readme
    ```
7.  **You will get a merge conflict!** Open `README.md` in your editor. You will see the conflict markers.
8.  Resolve the conflict: Edit the file to look how you want. For this exercise, let's choose the title from the `main` branch. Delete the other lines and all the conflict markers (`<<<`, `===`, `>>>`). The file should just contain:
    ```
    # My First Git Repository
    A project to practice Git commands.
    ```
9.  Stage the now-resolved `README.md` file.
    ```bash
    git add README.md
    ```
10. Finalize the merge by committing. A pre-populated commit message will appear. You can just save it.
    ```bash
    git commit
    ```
11. View the history with a graph to see the merge commit.
    ```bash
    git log --oneline --graph
    ```
