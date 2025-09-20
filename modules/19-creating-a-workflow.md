# Module 14: Creating a Workflow

GitHub Actions workflows are defined in YAML files and live in the `.github/workflows` directory of your repository.

## Anatomy of a Workflow File

Let's break down a basic example, `ci.yml`:

```yaml
# 1. The name of your workflow
name: Basic CI

# 2. The events that trigger this workflow
on: [push, pull_request]

# 3. The jobs to run
jobs:
  # 4. The ID of the job (e.g., 'build')
  build:
    # 5. The type of runner to use
    runs-on: ubuntu-latest

    # 6. The sequence of steps to run
    steps:
      # 7. A step to check out your repository's code
      - name: Checkout code
        uses: actions/checkout@v3

      # 8. A step to run a command
      - name: Run a simple command
        run: echo "Hello, world!"
```

### Key Components:

1.  **`name`**: The name of your workflow, which is displayed on the Actions tab in GitHub.
2.  **`on`**: The event(s) that will trigger the workflow. This can be a single event, an array of events, or a map that configures events (e.g., running only for pushes to the `main` branch).
3.  **`jobs`**: A workflow run is made up of one or more jobs, which run in parallel by default.
4.  **Job ID (`build`)**: Each job has a unique identifier.
5.  **`runs-on`**: The type of virtual machine to run the job on. GitHub offers runners for Ubuntu, Windows, and macOS.
6.  **`steps`**: A sequence of tasks to be executed. Steps can run commands or use actions.
7.  **`uses`**: Specifies that this step will use a pre-built, reusable action. `actions/checkout@v3` is a standard action that checks out your repository onto the runner.
8.  **`run`**: Specifies that this step will run a command-line program using the runner's shell.
