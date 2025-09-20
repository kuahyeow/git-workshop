# Module 5: Merging

Merging is how you integrate changes from a divergent branch back into your current branch.

## The `git merge` Command

This command takes the changes from another branch and combines them with the current branch.

- **Usage:** `git merge <branch-name-to-merge-in>`
- **Example:** If you are on the `main` branch and want to merge in the `new-feature` branch, you would run:
  ```bash
  git switch main
  git merge new-feature
  ```

## Types of Merges

There are two primary ways Git will perform a merge:

### 1. Fast-Forward Merge

A fast-forward merge can occur when there is a linear path from the current branch tip to the target branch. This means that since you created the feature branch, the `main` branch has not had any new commits.

In this case, Git simply moves the `main` branch pointer forward to point to the same commit that the `new-feature` branch does. No new commit is created.

![Fast-Forward Merge](https://git-scm.com/book/en/v2/images/basic-merging-1.png)

### 2. Three-Way Merge

If the branches have diverged (i.e., there have been commits on both branches since they were created), Git can't just move the pointer forward. It has to combine the work.

In this scenario, Git performs a "three-way merge." It uses the two snapshots pointed to by the branch tips and their common ancestor to create a new snapshot (and a new commit).

This new commit is special because it has two parents. It's called a **merge commit**.

![Three-Way Merge](https://git-scm.com/book/en/v2/images/basic-merging-2.png)
