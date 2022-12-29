# Git
- https://levelup.gitconnected.com/7-lesser-known-git-commands-and-tricks-9915e9caeb70
- https://www.reddit.com/r/commandline/comments/uy5quc/7_lesserknown_git_commands_and_tricks/
- https://www.w3schools.com/git/default.asp
- https://www.atlassian.com/git/tutorials/resetting-checking-out-and-reverting
- https://www.maxlist.xyz/2020/05/02/git-merge-rebase/

# Context

## Introduction to Git
Version Control System (VCS)

## Stage (Add)
- Add file FILE to stage
    - `git add FILE`
- Add files to stage interactively
    - `git add -p`
- Restore file FILE change
    - `git restore FILE`

## Commit
- Commit files on stage to git
    - `git commit`
- Modify commit message
    - `git commit --amend`
- Create a new commit to cancel last commit (move HEAD forward)
    - `git revert HEAD^`
- Reset to last commit (move HEAD backward)
    - `git reset HEAD^`
- Show committed content
    - `git show`

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

## Branch
- Show current branch
    - `git branch`
- List all branchess
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
