# Module 2: Getting Started with Git

## Installing Git

Before you can use Git, you need to install it on your computer.

- **macOS:** The easiest way is to install the Xcode Command Line Tools. On Mavericks (10.9) or above, you can do this by trying to run `git` from the Terminal for the first time. If you don’t have it installed already, it will prompt you to install it. Alternatively, you can install it with [Homebrew](https://brew.sh/) (`brew install git`).
- **Windows:** The official build is available for download on the [Git website](https://git-scm.com/download/win). Download the Git for Windows installer and run it.
- **Linux:** You can generally install Git through your distribution's package management system. For example, on Debian/Ubuntu, you can run `sudo apt-get install git`.

## First-Time Git Configuration

Once Git is installed, you need to do a few one-time configuration steps. These settings are attached to every commit you make.

Run the following commands from your terminal, replacing the example name and email with your own.

1.  **Set your user name:**
    ```bash
    git config --global user.name "Your Name"
    ```

2.  **Set your user email address:**
    ```bash
    git config --global user.email "you@example.com"
    ```

These are global settings, meaning they will apply to every Git repository on your system. You only need to do this once.
