## Git commands and meaning beyond basics

1. Git does not tracked the empty directories. If you want to track an empty directory, you can create a `.gitkeep` file inside it.

2. To remove a file from the staging area, you can use the command `git reset <file>`.

3. What is head `1. In Git, `HEAD` refers to the current commit your working directory is based on. It is a pointer that indicates the latest commit in the currently checked-out branch. When you make new commits, `HEAD` moves forward to point to the new commit.
, in simple- when you checkout a branch, means if you create new branch from current brach, 
you usually checkout the from the latest commit of the current branch. So, `HEAD` will point to that latest commit of the current branch.

4. git switch is a command that allows you to switch between branches in your Git repository. It is a more user-friendly alternative to the older `git checkout` command. The `git switch` command is specifically designed for switching branches, making it easier to understand and use.
- eg. `git switch <branch-name>`
- To create a new branch and switch to it in one command, you can use the `-c` option:
  - `git switch -c <new-branch-name>`

5. To merge a feature branch into the main branch, you can use the command `git merge <feature-branch>` -m "Merge message". This will combine the changes from the feature branch into the main branch.

* Two Types of Merge
  - Fast-forward merge
  - Three-way merge

  - Fast-forward merge occurs when the main branch has not diverged from the feature branch or main branch doesn't have any commits after the divergence. In this case, Git simply moves the pointer of the main branch forward to the latest commit of the feature branch.

  - Three-way merge occurs when the main branch has diverged from the feature branch, meaning both branches have new commits since they split. In this case, Git creates a new commit that combines the changes from both branches. 

  Or Non fast forward merge occurs when the main branch has diverged from the feature branch, meaning both branches have new commits since they split. In this case, Git creates a new commit that combines the changes from both branches.

## Merge Conflicts
- Merge conflicts occur when Git is unable to automatically resolve differences between two branches during a merge. This typically happens when changes have been made to the same lines of code in both branches. When a merge conflict occurs, Git will mark the conflicting files and require manual intervention to resolve the conflicts.

- While resoling the conflicts, you can use the command `git status` to see which files have conflicts. You can then open the conflicting files in a text editor and look for the conflict markers (<<<<<<<, =======, >>>>>>>) to identify the conflicting changes. After resolving the conflicts, you can add the resolved files to the staging area using `git add <file>`, and then commit the changes with `git commit`.

## What is a rebase?

A rebase is a Git command that allows you to move or "replay" commits from one branch to another. It is often used to integrate changes from one branch into another, but instead of creating a new merge commit, it applies the changes as if they were made on the target branch.

For example, if you have a feature branch that has several commits, and you want to integrate those changes into the main branch, you can use `git rebase` to apply the feature branch commits onto the main branch.

### How to use rebase

1. Switch to the feature branch: `git switch <feature-branch>`
2. Rebase the feature branch onto the main branch: `git rebase <main-branch>`

This will replay or move all the commits from the feature branch on top of the main branch.

In simple words- when we are working on a feature branch and want to integrate the latest changes from the main branch, we can use rebase to apply our feature branch commits on top of the main branch. This helps to keep the commit history linear and clean.

- Eg. Suppose i have a feature branch called a feature-rebase, i have made or add some files in feature brahces, and commited, 
meanwhile some other changes have been made in the main branch, and i want to integrate those changes into my feature branch, so i can use rebase to apply my feature branch commits on top of the main branch.

### Advantages of rebase

- Keeps the commit history linear and clean.
- Avoids unnecessary merge commits.
- Makes it easier to understand the project's history.

### Disadvantages of rebase

- Can be dangerous if you have already pushed your changes to a remote repository.
- Makes it harder to track which changes were made in which commit.

## How to time travel in git?

- Git allows you to "time travel" by checking out previous commits in your repository's history. This can be useful for reviewing past changes, debugging issues, or reverting to a previous state of the codebase.

- to time travel in Git, you can use the `git reset` command to move the `HEAD` pointer to a specific commit. You can find the commit hash of the desired commit using `git reflog`, and then use `git reset --hard <commit-hash>` to reset your working directory and staging area to that commit.

- eg. Suppose in current branch i have made some changes and commited, but i dont want keep those changes, in this scenario  
to go back to the previous commit, so i can use `git reset --hard HEAD~1` to reset my working directory and staging area to the previous commit.