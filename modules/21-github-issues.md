# Module 15: Using GitHub Issues

GitHub Issues are the primary tool for tracking tasks, enhancements, and bugs for your projects. They are much more than a simple bug tracker; they are a powerful hub for discussion and project management.

## Anatomy of an Issue

When you open an issue, you'll see a form with several fields:

- **Title & Description:** A clear title and a detailed description (which supports Markdown) are essential for good communication.
- **Assignees:** The person or people responsible for working on the issue.
- **Labels:** Tags to categorize the issue. This is one of the most powerful features for organization. Common labels include `bug`, `feature-request`, `documentation`, `help-wanted`, `good-first-issue`.
- **Projects:** Allows you to link the issue to a project board for visual tracking.
- **Milestones:** A way to group issues into a larger goal, like `Version 1.0 Launch` or `Q3-Cleanup`.

## Issue Templates

To encourage structured and complete reports from contributors, you can create **Issue Templates**. These are pre-filled templates for the issue description.

- They live in the `.github/ISSUE_TEMPLATE` directory of your repository.
- You can have different templates for different purposes (e.g., Bug Report vs. Feature Request).

**Example `bug_report.yml` template:**
```yaml
name: Bug Report
description: File a bug report
body:
  - type: markdown
    attributes:
      value: "Thanks for taking the time to fill out this bug report!"
  - type: textarea
    id: what-happened
    attributes:
      label: What happened?
      description: "Also tell us, what did you expect to happen?"
    validations:
      required: true
```

---

## Exercise: Creating and Managing an Issue

1.  In your `git-workshop-remote` repository on GitHub, click on the **"Issues"** tab.
2.  Click the **"New issue"** button.
3.  Give it a title: `Update website title`.
4.  In the description, write: `The HTML title tag in index.html is generic and should be updated.`
5.  On the right-hand side, assign the issue to yourself.
6.  Click on "Labels" and select the `documentation` or `enhancement` label (if they don't exist, you can create them!).
7.  Click **"Submit new issue"**.
8.  You have now created your first issue! Click on it and try leaving a comment.
