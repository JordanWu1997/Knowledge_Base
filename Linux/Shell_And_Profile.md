# Shell_And_Profile

- References
  - http://howtolamp.com/articles/difference-between-login-and-non-login-shell/
  - https://ithelp.ithome.com.tw/articles/10232226
  - https://tecadmin.net/difference-between-login-and-non-login-shell/
  - https://einverne.github.io/post/2017/03/bashrc-profile.html

# Table of Contents

- [Shell_And_Profile](#shell_and_profile)
  - [Table of Contents](#table-of-contents)
  - [Context](#context)
    - [Login shell and non-login shell](#login-shell-and-non-login-shell)
    - [Interactive shell and non-interactive shell](#interactive-shell-and-non-interactive-shell)
    - [Shell profile](#shell-profile)

Created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc)

# Context

## Login shell and non-login shell

- Login shell
  - Shell activated after successful login, including user switching
- Non-login shell
  - Shell started by a program without login. For example: `bash` command in terminal
- In bash, check login-shell or non-login shell you are including
  - Command: `echo $0`
  - Output:
    - `bash`: login-shell
    - `-bash`: non-login-shell

## Interactive shell and non-interactive shell

- Interactive shell
  - User can use command to interact with shell. For example: shell CLI in terminal
- Non-interactive shell
  - Run script to interact with shell. For example: `bash -C script` command in terminal

## Shell profile

- Shell profile
  - Configuration file that stores shell environment variables, function, and etc.
- Sequence of reading shell profile (here use bash as example)
  - Login-shell
    1. /etc/profile
    1. /etc/profile.d/
    1. First of the following
       1. $HOME/.bash_profile
       1. $HOME/.bash_login
       1. $HOME/.profile
    1. $HOME/.bashrc
    1. /etc/bashrc
  - Non-login-shell
    1. $HOME/.bashrc
    1. /etc/bashrc
    1. /etc/profile.d/
