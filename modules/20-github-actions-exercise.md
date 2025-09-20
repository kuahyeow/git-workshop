# Milestone 6: GitHub Actions Exercise

In this exercise, we will create a GitHub Actions workflow to automatically lint our JavaScript code.

### Step 1: Create the Project Files

1.  In the root of your `git-workshop` repository, create a file named `package.json` with the necessary `eslint` dependency.
2.  Create a file named `.eslintrc.json` to configure our linting rules.
3.  Create a file named `app.js` that contains some JavaScript code with deliberate errors.

*(Note: The tool has already created these files for you in the root of the project.)*

### Step 2: Create the Workflow

1.  Inside the `.github/workflows/` directory, create a new file named `linter.yml`.

*(Note: The tool has also already created this file for you.)*

### Step 3: Commit and Push to Trigger the Workflow

1.  Stage all the new files.
    ```bash
    git add app.js package.json .eslintrc.json .github/workflows/linter.yml
    ```
2.  Commit the files.
    ```bash
    git commit -m "feat: Add linting workflow and project files"
    ```
3.  Push the commit to your `main` branch on GitHub.
    ```bash
    git push origin main
    ```

### Step 4: Observe the Failing Action

1.  Go to your repository on GitHub and click on the **"Actions"** tab.
2.  You will see a new workflow run, likely with a red X, indicating it has failed.
3.  Click on the workflow run name ("feat: Add linting workflow...").
4.  On the left, click on the `Run linter` job.
5.  Expand the **"Run ESLint"** step. You will see the output from the linter, showing the errors it found in `app.js`.

### Step 5: Fix the Linting Errors

1.  On your local machine, open `app.js`.
2.  Fix the errors reported by the linter. For example:
    - Change `var` to `const` or `let`.
    - Change double quotes to single quotes.
    - Add a semicolon at the end of each line.
    The corrected file should look something like this:
    ```javascript
    const message = 'hello world';

    function greet() {
        console.log(message);
    }

    greet();
    ```
3.  Stage and commit the fix.
    ```bash
    git add app.js
    git commit -m "fix: Correct linting errors"
    ```
4.  Push the fix to GitHub.
    ```bash
    git push
    ```

### Step 6: See the Action Succeed

1.  Return to the **"Actions"** tab on GitHub.
2.  A new workflow run will have started. This time, it should complete successfully with a green checkmark.
3.  You have now successfully created a CI pipeline that automatically validates your code quality!
