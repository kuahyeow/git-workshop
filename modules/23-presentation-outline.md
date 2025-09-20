# Module 23: Presentation Outline & Speaker Notes

This document provides a slide-by-slide outline for delivering the GitHub workshop.

---

### Slide 1: Title Slide

**Content:**
- Title: The Ultimate GitHub Workshop
- Your Name / Company Name

**Speaker Notes:**
- Welcome everyone. Introduce yourself and the goals for the workshop: to get comfortable with Git and learn how to collaborate effectively on GitHub.

---

### Slide 2: Agenda

**Content:**
- Part 1: Git Fundamentals (What & Why)
- Part 2: Core Commands (`add`, `commit`, `log`)
- Part 3: Branching & Merging
- Part 4: Collaborating with GitHub (Remotes, PRs)
- Part 5: Automation with GitHub Actions
- Part 6: Capstone Project

**Speaker Notes:**
- Briefly walk through the agenda. Emphasize that this is a hands-on workshop and they will be writing commands and working in GitHub for most of it.

---

### Slide 3: What is Version Control?

**Content:**
- A system that records changes to a file or set of files over time so that you can recall specific versions later.
- Think of it as "unlimited undo" for your whole project.
- Allows for collaboration, history tracking, and a safety net.

**Speaker Notes:**
- Use the analogy of saving video game progress or tracking changes in a Google Doc. Explain why this is critical for software projects.

---

### Slide 4: Git is a *Distributed* VCS

**Content:**
- Image showing a centralized vs. distributed model.
- Centralized: One central server. (e.g., Subversion)
- Distributed: Everyone has a full copy of the project history. (e.g., Git)
- This means you can work offline!

**Speaker Notes:**
- Explain the key difference. With Git, you have the entire repository on your local machine. This makes it fast and flexible.

---

### Slide 5: The Three Trees

**Content:**
- Image showing the Working Directory -> Staging Area -> Repository flow.
- **Working Directory:** Your actual files.
- **Staging Area (Index):** A snapshot of what will go into your next commit.
- **Repository (.git dir):** The permanent history of your project.

**Speaker Notes:**
- This is the most important core concept. Walk through the `git add` (Working -> Staging) and `git commit` (Staging -> Repository) flow. Explain that the staging area lets you craft your commits precisely.

---

### Slide 6: Branching

**Content:**
- A branch is a lightweight, movable pointer to a commit.
- Use branches to work on features or bugs in isolation without affecting the main `main` branch.
- `git switch -c <branch-name>`

**Speaker Notes:**
- Use the analogy of a tree. The `main` branch is the trunk, and feature branches are the branches that diverge from it. This is the key to parallel development.

---

### Slide 7: Merging

**Content:**
- Merging combines the work from two branches.
- `git merge <branch-name>`
- Sometimes, you get a **merge conflict**! Don't panic.

**Speaker Notes:**
- Explain that merging is how you bring a completed feature back into the main line. Briefly explain what a conflict is and that the next module covers how to solve them.

---

### Slide 8: The GitHub Flow

**Content:**
- Image showing the Fork -> Clone -> Branch -> Change -> Push -> PR -> Merge workflow.
- This is the foundation of open-source collaboration.

**Speaker Notes:**
- Walk through the entire loop. Explain that a Pull Request is a proposal to merge your changes. It's a place for discussion and code review.

---

### Slide 9: GitHub Actions

**Content:**
- Automate your workflows right from GitHub.
- CI/CD: Continuous Integration & Continuous Delivery.
- Automatically build, test, and lint your code every time you push.

**Speaker Notes:**
- Explain that this is how we ensure code quality and automate repetitive tasks. Show them the "Actions" tab in a repository and what a passing/failing check looks like on a PR.

---

### Slide 10: Capstone Project

**Content:**
- Time to put it all together!
- You will fix an issue, create a PR, and get it merged.

**Speaker Notes:**
- Introduce the final project and explain that it will require them to use all the skills they've just learned.
