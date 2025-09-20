# Module 10: Pull Requests (PRs)

A **Pull Request** (or PR) is the heart of collaboration on GitHub. It's a formal proposal to merge changes from one branch into another. Typically, this means you are proposing to merge a feature branch from your fork into the `main` branch of the original (`upstream`) repository.

A PR is a request to the maintainers of the upstream project to "pull" your changes into their codebase.

## The Pull Request Workflow

1.  **Create a Feature Branch:** Always create a new, descriptively named branch on your local machine to work on your changes.
2.  **Make and Commit Changes:** Edit code, fix bugs, or add features. Make one or more commits to your feature branch.
3.  **Push to Your Fork:** Push your feature branch to your fork on GitHub (`origin`).
    ```bash
    git push -u origin my-new-feature
    ```
4.  **Open a Pull Request:** Go to the original (`upstream`) repository on GitHub. You will often see a banner prompting you to create a PR from your recently pushed branch. Click it, or go to the "Pull Requests" tab and click "New pull request".

## The Code Review Process

Once a PR is opened, it creates a forum for discussion and review.

- **Discussion:** You and the project maintainers can have a conversation about the proposed changes in the PR's comment thread.
- **Line Comments:** Reviewers can comment on specific lines of code in the "Files Changed" tab to ask questions or suggest improvements.
- **Updating a PR:** If a maintainer requests changes, you don't need to close the PR. Simply make more commits on your local feature branch and push them to your fork. The new commits will automatically be added to the existing PR.
- **Approval:** Once the maintainers are happy with the changes, they will approve the PR.

## Merging a Pull Request

After approval, a project maintainer will merge your PR. GitHub provides a few options for this:

- **Create a merge commit:** This is similar to a standard `git merge`. It creates a merge commit in the project history, preserving the context of the feature branch.
- **Squash and merge:** This combines all of the PR's commits into a single commit before merging. This results in a cleaner, more linear project history.
- **Rebase and merge:** This takes all the commits from the feature branch and adds them to the end of the `main` branch history without creating a merge commit.

Once merged, your changes are officially part of the project!
