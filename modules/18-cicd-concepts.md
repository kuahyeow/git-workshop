# Module 13: CI/CD Concepts

## What is CI/CD?

CI/CD is a cornerstone of modern software development. It stands for **Continuous Integration** and **Continuous Delivery** (or **Continuous Deployment**).

### Continuous Integration (CI)

**Continuous Integration** is the practice of automating the integration of code changes from multiple contributors into a single software project. Developers frequently merge their changes into a central repository, and after each merge, an automated build and automated tests are run.

**The key goals of CI are:**
- To find and address bugs quicker.
- To improve software quality.
- To reduce the time it takes to validate and release new software updates.

### Continuous Delivery / Deployment (CD)

**Continuous Delivery** is the practice of automatically preparing and releasing code changes to a production-like environment. It expands on CI by deploying all code changes to a testing environment and/or a production environment after the build stage has passed.

**Continuous Deployment** goes one step further and automatically deploys every change that passes all stages of your production pipeline to your end users.

## How Does GitHub Actions Fit In?

**GitHub Actions** is a CI/CD platform built directly into GitHub. It allows you to automate your build, test, and deployment pipeline right from your repository.

You can create **workflows** that are triggered by specific **events** in your repository, such as a push, a pull request, or a new issue. These workflows are made up of **jobs**, which in turn are made up of **steps** that run commands or use reusable **actions**.

This makes it incredibly easy to get started with CI/CD without needing a separate, external service.
