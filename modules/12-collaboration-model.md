# Module 9: The Collaboration Model

When working on projects where you don't have direct write access, or in most open-source projects, the standard workflow is "Fork & Pull Request".

This model allows anyone to contribute to a project in a structured and controlled way.

## 1. Forking a Repository

A **fork** is a personal, server-side copy of a repository. When you fork a project on GitHub, you are creating a complete copy of it under your own GitHub account. This new repository is entirely yours; you can write to it, create branches, and experiment freely without affecting the original project.

To fork a repository, you simply navigate to its page on GitHub and click the **"Fork"** button in the top-right corner.

## 2. Cloning Your Fork

Once you have a fork, you clone it to your local machine just like any other repository. This is the copy you will work on locally.

```bash
# Clone YOUR fork, not the original repository
git clone https://github.com/YOUR-USERNAME/the-forked-repo.git
```

## 3. Configuring an `upstream` Remote

Your cloned fork has a remote named `origin` that points to your fork on GitHub. However, you also need a way to keep your fork updated with any new changes from the original project.

To do this, you add another remote, conventionally named `upstream`, that points to the original repository.

- **Usage:** `git remote add upstream <original-repo-url>`

Now you have two remotes:
- `origin`: Points to your fork (`YOUR-USERNAME/the-forked-repo`). You can push to this.
- `upstream`: Points to the original repo (`ORIGINAL-OWNER/the-forked-repo`). You can only fetch from this.

### Keeping Your Fork in Sync

To pull in changes from the original project, you'll fetch from `upstream` and merge them into your local `main` branch.

```bash
# Fetch the latest changes from the original repository
git fetch upstream

# Switch to your local main branch
git switch main

# Merge the changes from upstream/main into your local main
git merge upstream/main

# (Optional) Push the updates to your fork on GitHub
git push origin main
```
