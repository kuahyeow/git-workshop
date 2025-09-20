# Milestone 4: The Pull Request Workflow Exercise

This exercise simulates the full open-source contribution workflow. You will act as both the contributor and the project maintainer.

### Exercise 1: Fork and Clone

1.  In your web browser, go to the GitHub page for your `git-workshop-remote` repository that you created in the previous milestone.
2.  You are going to pretend this is someone else's project. Click the **"Fork"** button in the top-right to create a copy of this repository under your own GitHub account.
3.  On your local machine, navigate to a new directory (e.g., `cd ..` from your previous project folders).
4.  Clone **your fork** to your local machine. Replace `<YOUR-USERNAME>`.
    ```bash
    git clone https://github.com/<YOUR-USERNAME>/git-workshop-remote.git
    ```
5.  Navigate into the cloned directory.
    ```bash
    cd git-workshop-remote
    ```

### Exercise 2: Configure the `upstream` Remote

1.  Add a remote that points to the **original** repository. This is the "upstream". Replace `<YOUR-USERNAME>` with your actual username.
    ```bash
    git remote add upstream https://github.com/<YOUR-USERNAME>/git-workshop-remote.git
    ```
    *(Note: In a real scenario, you would be using the original owner's URL here, but for this simulation, you are the original owner.)*
2.  Verify your remotes are set up correctly.
    ```bash
    git remote -v
    ```
    You should see `origin` (pointing to your fork) and `upstream` (pointing to the original repo).

### Exercise 3: Create a Feature and Push to Your Fork

1.  Create a new branch to work on a change.
    ```bash
    git switch -c add-project-goal
    ```
2.  Open the `README.md` file and add a new section:
    ```markdown
    ## Project Goal

    The goal of this project is to provide a space for workshop participants to practice Git and GitHub commands.
    ```
3.  Stage and commit your change.
    ```bash
    git add README.md
    git commit -m "docs: Add project goal to README"
    ```
4.  Push your new branch to **your fork** (`origin`).
    ```bash
    git push -u origin add-project-goal
    ```

### Exercise 4: Open a Pull Request

1.  Go to the original `git-workshop-remote` repository on GitHub (not your fork).
2.  You should see a yellow banner saying "`add-project-goal` had recent pushes". Click the **"Compare & pull request"** button.
3.  If you don't see the banner, go to the "Pull requests" tab and click "New pull request".
4.  Ensure the base repository is your original repo and the `base` branch is `main`. The head repository should be your fork and the `compare` branch should be `add-project-goal`.
5.  Give your PR a title (e.g., "Add Project Goal") and a brief description.
6.  Click **"Create pull request"**.

### Exercise 5: Review and Merge the Pull Request

1.  You are now acting as the project maintainer. In the "Pull requests" tab of your original repository, you will see the PR you just opened.
2.  Click on the PR to view it.
3.  Go to the "Files changed" tab to review the changes. You could add a line comment here if you wanted to.
4.  Go back to the "Conversation" tab. Everything looks good, so click the **"Merge pull request"** button, and then **"Confirm merge"**.

### Exercise 6: Clean Up and Sync

1.  After merging, it's good practice to delete the feature branch. Click the **"Delete branch"** button on the PR page.
2.  Now, go back to your local machine (in the `git-workshop-remote` directory).
3.  Your `main` branch doesn't have the new changes yet. Switch to it.
    ```bash
    git switch main
    ```
4.  Pull the latest changes from the **`upstream`** repository.
    ```bash
    git pull upstream main
    ```
5.  Your local `main` branch is now up-to-date with the merged changes. You can verify by checking the content of `README.md`.
