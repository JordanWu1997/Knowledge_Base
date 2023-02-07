# SELinux (Secure Enhanced Linux)
- https://www.youtube.com/watch?v=YcWMoIkpyp0 (Chinese)
- https://www.youtube.com/watch?v=fibllWD1_4s&t=26s
- https://www.youtube.com/watch?v=S0bCoVWqo-o

## What is SELinux
- Linux security strategy developed by NSA
- SElinux is kernel-level application, which means the modification of SELinux needs to reboot
- SELinux is enabled as default in Fedora/CentOS/RHEL


## SELinux Component

Domain
- to constrain process
- ps -Z: list domain of processes

Context
- to constrain system resource (e.g. files, sockets)
- ls -Z: list context of files

SELinux sets strategy for domains for the access of contexts
- Default strategy in CentOS/RHEL: target strategy
    - Only target processes are constrained by SELinux, other processes are not affected
    - Target strategy only affect network application process (~200)
        - Examples: `dhcpd`, `httpd`, `mysqld`, and etc.

SELinux Working mode

enforcing: Operation that violates strategy will be stopped
permissive: Operation that violates strategy will not be stopped but warning message is generated
disable: Disable SELinux

`/etc/sysconfig/selinux`

getenforce: Check SELinux working status
setenforce: Set SELinux working status

setenforce 1: enforcing
setenforce 0: permissive

unconfined_u:object_r:user_home_t:s0          SELinux.md
    User    :  Role  :   Type    : MLS, MCS



Output of `ls -Z SELinux.md`
| User         | Role     | Type        | MLS, MCS | Filename   |
| :----------: | :------: | :---------: | :------: | :--------: |
| unconfined_u | object_r | user_home_t | s0       | SELinux.md |


Some operation will accidentally change context of file and cause problem for file access
restorecon -R -v /var/www :restore default context of file in directory
chcon --refence=/etc/named.conf.orig /etc/named.conf: change context of file
ausearch

getsebool -a
sestatus -vb
setsebool
