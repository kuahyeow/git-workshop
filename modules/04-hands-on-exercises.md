# Milestone 1: Hands-On Exercises

Follow these steps to practice the core Git commands.

### Exercise 1: Setup

1.  Open your terminal or command prompt.
2.  If you haven't already, configure your Git user name and email using `git config`.
    ```bash
    git config --global user.name "Your Name"
    git config --global user.email "you@example.com"
    ```

### Exercise 2: Create a Local Repository

1.  Create a new directory for your project called `my-first-repo`.
    ```bash
    mkdir my-first-repo
    ```
2.  Navigate into the new directory.
    ```bash
    cd my-first-repo
    ```
3.  Initialize a new Git repository.
    ```bash
    git init
    ```
4.  (Optional) List the contents of the directory, including hidden files, to see the `.git` folder.
    ```bash
    ls -a
    ```

### Exercise 3: Your First Commit

1.  Create a new file named `README.md` and add some text to it. You can use a text editor or the command line.
    ```bash
    echo "# My First Repo" > README.md
    ```
2.  Check the status of your repository. You should see `README.md` listed as an "untracked file".
    ```bash
    git status
    ```
3.  Add the new file to the staging area.
    ```bash
    git add README.md
    ```
4.  Check the status again. You should now see that `README.md` is a "new file" ready to be committed.
    ```bash
    git status
    ```
5.  Commit the file to your project history with a descriptive message.
    ```bash
    git commit -m "Add project README"
    ```
6.  View the history of your project. You should see your first commit.
    ```bash
    git log
    ```

### Exercise 4: The Modify-Stage-Commit Cycle

1.  Open `README.md` and add another line of text, like "A project to practice Git commands."
2.  Check the status. Git will show that `README.md` has been "modified".
    ```bash
    git status
    ```
3.  Stage the modified file.
    ```bash
    git add README.md
    ```
4.  Commit the change with a new message.
    ```bash
    git commit -m "Update README with project description"
    ```
5.  View the log again to see both of your commits.
    ```bash
    git log --oneline
    ```
