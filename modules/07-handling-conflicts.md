# Module 6: Handling Conflicts

## When Do Conflicts Happen?

A merge conflict occurs when you try to merge two branches that have competing changes, and Git doesn't know which change to accept. This typically happens when two developers have changed the **same lines in the same file**, or if one developer deleted a file while another developer was modifying it.

Git will pause the merge process and wait for you to resolve the conflict manually.

## How to Resolve a Merge Conflict

1.  **Identify the Conflict:** When you try to merge, Git will tell you if there's a conflict. You can also run `git status` to see which files are in a conflicted state.

    ```
    Auto-merging README.md
    CONFLICT (content): Merge conflict in README.md
    Automatic merge failed; fix conflicts and then commit the result.
    ```

2.  **Open the Conflicted File:** When you open the file in your text editor, you will see the conflict markers that Git has added:

    ```
    <<<<<<< HEAD
    This is the content from your current branch (main).
    =======
    This is the content from the other branch (feature).
    >>>>>>> feature
    ```

    - The content between `<<<<<<< HEAD` and `=======` is from your current branch (`HEAD`).
    - The content between `=======` and `>>>>>>> <branch-name>` is from the branch you are trying to merge in.

3.  **Fix the Conflict:** Edit the file to be exactly how you want it. This might mean keeping your changes, keeping the other branch's changes, or a combination of both. You must also **delete the conflict markers** (`<<<<<<<`, `=======`, `>>>>>>>`).

    For example, you might decide to combine them:
    ```
    This is the combined content from both main and the feature branch.
    ```

4.  **Stage the Resolved File:** Once you've saved the file, you need to tell Git that the conflict is resolved by staging the file.

    ```bash
    git add <conflicted-file-name>
    ```

5.  **Commit the Merge:** After staging all conflicted files, you can create the merge commit to finalize the merge. Running `git commit` will open your text editor with a pre-populated merge commit message, which you can usually just save and close.

    ```bash
    git commit
    ```
