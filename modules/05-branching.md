# Module 4: Branching

## What is a Branch?

In Git, a branch is a lightweight movable pointer to a commit. When you start making commits, you're given a default branch named `main` (or `master`) that points to the last commit you made. When you create a new branch, you're creating a new pointer to that same commit.

Think of it as a new line of development. It allows you to diverge from the main line of work to, for example, develop a new feature or fix a bug without affecting the stable `main` branch.

## Why Use Branches?

- **Isolation:** Work on a new feature without worrying about breaking the main codebase. If you make a mistake, you can just delete the branch and start over.
- **Parallel Development:** Multiple people can work on different features simultaneously, each in their own branch.
- **Organization:** It helps keep your project history clean and understandable. Each feature or bug fix can have its own dedicated branch.

## Core Branching Commands

- **`git branch`**: Lists all of the branches in your repository.
  ```bash
  git branch
  ```
- **`git branch <branch-name>`**: Creates a new branch.
  ```bash
  git branch new-feature
  ```
- **`git checkout <branch-name>`** or **`git switch <branch-name>`**: Switches to the specified branch. `switch` is the newer, safer command.
  ```bash
  git switch new-feature
  ```
- **`git branch -d <branch-name>`**: Deletes a branch (if it has been merged).
  ```bash
  git branch -d new-feature
  ```
