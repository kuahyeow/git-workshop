# Module 16: Organizing with Projects

GitHub Projects provide a visual, Kanban-style board to organize and prioritize your work. You can manage issues, pull requests, and even simple notes as cards on a board.

## Creating a Project Board

1.  Go to the **"Projects"** tab in your repository.
2.  Click **"New project"**.
3.  Choose a template. The "Team backlog" template is a great starting point.
4.  Give your project a name and click **"Create"**.

## Using the Board

- **Columns:** The board is organized into columns representing a status (e.g., `Todo`, `In Progress`, `Done`).
- **Cards:** Each card on the board represents a task. A card can be a GitHub Issue, a Pull Request, or a simple draft note.
- **Adding Issues:** You can add existing issues to your project board. They will appear in the `Todo` column by default.
- **Moving Cards:** Simply drag and drop cards from one column to another to reflect the progress of your work.

## Linking Pull Requests to Issues

This is a critical workflow for automating your project board and keeping it in sync. You can automatically close an issue when a Pull Request that fixes it is merged.

To do this, use a **closing keyword** in your Pull Request's description.

- **Keywords:** `close`, `closes`, `closed`, `fix`, `fixes`, `fixed`, `resolve`, `resolves`, `resolved`.
- **Usage:** `Closes #<issue-number>`

**Example:** If your PR fixes issue #12, you would write `Closes #12` in the PR description.

When the PR is merged, GitHub will automatically close issue #12. If the issue is part of a project board, it will also automatically be moved to the `Done` column.

---

## Exercise: Managing Work on a Project Board

1.  Go to the **"Projects"** tab and create a new project board.
2.  Find the `Update website title` issue you created in the last exercise and add it to the project. It should appear in the `Todo` column.
3.  Drag the card from `Todo` to `In Progress`.
4.  On your local machine, create a new branch to fix the issue.
    ```bash
    git switch -c fix/website-title
    ```
5.  Edit `index.html` and change the `<title>` tag to something more descriptive, like `GitHub Workshop Project`.
6.  Commit and push your branch.
    ```bash
    git add index.html
    git commit -m "fix: Update website title"
    git push -u origin fix/website-title
    ```
7.  On GitHub, create a new Pull Request for your `fix/website-title` branch.
8.  **In the PR description**, add the magic words: `Closes #<issue-number>`, replacing `<issue-number>` with the actual number of your issue.
9.  Create the PR. Notice in the PR and the issue, they are now linked.
10. Merge the Pull Request.
11. Go back to your **"Issues"** tab. The issue is now closed. Go to your **"Projects"** tab. The card has automatically moved to the `Done` column.
