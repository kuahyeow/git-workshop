# Module 8: Working with Remotes

A "remote" is a version of your repository that is hosted on the internet or another network. When you collaborate with others, you need to manage these remote repositories to share your work.

## `git clone`

This is how you get a local copy of an existing remote repository.

- **Usage:** `git clone <url>`
- **What it does:** It creates a new directory on your local machine, copies the entire project history into it, and automatically sets up a remote connection named `origin` that points to the URL you cloned from.

## `git remote`

This command is used to manage the set of remotes you are tracking.

- **`git remote -v`**: Lists the shortnames and URLs of your remote connections.
- **`git remote add <name> <url>`**: Connects your local repository to a new remote. The conventional name for the primary remote is `origin`.

## `git push`

This command is used to upload your committed changes to a remote repository.

- **Usage:** `git push <remote-name> <branch-name>`
- **What it does:** It sends all the commits you have on your local branch that are missing from the remote branch.
- **`--set-upstream` (or `-u`)**: The first time you push a new branch, you should use the `-u` flag (`git push -u origin main`). This sets up a tracking relationship between your local branch and the remote branch, allowing you to simply use `git push` and `git pull` in the future without specifying the remote and branch.

## `git fetch`

This command downloads commits, files, and refs from a remote repository into your local repo, but it does **not** merge them.

- **Usage:** `git fetch <remote-name>`
- **What it does:** It allows you to see what others have been working on without having to merge it into your local branches immediately. This is a safe way to review changes before integrating them.

## `git pull`

This command is a combination of `git fetch` followed by `git merge`.

- **Usage:** `git pull <remote-name> <branch-name>`
- **What it does:** It fetches the specified remote branch and immediately tries to merge it into the branch you are currently on. This is a common way to keep your local repository up-to-date with the remote.
