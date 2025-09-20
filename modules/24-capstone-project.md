# Module 24: Capstone Project

## Objective

To use all the skills learned in this workshop to contribute a new feature to the workshop's website, triggered by a GitHub Issue.

## The Scenario

The workshop organizers want to add a new "Advanced Topics" section to the `index.html` website to reflect the content of the workshop. An issue has already been created for this task.

## Step-by-Step Guide

1.  **Find and Assign the Issue:**
    - Go to the main project repository on GitHub.
    - In the **"Issues"** tab, find the issue titled **"Feature: Add Advanced Topics section to website"**. *(Instructor: You will need to create this issue before the workshop)*.
    - Open the issue and assign it to yourself.

2.  **Fork, Clone, and Configure:**
    - Fork the repository to your own GitHub account.
    - Clone your fork to your local machine.
    - Configure the original repository as your `upstream` remote.

3.  **Create a Feature Branch:**
    - Before writing any code, create a new, descriptive branch.
    - `git switch -c feat/advanced-topics-section`

4.  **Develop the Feature:**
    - Open `index.html` in your editor.
    - Add a new "module" div to the page for advanced topics. It should look something like this:
      ```html
      <div class="module">
          <h3>Module 4: Advanced Topics</h3>
          <p>Explore powerful tools like interactive rebase, stashing, and the reflog. We'll also build a CI pipeline with GitHub Actions.</p>
      </div>
      ```

5.  **Fix the CI Build:**
    - The project is configured to run a linter, and there are known errors in the `app.js` file.
    - Open `app.js` and fix the linting errors (change `var` to `const`, use single quotes, add semicolons).

6.  **Commit and Push:**
    - Create two separate, clean commits.
      ```bash
      # First commit the feature
      git add index.html
      git commit -m "feat: Add advanced topics section to website"

      # Then commit the fix
      git add app.js
      git commit -m "fix: Correct linting errors in app.js"
      ```
    - Push your branch to your fork (`origin`).
      ```bash
      git push -u origin feat/advanced-topics-section
      ```

7.  **Open a Pull Request:**
    - Go to the original repository on GitHub and open a new Pull Request for your branch.
    - In the description, write **`Closes #<issue-number>`** to automatically link it to the issue.

8.  **Review and Merge:**
    - As the "maintainer", review your own PR.
    - Check that the GitHub Actions CI build is green (passing).
    - Merge the Pull Request.

9.  **Confirm Your Work:**
    - Check that the issue you were assigned is now closed.
    - Check the main project's website to see your new section is live.

Congratulations, you've completed the full GitHub contribution workflow!
