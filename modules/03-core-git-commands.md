# Module 3: Core Git Commands

This module covers the essential commands you'll use in your daily workflow.

## `git init`

This command is used to create a new Git repository.

- **Usage:** `git init`
- **What it does:** It creates a new subdirectory named `.git` in your current directory. This is where Git stores all the metadata and object database for your project. This `.git` directory is the heart of your repository.

## `git status`

This command shows the current state of your working directory and staging area.

- **Usage:** `git status`
- **What it does:** It lets you see which changes have been staged, which haven't, and which files aren't being tracked by Git.

## `git add`

This command adds changes from the working directory to the staging area.

- **Usage:** `git add <file-name>` or `git add .` to add all changes.
- **What it does:** It takes a "snapshot" of the file as it is and adds that snapshot to the staging area. You can think of the staging area as a preparation space for your next commit.

## `git commit`

This command saves the staged snapshot to the project's history.

- **Usage:** `git commit -m "Your descriptive message"`
- **What it does:** It takes the files from the staging area and permanently saves them in the Git directory. The `-m` flag allows you to provide a commit message directly from the command line.

## `git log`

This command is used to view the history of commits.

- **Usage:** `git log`
- **What it does:** It shows a list of all the commits made in the repository, starting with the most recent. Each log entry includes the commit hash (a unique ID), the author, the date, and the commit message.
- **Useful options:**
    - `--oneline`: Condenses each commit to a single line.
    - `--graph`: Shows a simple ASCII graph of the branch and merge history.
    - `--all`: Shows the history of all branches.
