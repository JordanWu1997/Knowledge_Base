# Linux Journey - Grasshopper
- Reference
    - https://linuxjourney.com/
    - https://linuxjourney.com/lesson/monitor-processes-ps-command
    - https://linuxjourney.com/lesson/file-permissions
    - https://linuxjourney.com/lesson/users-and-groups
    - https://www.geeksforgeeks.org/real-effective-and-saved-userid-in-linux/

Table of Contents
=================

* [Linux Journey - Grasshopper](#linux-journey---grasshopper)
   * [User Management](#user-management)
   * [Permissions](#permissions)
   * [Process](#process)
      * [Terminals in Linux System](#terminals-in-linux-system)
      * [requently used command](#requently-used-command)

Created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc)

# Context

## User Management
- ID
    - `UID`: User ID
    - `GID`: Group ID
- User management
    - `useradd`: Add user
    - `userdel`: Delete user
    - `passwd`: Change user password
- User/Password configuration
    - `/etc/passwd`: Configuration file in format
        - `username:password:UID:GID:comment:userhome:usershell`
    - `/etc/shadow`: Configuration file in format
        - `username:password:min_age:max_age:warning_period:inactivity_period:expiration_date:reversed_field`
- Group configuration
    - `/etc/group`: Configuration file in format
        - `groupname:grouppassword:GID:userlist`

## Permissions
- Frequently used command
    - `ls -l`: List file/directory in long format (including name, group, permissions and etc.)
    - `chmod`: Change file Mode bit (user/group/others permission)
    - `chwon`: Change owner of file
    - `chgrp`: Change group of file
    - `umask`: Default file permission
- Permission mode bit
    - `r`: readable
    - `w`: writable
    - `x`: executable
    - `-`: empty
    - `s`: SUID/SGID
        - SUID: Set User ID (symbolic: s, numerical: 4)
        - SGID: Set Group ID (symbolic: s, numerical: 2)
    - `t`: sticky bit
- Mode bit examples:
    - `d | rwx | r-x | r-x`: directory
    - `- | rwx | r-x | r-x`: regular file
    - `- | rws | r-x | r-x`: file that is permitted to read/write/execute as user
    - `- | rwS | r-x | r-x`: file that is permitted read/write as user (not executable)
    - `d | rwx | rwx | rwx | t`: file that everyone can add/write/modify in directory, but only root can delete the directory
- Type of UID (User ID)
    - Effective user ID: user ID used in process
    - Real user ID
    - Saved user ID

## Process
Kernel manages all processes on linux system, with information of status, resources, process owner, signal and etc.

### Terminals in Linux System
- `TTY`: controlling terminal
    - TTY1-TTY7
        - `Ctrl`+`Alt`+`[1~6]`
- `PTS`: Pseudo terminal devices
    - TTY label for PTS: `?`

### requently used command
- `ps`: Show active processes, contains
    - `PID`: Process ID
    - `TTY`: Terminal
    - `STAT`: Process status code
    - `TIME`: Total CPU usage time
    - `CMD`: Command
- `ps aux`: Show detailed all processes, contains
    - `USER`: Effective user
    - `PID`: Process ID
    - `VSZ`: Virtual memory usage
    - `RSS`: Resident set size (non-swapped physical memory)
    - `START`: Start time of the process
- `ps l`: BSD long format, contains
    - `PPID`: Parent Process ID
