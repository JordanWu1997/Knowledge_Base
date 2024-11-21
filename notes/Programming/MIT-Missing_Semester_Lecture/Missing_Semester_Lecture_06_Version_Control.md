# Missing Semester - Lecture 06 - Version Control (git)

- Reference
  - [Course_youtube_link](https://www.youtube.com/watch?v=2sjqTHE0zok)
  - [Course_webpage_resources](https://missing.csail.mit.edu/2020/version-control/)

# Table of Contents

- [Missing Semester - Lecture 06 - Version Control (git)](#missing-semester---lecture-06---version-control-git)
  - [Table of Contents](#table-of-contents)
  - [Context](#context)
    - [What is Git](#what-is-git)
    - [Terminology](#terminology)
    - [Git on local machine](#git-on-local-machine)
    - [Git on remote repository (Github)](#git-on-remote-repository-github)
    - [Miscellaneous](#miscellaneous)

Created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc)

# Context

## What is Git

- Tools that create a series of snapshots and branches for development

## Terminology

- Tree (folder)
- Blob (file)
- Commit (snapshot)
  - Object that git used to store version information
- Secure Hash Algorithm 1 (SHA-1)
  - Algorithm that turn input into long string (max 160 characters)

## Git on local machine

- Initialization

  ```bash
  #_Initialize directory to root of git (on local machine)
  git init
  ```

- Basic manipulation

  ```bash
  #_Help for git command (like man in UNIX-like system)
  git help <command>

  #_Add file to stage area
  git add <file>

  #_Add file to stage area interactively
  git add -p

  #_Commit to git repository (create a snapshot)
  git commit

  #_Find information for repository objects (including tree, author, commit message and etc.)
  git cat-file -p <git_commit_index (SHA-1)>

  #_Print commit history in tree graph
  git log --all --graph --decorate --oneline
  ```

- Branch manipulation of git

  ```bash
  #_Point repository to certain commit (snapshot)
  #_WARNING: This operation will remove all local changes (not-committed changes)
  git checkout <git_commit_index (SHA-1)>

  #_Remove all changes to certain file (go back to last commit)
  git checkout <filename>

  #_Check difference between nodes (commits)
  git diff <git_commit_1_index (SHA-1)> <git_commit_2_index (SHA-1)> (filename)

  #_Show staged commits on current branch
  git diff --cached

  #_Create new branch from current one
  git branch <branch_name>

  #_Change to branch
  git checkout <branch_name>

  #_Merge branches
  git merge <target_branch_name>

  #_Give up current merge
  git merge --abort

  #_Continue previous unsuccessful merge
  git merge --continue
  ```

## Git on remote repository (Github)

- Manipulation of remote git (Github)

  ```bash
  #_Add current local directory to remote github repository (HTTPS)
  git remote add origin <url_of_github_repository>

  #_Add current local directory to remote github repository (SSH)
  git remote add origin git@github.com:<Username>/<Project>.git

  #_Change current local directory to remote github repository (HTTPS)
  git remote set-url origin <url_of_github_repository>

  #_Change current local directory to remote github repository (SSH)
  git remote set-url origin git@github.com:<Username>/<Project>.git

  #_Upload local commits to remote repository
  git push

  #_Find remote commits but not merged into one
  git fetch

  #_Find remote commits and merged into one
  git pull

  #_Clone remote repository to local machine with all commit history
  git clone <url_of_github_repository>j

  #_Clone remote repository to local machine without commit history
  git clone --shallow <url_of_github_repository>

  #_Find commit information of file line by line
  git blame

  #_Use binary search to find the commit that introduced a bug
  git bisect
  ```

## Miscellaneous

- Text file that store all files that git ignores (.gitignore)

  ```text
  #_Local_Git_Repository/.gitignore
  /file_or_directory_to_ignore_by_git
  ```
