# GitHub Features

## Introduction

GitHub is a cloud-based platform for **Version control and collaborative development**. It privides tools for managing repositories, tracking changes and issues, reviewing code, and automating workflows. Developers use GitHub to host projects, collaborate with teams, and integrate CI/CD pipelines. This chapter explores GitHub's core features and their usage.

## Repositories

### Overview

A **repository (repo)** is a storage location for project files, version history, and collaboration tolls. Repositories can be **Public** (visible to everyone) or **private** (restricted to selected users). Developers use repositories to store source code documentation, and project-related files. 

### Steps

1. **Create a new repository**:
    - Go to [GitHub](https://github.com) and Sign in.
    - Click **"New"** to create a new repository.
    - Provide a **repository name**, an optional **description**, and choose **Public** or **Private**.
    - Initialize with a **README**, **.gitignore**, or **license** if needed.
    - Click **"Create repository"** to finish.

2. ** CLone an existing repository (to work locally)** :

    ```bash
    git clone <repository-url>
    cd repository
    ```

3. **Link a local project to a remote repository**:

    ```bash
    git init    # Initialize a new Git repository
    git remote add origin <repository-url>
    git add .
    git commit -m "initial commit"
    git push -u origin main
    ```


## Branches

### Overview

A branch is an independent version of the project where changes can be made without affecting the ``main`` branch. Branching allows for parallel development, feature isolation and controlled code merging.

### Steps

1. **Create and switching toa new branch** :

    ```bash
    git checkout -b <branch-name>
    ```

2. **List available branches** :

    ```bash
    git branch
    ```

3. **Switch to an existing branch** :

    ```bash
    git checkout <branch-name>
    ```

4. **Merge a branch into ``main``** :

    ```bash
    git checkout main
    git merge <branch-name>
    ```

5. **Delete a branch after merging** :

    ```bash
    git branch -d <branch-name> # Delete local branch
    git push origin --delete <branch-name> # Delete remote branch
    ```
## Pull Requests (PRs)

### Overview 

A **Pull Request (PRs)** is a request to merge changes from one branch into another. PRs enable **code review, discussion, and approval before merging**. They are commonly used in collaborative projects to maintain code quality and track changes.

### Steps

1. **Push a feature branch to GitHub** :

    ```bash
    git push origin feature-branch
    ```

2. **Create a pull request** :
 
    - Go to the repository on GitHub.
    - Click the **Pull Requests** tab -> **New Pull Request**.
    - Select ``feature-branch`` as the source and ``main`` as the target.
    - Add a **title, description, and assign reviewers**.
    - Click **"Create Pull Request"** to submit the PR.

3. **Review and merge the PR** :

    - Reviewers can connect, approve, or request changes.
    - Once approved, merge the PR using **"Merge Pull Request"**.
    - Delete the branch if no longer needed.


## Issues

### Overview

GitHub **issues** are used to track bugs, feature requestsm and improvements. They act as a task management system withing a repository.
Issues can be assigned to team members, labeled, and linked to PRs for better tracking and collaboration.

### Steps

1. **Creating a new issue** :

    - Navigate to the issues tab in the repository.
    - Click **"New Issue"**.
    - Provide a title, description, and attach relevant screenshots or files.
    - Assign the issue to a developer.
    - Click **"Submit New Issue"** to create it.

2. **Categorize issues using labels**:

    - Labels help classify issues (e.g., ``bug``, ``enhancement``, ``documentation`` etc.)
    - Apply labels from the **Labels** section in the issue tracker.

3. **Assign and track progress** :

    - Assign team members to specific issues.
    - Use **milestones** to track progress on multiple issues.


## GitHub Actions

### Overview

GitHub Actions automates workflows such as testing, building, and deploying applications. It allows continuous integration and continuous deployment (CI/CD) pipelines to be defined in code within the repository.

### Steps

1. **Create a GitHub Actions workflow file** :

    - Navigate to the Actions tab in the repository.

    - Click **"New Workflow"** or create a custom workflow file :


    ```yaml
    name: CI
    on: push
    jobs:
      test:
        runs-on: Ubuntu-latest
        steps:
            -uses: actions/checkout@v2
            -name: Install dependencies
             run: npm install
            -name: Run tests
             run: npm test
    ```

2. **Enable and monitor workflows** :

    - Workflows run automatically on push, pull requests or scheduled events.
    - View logs under **Actions** tab.
    - Monitor and troubleshoot failed workflows.


## Wiki

### Overview

GitHub **wiki** is a documentation tool that allows teams to create and maintain project guides and instructions.

### Steps

1. **Enable Wiki in a repository** :

    - Go to **Repository Settings** -> **Features** -> **Wiki**.
    - Enable the **Wiki** option.
    - Access the Wiki tab in the repository to create and edit pages.

2. **Create and edit Wiki pages** :

    - Use Markdown formatting for structured documentation.
    - Link related pages for better navigation.
    - Collaborate with team members to maintain the wiki.


## GitHub Projects

### Overview

GitHub projects is a Kanban-style task management tool that organizes issues, pull requests, and notes.

> **Note** : Kanban is a workflow management method that visualize work, limit work-in-progress, and optimize efficiency. In GitHub projects, tasks are represented as cards and can be moved between columns (e.g., ``To Do``, ``In Progress``, ``Done``) to represent different stages of a process. Tasks or items are represented as cards that move across the board as they progress through the workflow. In GitHub projects, Kanban-style boards help teams organize and track issues, pull requests and notes. 
