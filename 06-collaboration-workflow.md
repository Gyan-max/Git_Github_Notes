# Collaboation Workflow

## Introduction

Collaborative workflows outline how team coordinate their efforts using Git and remote repositories. They enable efficient development, maintain code quality, and integrate contributions seamlessly. This chapter explores key workflows, with practical examples using GitHub.

## Understanding Collaborative Workflows

A collaborative workflow is a systematic process for managing code changes accross a team. It leverages Git's branching, merging, and remote features to ensure smooth collaboration and a unified project history. 

## Centralized Workflow

### Overview 

The centralized workflow involves all developers working on a single branch, typically ``main`` or ``master``. This workflow is common in small teams or projects where code changes are straightforward.

### Steps

**1. Sync with remote:**

``` bash
git pull origin main        # Fetch and merge latest changes
```

**2. Make changes and commit:**

``` bash
git add <file>                      # Stage changes
git commit -m "Commit message"      # Commit changes
```

**3. Push to remote:**

``` bash
git push origin main      # Push changes to remote
```

### Pros and Cons

- **Pros:**
    - Simple and easy to understand
    - Suitable for small teams or projects
    - Linear project history

- **Cons:**
    - Risk of conflicts with multiple developers
    - Limited flexibility for complex projects
    - No isolation for feature development.

**Example:**

``` bash
git pull origin main
git add styles.css
git commit -m "update styles"
git push origin main
```

### Handling COnflicts

If pushing fails due to remote updates:

1. Pull with rebase:

``` bash
git pull --rebase origin main
```

2. Resolve conflicts in files.
3. Continue rebase:

``` bash
git rebase --continue
```
4. Push Changes:

``` bash
git push origin main
```

## Feature Branch Workflow

### Overview

In the feature branch workflow, each task (feature, bugfix, etc.) gets its own branch. Changes are reviewed via pull requests before merging into ``main``, enhancing collaboration and review. 

**Steps:**

1. Create a new branch:

``` bash
git checkout -b feature-name        # Create and switch to new branch
```