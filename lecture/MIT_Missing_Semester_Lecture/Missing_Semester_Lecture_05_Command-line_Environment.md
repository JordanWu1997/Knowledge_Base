# Missing Semester - Lecture 05 - Command-line Environment
- [Course youtube link](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbW1IVEtzaFZmRVk3T3lrMWg1bGt2UjFnUGtld3xBQ3Jtc0ttWTM0a3VieTQwOWhIUWx3bHB2ME42aXpRdU9HNkd6Ml9ScEp5QkZJQU5HVGhOQ1NXZjdJNHphREsxYmRHQS1rVE9ZMVdhaEkzdVlWMjNMUldpWVFRSUtkak1Nd1RLMWxKbzRYY29ZQmRhSmcyb3Rxbw&q=https%3A%2F%2Fmissing.csail.mit.edu%2F2020%2Fcommand-line%3F)
- [Course webpage resources](https://missing.csail.mit.edu/2020/command-line/)

## Table of content
* [Missing Semester - Lecture 05 - Command-line Environment](#missing-semester---lecture-05---command-line-environment)
   * [Table of content](#table-of-content)
   * [Context](#context)
      * [Job Control Command](#job-control-command)
      * [Terminal Multiplexers (TMUX)](#terminal-multiplexers-tmux)
      * [Dotfiles](#dotfiles)
      * [Remote Machine](#remote-machine)

Created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc)

## Context

### Job Control Command
- sleep
    - Wait for given time
    ```bash
    sleep 1          # Sleep 1000 s
    ```
- signal
    - SIGHUP
        - Hang up process to background
    - SIGINT
    -   - Interrupt process (same as Ctrl+c in command line)
    - SIGQUIT
        - Quit process
    - SIGTERM
        - Terminate process
- kill
    - Send signal to process
   ```bash
   kill -HUP %1      # HUP  JOB %1 in background
   kill -KILL %1     # KILL JOB %1
   ```
- jobs
    - Show all background processes
- bg/fg
    - Bring process in jobs background/foreground
    ```bash
    bg %1            # Continue JOB %1 running in background
    fg %1            # Bring background JOB %1 to foreground
    ```

### Terminal Multiplexers (TMUX)
- TMUX component
    - Session
        - TMUX Process
    - Window
        - Workspace for each session
    - Pane
        - Split for each window
- TMUX command
    - In TMUX, use PREFIX + BINDKEY to execute TMUX command
    - Default prefix is Ctrl+b (I prefer to map prefix to Ctrl+space for ergonomic)
    - Session command
        ```bash
        # In terminal
        tmux new -t NEW_NAME        # Generate new session
        tmux ls                     # Show all exist sessions
        tmux attach -t NAME         # Attach to exist sessions
        # Inside TMUX
        PREFIX+d                    # Detach current session
        PREFIX+$                    # Rename current session
        ```
    - Window command
        ```bash
        # Inside TMUX
        PREFIX+c                    # Create new window
        PREFIX+NUMBER               # Move to window#
        PREFIX+,                    # Rename current window
        PREFIX+x                    # Close current window
        ```
    - Pane command
        ```bash
        # Inside TMUX
        PREFIX+%                    # Split current pane horizontally
        PREFIX+"                    # Split Current pane vertically
        ```
    - Miscellaneous command
        ```bash
        PREFIX+z                    # Maximize current pane
        PREFIX+alt+[1-5]            # Change current window layout
        PREFIX+?                    # Show all TMUX commands
        ```

### Dotfiles
System, shell, application configuration files (file starts with dot .)
- dotfile file tree
    ```bash
    # In user home directory ($HOME)
    .
    ├── .bash_aliases -> /home/jordankhwu/Desktop/Dotfiles/Fedora_Dotfiles/bash_aliases
    ├── .bashrc -> /home/jordankhwu/Desktop/Dotfiles/Fedora_Dotfiles/bashrc
    ├── .config
    ├── .local
    ├── .profile -> /home/jordankhwu/Desktop/Dotfiles/Fedora_Dotfiles/profile
    ├── .tmux
    ├── .tmux.conf -> /home/jordankhwu/Desktop/Vim_Tmux_Config/tmux.conf
    └── .Xresources -> /home/jordankhwu/Desktop/I3_Sway_Config/dotfile/Xresources
    ```
- symlink
    - Generate link point to file/directory
        ```bash
        # Generate link pointing to target
        ln -s TARGET_TO_LINK LINK_NAME
        ```
- dotfile for bash shell
    - alias
        - Shortcut for long command
        ```bash
        # In terminal or $HOME/.bashrc file
        alias mv="mv -i"
        ```

### Remote Machine
- SSH (connect to remote machine)
    ```
    # Connect to remote machine as user
    ssh users@remote_machine_ip
    ```
    - SSH key
        - Public key
            - Key to store in remote machine ~/.ssh/known_hosts
        - Private Key
            - Key to keep safe in local machine
        - ssh-keygen
            - Generate public and private ssh keypair
    - scp
        - Copy file from remote/local machine through SSH
    - rsync
        - Sync file from remote/local machine through SSH
