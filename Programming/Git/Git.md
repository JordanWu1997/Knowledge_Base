Tags: #Git
Vimwiki: :Git:

# Git

Note for git learning

- Reference
  - https://levelup.gitconnected.com/7-lesser-known-git-commands-and-tricks-9915e9caeb70
  - https://www.reddit.com/r/commandline/comments/uy5quc/7_lesserknown_git_commands_and_tricks/
  - https://www.w3schools.com/git/default.asp
  - https://www.atlassian.com/git/tutorials/resetting-checking-out-and-reverting
  - https://www.maxlist.xyz/2020/05/02/git-merge-rebase/
  - https://www.youtube.com/watch?v=akD-DpolilE

# Context

## Introduction to Git

Version Control System (VCS)

## Config

- `git init`
- `git clone`
- `git config --global`

## Stage (Add)

- Add file FILE to stage
  - `git add FILE`
- Add files to stage interactively
  - `git add -p`
- Restore file FILE change
  - `git restore FILE`

## Commit

- Commit files on stage to git (snapshot)
  - `git commit`
- Modify commit message
  - `git commit --amend`
- Create a new commit to cancel last commit (move HEAD forward)
  - `git revert HEAD^`
- Reset to last commit (move HEAD backward)
  - `git reset HEAD^`
- Show committed content
  - `git show`
- Save change made without making commit (to clean your stage for other works)
  - `git stash`
- List saved changes saved by stash
  - `git stash list`
- Apply saved changes saved by stash
  - `git stash apply`

## Remote

- Add remote server
  - `git remote add [variable_name] [remote_server]`
  - `git remote add ssh-origin git@`
- Set URL for existing remote server
  - `git remote set-url origin git@`
- Rename remote server
  - `git remote rename`

## Log

- Show commit message only

  - `git shortlog`

- Show hash and commit message in one line

  - `git log --online`

- Show log of commits

  - `git log --stat`

- Show all changes of commits

  - `git log -p`

- `git status`

- `git blame`

- `git tag`

## Branch

- Show current branch
  - `git branch`
- List all branches
  - `git branch -a`
- Show remote branches
  - `git branch -r`
- Delete branch BRANCH
  - `git branch -d BRANCH`
- Change from current branch to BRANCH
  - `git checkout BRANCH`
- Push commit on current branch to remote server
  - `git push`
- Update commits on remote server to local
  - `git fetch`
- Merge current branch with branch BRANCH (RECOMMENDED for public branch)
  - `git merge BRANCH`
- Use branch BRANCH as base of current branch (RECOMMENDED for private branch)
  - `git rebase BRANCH`
- Combination of `git fetch` and `git merge`
  - `git pull`
- Combination of `git fetch` and `git rebase`
  - `git pull --rebase`

## Misc

- `git bisect`
- `git diff`
- `git grep`
- `git notes add -m "Test note"`
- `git rev-parse HEAD`
- `git archive`
- `git bundle`

git checkout <COMMIT>
git reset --hard <COMMIT>
git merge <COMMIT>
git push <REMOTE> HEAD:<BRANCH>
git pull <REMOTE> <BRANCH>

git rebase -i

git reset --hard <COMMIT>
git cherry-pick <COMMIT-1> <COMMIT-2> <COMMIT-3> ...  <COMMIT-N>

git checkout <COMMIT> <FILE>
git revert <COMMIT>

- Revert the changes of the specified commits

git stash push
git stash pop
git stash apply
git stash clear
git stash drop <stash>
