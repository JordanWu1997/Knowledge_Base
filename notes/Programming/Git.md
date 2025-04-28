- __Tags__: #Git
- __Vimwiki__: :Git:

# Git

A learning note for Git.

- **References**:
  - [7 Lesser-Known Git Commands and Tricks - GitConnected](https://levelup.gitconnected.com/7-lesser-known-git-commands-and-tricks-9915e9caeb70)
  - [Reddit: 7 Lesser-Known Git Commands and Tricks](https://www.reddit.com/r/commandline/comments/uy5quc/7_lesserknown_git_commands_and_tricks/)
  - [W3Schools Git Tutorial](https://www.w3schools.com/git/default.asp)
  - [Atlassian Git Tutorials](https://www.atlassian.com/git/tutorials/resetting-checking-out-and-reverting)
  - [Maxlist Git Merge vs. Rebase](https://www.maxlist.xyz/2020/05/02/git-merge-rebase/)
  - [YouTube Video on Git Concepts](https://www.youtube.com/watch?v=akD-DpolilE)

---

# Context

## Introduction to Git

Git is a **Version Control System (VCS)** that tracks changes in files and
coordinates work on those files among multiple people.

---

# Git Commands

## Configuration

- Initialize a new Git repository
  - `git init`
- Clone an existing repository
  - `git clone [repository_url]`
- Set global Git configuration (e.g., username, email)
  - `git config --global [key] [value]`

---

## Staging (Add/Restore)

- Add a file to the staging area
  - `git add FILE`
- Interactively choose chunks of a file to stage
  - `git add -p`
- Discard changes in a file (restore to last committed state)
  - `git restore FILE`

---

## Commit

- Create a commit with staged changes
  - `git commit`
- Modify the last commit (e.g., edit commit message)
  - `git commit --amend`
- Revert the last commit by creating a new commit that undoes it
  - `git revert HEAD^`
- Move HEAD one commit backward, unstaging changes
  - `git reset HEAD^`
- Display changes introduced by a commit
  - `git show`
- Save uncommitted changes temporarily (clean workspace)
  - `git stash`
- List all stashes
  - `git stash list`
- Reapply stashed changes
  - `git stash apply`
- Save changes to a new stash manually
  - `git stash push`
- Reapply and remove the most recent stash
  - `git stash pop`
- Remove a specific stash
  - `git stash drop <stash>`
- Clear all stashes
  - `git stash clear`

---

## Branching and Merging

- Show the current branch
  - `git branch`
- List all local and remote branches
  - `git branch -a`
- List remote branches only
  - `git branch -r`
- Delete a local branch
  - `git branch -d BRANCH`
- Switch to another branch
  - `git checkout BRANCH`
- Checkout a specific commit
  - `git checkout <COMMIT>`
- Checkout a specific file from a commit
  - `git checkout <COMMIT> <FILE>`
- Merge a branch into the current branch (recommended for public branches)
  - `git merge BRANCH`
- Merge a specific commit into current branch
  - `git merge <COMMIT>`
- Use a branch as the new base for the current branch (recommended for private branches)
  - `git rebase BRANCH`
- Interactive rebase (edit, reorder, squash commits)
  - `git rebase -i`
- Revert changes made by a specific commit
  - `git revert <COMMIT>`
- Apply changes from specific commits onto your current branch
  - `git cherry-pick <COMMIT-1> <COMMIT-2> ... <COMMIT-N>`

---

## Remote Repositories

- Add a remote repository
  - `git remote add [variable_name] [remote_server_url]`
- Add a remote server via SSH
  - `git remote add ssh-origin git@[server]:[path]`
- Change the URL of a remote repository
  - `git remote set-url origin git@[server]:[path]`
- Rename a remote repository
  - `git remote rename [old_name] [new_name]`
- Push the current branch commits to the remote
  - `git push`
- Push specific commit to a branch on the remote
  - `git push <REMOTE> HEAD:<BRANCH>`
- Fetch updates from a remote repository
  - `git fetch`
- Fetch and merge updates from a remote repository
  - `git pull`
- Fetch and rebase updates from a remote repository
  - `git pull --rebase`
- Pull a specific branch from a remote
  - `git pull <REMOTE> <BRANCH>`

---

## Viewing History

- Show the commit history
  - `git log`
- Show commit history with file changes
  - `git log --stat`
- Show all changes introduced by each commit
  - `git log -p`
- Show commit history in a summarized, one-line-per-commit format
  - `git log --oneline`
- Display commits grouped by author
  - `git shortlog`
- Show the working tree status
  - `git status`
- Show who last modified each line of a file
  - `git blame`
- List, create, or delete tags
  - `git tag`

---

## Inspecting Changes

- Find changes between commits, branches, or working tree
  - `git diff`
- Search for text in tracked files
  - `git grep`
- Parse and display revision (commit) information
  - `git rev-parse HEAD`

---

## Advanced and Miscellaneous

- Binary search to find the commit that introduced a bug
  - `git bisect`
- Add notes to commits
  - `git notes add -m "Your note"`
- Create an archive of files from a tree
  - `git archive --format=tar HEAD > archive.tar`
- Create a single-file backup (bundle) of repository
  - `git bundle create myrepo.bundle --all`
- Hard reset current branch to a specific commit (DANGEROUS: discards changes)
  - `git reset --hard <COMMIT>`
