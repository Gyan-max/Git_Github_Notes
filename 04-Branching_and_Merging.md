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

### Conflict Markers

Conflict markers in the file look like this:

```
<<<<<<< HEAD
changes from the branch you're merging into
========
changes from the branch you're merging from
>>>>>> feature-branch

```

### Using Merge Tools

```
git mergetool       # Launch configured visual merge tool

```

### Aborting a Merge

```
git merge --abort   # CAncle the merge and return the pre-merge state

```

## Advanced Merging Strategies

### Squash Merging

Condenses all commits from a branch into a single commit:

```
git merge --squash feature      # combines all changes without merging histories
git commit -m "Implement feature X"

```
### Rebase and Merge

Creates a linear history (covered in more detail in the Advanced Techniques chapter):

```
git checkout feature
git rebase main
git checkout main
git merge feature       # will be a fash-forward merge

```

## Branching Strategies

### Feature Branch Workflow
1. Create a branch from each feature/bug: ``git checkout -b feature-x``
2. Work on the branch, making regular commits
3. When complete, merge back to main:

```
git checkout main
git merge feature-x
```

### Git FLow


A more structured workflow with multiple branch types:

* ``main`` - production-ready code
* ``develop`` - integration branch
* ``feature/*`` - for new features
* ``release/*`` - preparation for releases
* ``hotfix/*`` - urgent fixes for production 

### GitHub Flow

A simpler workflow

* Branch from ``main``
* Add commits
* open Pull Requests
* Review and discuss
* Merge to ``main`` and deploy

## Branch Visualization

To visualize our branch structure:

```
git log --graph --oneline --all --decorate

```

Or use GUI tools like **Sourcetree**, **GitKraken**, or **GitHub Desktop** for a more visual representation.

### Best Practices

1. Use descriptive branch names (``feature/user-authentication``, ``bugfix/login-error`` )
2. Keep branches focused on single features or fixes
3. Regularly sync with the base branch to minimize conflicts
4. Delete branches after merging to keep repository clean
5. Consider using pull/merge requests for code review
6. Testing before merging

## Next step

Now that we understand branching and merging , proceed to [Remote Repositories](05-Remote-Repositories.md) to learn how to collaborate with others using GitHub. 
