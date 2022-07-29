# Shell Commands
- Reference
    - https://www.freecodecamp.org/news/the-linux-commands-handbook/
    - https://crontab-generator.org/
    - https://www.howtogeek.com/412055/37-important-linux-commands-you-should-know/
    - https://overthewire.org/wargames/bandit/bandit10.html
    - Man (Linux system reference manuals)

Table of Contents
=================

* [Shell Commands](#shell-commands)
* [Table of Contents](#table-of-contents)
* [Context](#context)
   * [Useful commands](#useful-commands)
      * [basename](#basename)
      * [dirname](#dirname)
      * [column](#column)
      * [comm](#comm)
      * [crontab](#crontab)
      * [cut](#cut)
      * [diff](#diff)
      * [dig](#dig)
      * [env](#env)
      * [host](#host)
      * [join](#join)
      * [ldd](#ldd)
      * [lshw](#lshw)
      * [printenv](#printenv)
      * [printf](#printf)
      * [read](#read)
      * [stat](#stat)
      * [tee](#tee)
      * [test](#test)
      * [time](#time)
      * [traceroute](#traceroute)
      * [uniq](#uniq)
      * [w](#w)
      * [whatis](#whatis)
      * [whois](#whois)
      * [whereis](#whereis)

Created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc)

# Context

## Useful commands
Note for some useful shell commands

### `basename`
- Strip directory and suffix from filenames

### `dirname`
- Strip filename and return directory name

### `column`
- Columnate lists

### `comm`
- Compare two sorted files line by line

### `crontab`
- Maintain crontab files
- e.g. ```crontab -e```
    - edit cron file

### `cut`
- Remove sections from each line of files

### `diff`
- Compare files line by line

### `dig`
- DNS lookup utility

### `env`
- Run a program in a modified environment variable

### `host`
- DNS lookup utility

### `join`
- Join lines of two files on a common field

### `ldd`
- List package dependency

### `lshw`
- List hardware information
    ```
    lshw -short
    ```

### `printenv`
- Print all environment variables

### `printf`
- Format and print data

### `read`
- Read user input

### `stat`
- Display file or file system status

### `tee`
- Read from standard input and write to standard output and files

### `test`
- Check if variable exists

### `time`
- Time program execution time and resources

### `traceroute`
- Print the route packets trace to net work host

### `uniq`
- Report or omit repeated lines

### `w`
- List current logged in users

### `wget`
- Get remote file with new name
    ```
    wget -O
    ```
- Save file to different directory
    ```
    wget -P
    ```
- Continue previous downloading
    ```
    wget -c
    ```
- Download file with input text list
    ```
    wget -i
    ```

### `whatis`
- Explain commands

### `whois`
- Search URL of database contains `.COM` `.NET` `.EDU` domain

### `whereis`
- Locate binary, source and manual page for __a command__

### `nice`

### `renice`

### `kill`

kill -1
kill -2
kill -15
kill -9

### `at`

### `set`

### `nmap`

### `exec`

### `eval`

### `trap`

### `wait`

### `type`

### `times`

### `dd`

### `fsck`

### `service`

### `systemctl`

### `iwconfig`

### `iwlist`

### `nmcli`

### `airmon-ng`

### `hciconfig`

### `hcitool`

### `hcitool`

### `sysctl`

### `lsmod`

### `modinfo`

### `modprobe`

### `xxd`
xxd -r

### `base64`

### `tr`
tr 'A-Za-z' 'N-ZA-Mn-za-m'
