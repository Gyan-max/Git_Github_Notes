# Advanced Git and GitHub techniques

## Introduction

So far, we have covered the basics of Git and GitHub, including installation, setup, basic commands, branching, merging, remote repositories, collaboration workflows, and GitHub features. But 
Git offers powerful advanced features that can improve our workflow, fix mistakes, automate tasks, and enhance security. 


## Interactive Rebase - Editing Commit History

### What is Interactive Rebase?

Interactive rebase (``git rebase -i``) lets us rewrite commit history by combining, splitting, editing, and deleting commits. It provides a flexible way to clean up the commit history before sharing it with others.

It is helpful for:
- Editing commit messages
- Reordering commits
- Combining multiple commits (squash)
- Deleting unnecessary commits

### When to Use it?

- Cleaning up commit history before pushing to  GitHub
- Fixing commit messages for better clarity
Merging multiple small commits into one.

### How to Use it!

1. **Start Interactive rebase** 

    ```bash
    git rebase -i HEAD~3
    ```
> This open an editor showing the last 3 commits.

2. **Modify commits using these commands :**

Commands | Description
--- | ---
``pick`` | keep the commit as is
``reword`` | Use commit but edit the message
``edit`` | modify the commit content
``squash`` | Combine commit with the previous one
``fixup`` | Combine commit with the previous one, discarding the message
``drop`` | Remove commit

3. **Apply changes and continue**

After making changes, save and close the editor. If we selected ``edit`` or ``reword``, Git will pause at that commit. We can make changes, amend the commit, and continue the rebase.

```bash
git add .
git commit --amend
git rebase --continue
```

4. **Push the modified history**

```bash
git push origin <branch-name> --force
```

> **Note:** Be cautious while rewriting commit history, especially on shared branches. It can cause conflicts and confusion for collaborators.


## Stashing - Saving Work without committing

### What is Stashing?

Stashing lets you save **uncommitted changes** without committing them. It's useful when you :

- Need to switch branches but don't want to commit yet
- Want to temporarily save changes and come back later.

### How to Use it?

1. **Save uncommitted changes**

    ```bash
    git stash
    ```

2. **List saved stashes**

    ```bash
    git stash list
    ```

3. **Apply the most recent stash**

    ```bash
    git stash apply
    ```

4. **Apply a specific stash**

    ```bash
    git stash apply stash@{1}
    ```

5. **Remove stash after applying**

    ```bash
    git stash pop
    ```

6. **Clear all stashes**

    ```bash
    git stash clear
    ```

## Submodules - Adding another repo inside your repo

### What is a Submodule?

A **Submodule** is a Git repository inside another repository. It's useful when:

- You want to include another project as a dependency
- You need multiple repositories in a single project

### How to Use Submodules?

1. **Add a submodules**

    ```bash
    git submodule add <repo-link> submodule-folder
    ```

2. **Clone a repo with Submodules**

    ```bash
    git clone --recursive <repo-link>
    ```

3. **Update submodules**

    ```bash
    git submodule update --init --recursive
    ```

4. **Remove a submodule**

    ```bash
    git submodule deinit submodule-folder
    rm -rf submodule-folder
    git rm submodule-folder
    ```


## Git Hooks - Automate Git Tasks

### What are Git Hooks?

Git hooks let you run scripts automatically before or after Git commands.

### Example: Prevent Commits without Messages

1. **Create a pre-commit hook**
    
    ```bash
    nano .git /hooks/pre-commit
    ```

2. **Add this script**

    ```bash
    #!/bin/sh
    if ! git log -1 --pretty=%B | grep -q '[^[:space:]]; then
        echo "Commit message cannot be empty!"
        exit 1
    fi
    ```

3. **Make it executable

    ```bash
    chmod +x .git/hooks/pre-commt
    ```
> Now if someone tries to commit without a message, Git will stop them!


## Cherry-Picking - Selective Applying Commits

### What is Cherry-Picking?

Cherry-picking allows you to apply a single commit from one branch to another without merging the entire branch.

### How to use it?

1. **Find the commit hash**

    ```bash
    git log --online
    ```

2. **Apply the commit to another branch**

    ```bash
    git checkout target-branch
    git cherry-pick <commit-hash>
    ```

## Recovering Lost commits with Reflog

### What is Reflog?

Reflog helps recover lost commits by tracking every Git action.

### How to Recover a Lost Commit?

1. **View reflog history**

    ```bash
    git reflog
    ```

2. **Restore a lost commt**

    ```bash
    git checkout <commit-hash>
    ```

3. **Reset branch to a previous state**

    ```bash
    git reset --hard <commit-hash>
    ```

## Finding Bugs with Git Bisect

### What is Git Bisect?

Git bisect helps find the commit that introduced a big using a binary search.

### How to Use it?

1. **Start bisecting**

    ```bash
    git bisect start
    git bisect bad      # Mark the current commit as bad
    git bisect good <commit-hash>   # Mark an earlier commit as good
    ```

2. **Test the commit and make it as good/bas**

    ```bash
    git bisect good    # if the commit is working
    git bisect bad     # if the commit contains the bug
    ```

3. **Continue until Git finds the faulty commit**

4. **Exit bisect mode**

    ```bash
    git bisect reset
    ```


## GitHub Security Best Practices

- Enable Two-Factor Authentication (2FA)
- Use SSH keys instead of passwords
- Scan repositories for secrets

# Conclusion

Now you have a powerful Git toolkit for:
- Rewrite history (rebase)
- Saving work temporarily (stash)
- Managing multiple repositories (submodules)
- Automating tasks (hooks)
- Applying selective changes (cherry-pick)
- Recovering lost commits (reflog)
- Finding bugs quickly (bisect)
- Enhancing security
