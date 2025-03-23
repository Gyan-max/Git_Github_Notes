# Branching and Merging

## Introduction

Branching and merging are core Git concepts that enable parallel development and collaboration. Branches allow us to diverge from the main development line to work on features, fixes or experiments independently, while merging bring changes back together. 

## Understanding Branches

A branch in Git is simply a lightweight movable pointer to commit. The default branch is usually called ``main`` (formerly ``master``). When we create a new branch, we are creating a new pointer to the current commit. 

## Working with Branches

### Viewing Branches

```
git branch                  # List local branches
git branch -a               # List all branches (local and remote)
git branch -v               # View branches with last commit
git branch --merged         # List branches merged into current branch
git branch --no-merged      # List branches not merged into current branches

```

### Creating Branches

```
git branch <branch-name>                 # Create a new branch (without switching to it)
git checkout -b <branch-name>            # creating and switching to new branch (traditional)
git switch -c <branch-name>              # create and switch to new branch (modern)

```

### Switching Branches

```
git checkout <branch-name>          # Switch to an existing branch (traditional)
git switch <branch-name>            # switch to an existing branch (modern)

```

### Renaming Branches

```
git branch -m <old-name> <new-name>     # Rename a branch while not on that branch
git branch -m <new-name>                # Rename current branch
```

### Deletiing Branches

```
git branch -d <branch-name>       # Delete a branch (safe - prevents deletion if changes not merged)
git branch -D <branch-name>       # Force delete a branch (dangerous - discards unmerged changes)
```

## Merging Basics

Merging combines the changes from one branch into another.

### Fast-Forward Merges

When there are no new commits on the base branch since the feature branch was created, Git performs a ``fast-forward`` merge:

```
git checkout main       # switch to the target branch
git merge feature       # Merge the feature branch into main
```

### Three-Way Merges

When both branches have new commits, Git creates a merge commit: 

```
git checkout main       # Switch to the target branch
git merge feature       # Merge feature branch, creating a merge commit

```

## Handling Merge Conflicts

Conglicts occur when the same part of a file has been modified differently in both branches. 

### Resolving Conflicts

1. Git will mark the conflicted areas in files
2. Manually edit the files to resolve conflicts.
3. Add the resolved files: ``git add <resolved-file>``
4. Complete the merge: ``git commit``



