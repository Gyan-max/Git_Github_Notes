# Basics Git Commands

## Introduction

Git provides a set of core commands that form the foundation of version contril workflows. This chapter covers the essential Git commands we will use regulary to manage our repositories and track changes. 

## Initializing a Repository

### Creating a New Repository

```
git init
```
This command creates a new Git repository in the current directory by setting up the necessary Git files in a hidden ``` .git``` folder.

### Cloning an Existing Repository

``` 
git clone <repository url>
```
This downloads a complete copy of a remote repository, including all files, branches, and history.

### Checking Status

```
git status
```
Shows the current status of the working directory.

* Which files have been modified
* Which changes are staged for the next commit
* Which files are not being tracked. 

## Tracking Files
### Adding Files to Staging Area

```
git add <filename>         # Add a specific file
git add .                  # Add all files in current directory to staging area
git add -A                 # Add all files in the repository
git add *.js               # Add all JavaScript files using wildcard
```

### Removing Files

```
git rm <filename>               # Remove files from working directory and staginf area
git rm --cached <filename>      # Keep file in working direcotry but remove from staging area
```

## Making Commits 

### Committing Staged Changes

```
git commit -m "Commit message" 
```

Creates a new commit with the changes currently in the staging area.

### Shortcut for Add and Commit

```
git commit -am  "Commit message"        # Add all tracked files and commit in one step
```


## Viewing Hostory


### Viewing Commit History

```
git log                     # Standard commit history
git log --oneline           # COndensed history, one commit per line
git log --graph             # Visual representation of branch history
git log -p                  # Show patches (Changes) for each commit
igt log --author="Name"     # Show commits by specific author


```
### Examining Specific Commits
```
git show <commit-hash>      #Show deatils of a specific commit

```



