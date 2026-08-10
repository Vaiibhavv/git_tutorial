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