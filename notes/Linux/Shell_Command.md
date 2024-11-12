# Shell Commands

- Reference
  - https://www.freecodecamp.org/news/the-linux-commands-handbook/
  - https://crontab-generator.org/
  - https://www.howtogeek.com/412055/37-important-linux-commands-you-should-know/
  - https://overthewire.org/wargames/bandit/bandit10.html
  - https://thevalleyofcode.com/linux/
  - Man (Linux system reference manuals)

# Context

## General

### `tar`

### `env`

- Run a program in a modified environment variable

env -i

### `printenv`

- Print all environment variables

### `grep`

### `find`

### `wc`

### `ls`

### `ln`

### `type`

### `printf`

- Format and print data

### `set`

### `exec`

### `expr`

### `eval`

### `read`

- Read user input and store it as `REPLY` variable

### `echo`

### `xarg`

### `locate`

### `updatedb`

### `readlink`

## Process Control

### `trap`

### `wait`

### `sleep`

### `service`

### `systemctl`

### `journalctl`

journalctl -u

### `time`

- Time program execution time and resources

### `times`

### `nice`

### `renice`

### `nohup`

### `kill`

kill -1
kill -2
kill -15
kill -9

### `killall`

### `jobs`

### `bg`

### `fg`

### `nohup`

### `pidof`

### `ps`

### `at`

### `atq`

### `atrm`

### `crontab`

- Maintain crontab files
- e.g. `crontab -e`
  - edit cron file

### `eval`

### `stat`

## File and Directory

### `mkdir`

- `-m`: chmod
- `-p`: create parent directory is there is not

### `file`

### `chown`

### `chattr`

### `lsattr`

### `umask`

### `basename`

- Get the last Strip directory and suffix from filenames

### `dirname`

- Strip filename and return directory name

## Administration

### `lsof`

-a # AND operator

lsof -i # TCP/UDP/:PORT/:PORT_START-PORT_END/@IP:PORT
lsof -u # user
lsof -p # PID
lsof +D # Recursive

### `id`

## Text Manipulation

### `cat`

### `tac`

### `watch`

watch -d

### `uniq`

- Report or omit repeated lines

### `tr`

tr 'A-Za-z' 'N-ZA-Mn-za-m'

### `bat`

### `sed`

sed -i

### `awk`

### `comm`

- Compare two sorted files line by line

### `column`

- Columnate lists

### `cut`

- Remove sections from each line of files

cut -c

### `diff`

- Compare files line by line

### `join`

- Join lines of two files on a common field

### `sort`

sort -n

## Kernel and Hardware

### `df`

df -T

### `du`

### `findmnt`

### `sysctl`

### `xxd`

xxd -r

### `base64`

### `modinfo`

### `modprobe`

### `lsmod`

### `lshw`

- List hardware information

```
lshw -short
```

### `lscpu`

### `lsscsi`

### `lsusb`

### `stat`

- Display file or file system status

### `dd`

### `fsck`

### `cfdisk`

### `dmesg`

### `init`

init 1 # single user mode: root login without password, can only be activated by adding "single" to kernel argument in grub
init 3 # multi-user mode: text user interface (TUI)
init 5 # graphic mode: graphic user interface (GUI)

### `runlevel`

## Network

### `mtr`

### `iftop`

### `airmon-ng`

### `nmap`

### `ping`

### `curl`

- Client URL

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

### `traceroute`

- Print the route packets trace to net work host

### `iwconfig`

### `iwlist`

### `nmcli`

### `dig`

- DNS lookup utility

### `host`

- DNS lookup utility

### `nslookup`

### `ip`

ip link
ip addr
ip addr add
ip route
ip route add

### `netstat`

netstat -tupln
netstat -ano

### `tcpdump`

tcp -nn -i wlp3s0

## Bluetooth

### `hciconfig`

### `hcitool`

## Miscellaneous

Note for some useful shell commands

### `tee`

- Read from standard input and write to standard output and files

### `pv`

### `ldd`

- List package dependency

### `test`

- Check if variable exists

### `w`

- List current logged in users

### `whatis`

- Explain commands

### `who`

### `whois`

- Search URL of database contains `.COM` `.NET` `.EDU` domain

### `whereis`

- Locate binary, source and manual page for __a command__

### `open`

- xdg-open

### `od`

### `chroot`

fuser
lsof
pidof

chage
sar
vmstat
pstree
