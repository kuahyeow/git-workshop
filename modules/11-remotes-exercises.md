# Milestone 3: Remote Repository Exercises

**Prerequisite:** You must have a GitHub account for these exercises.

### Exercise 1: Create a GitHub Repository

1.  Go to [GitHub.com](https://github.com) and log in.
2.  Create a new **public** repository named `git-workshop-remote`.
3.  **Important:** Do **not** initialize it with a README, .gitignore, or license. We want an empty repository that we can push our existing local project to.
4.  After creating the repository, you will see a page with a URL. Copy the HTTPS URL (it should end with `.git`).

### Exercise 2: Connect Your Local Repo to the Remote

1.  Navigate to your `my-first-repo` project on your local machine.
2.  Add the GitHub repository as a remote for your local repository. Replace `<YOUR-URL>` with the URL you copied.
    ```bash
    git remote add origin <YOUR-URL>
    ```
3.  Verify that the remote has been added successfully.
    ```bash
    git remote -v
    ```
    You should see your `origin` remote listed with `fetch` and `push` URLs.

### Exercise 3: Push Your Local Repo to GitHub

1.  Now, push your local `main` branch to the `origin` remote. The `-u` flag will set up a tracking relationship.
    ```bash
    git push -u origin main
    ```
2.  Go back to your repository on GitHub.com and refresh the page. You should now see all your files (`README.md`, `LICENSE`, etc.) online.

### Exercise 4: Simulate Collaboration (Clone and Push)

1.  Let's simulate being another collaborator (or working from a new computer). Navigate to a different directory on your computer, outside of `my-first-repo`.
    ```bash
    cd ..
    ```
2.  Clone the repository from GitHub to a new local copy.
    ```bash
    git clone <YOUR-URL>
    ```
3.  Navigate into the newly cloned directory.
    ```bash
    cd git-workshop-remote
    ```
4.  Create a new file called `CONTRIBUTORS.md` and add your name to it.
    ```bash
    echo "- Your Name" > CONTRIBUTORS.md
    ```
5.  Stage, commit, and push this change to GitHub.
    ```bash
    git add CONTRIBUTORS.md
    git commit -m "Add contributors file"
    git push
    ```
    (Note: You don't need to specify `origin main` because of the tracking relationship set up by `clone`.)

### Exercise 5: Pull Remote Changes

1.  Now, let's go back to your original project and get the latest changes.
    ```bash
    cd ../my-first-repo
    ```
2.  You'll notice that `CONTRIBUTORS.md` is not here.
3.  Pull the changes from the remote repository.
    ```bash
    git pull
    ```
4.  The `CONTRIBUTORS.md` file should now appear in your directory. You are now in sync with the remote repository.
