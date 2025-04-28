# Linux Logs and Journaling

A learning note for system logs and journal management in Linux.

- Resources
  - https://chatgpt.com
  - https://www.youtube.com/watch?v=6uP_f_z3CbM

---

# Basic Log Files and Commands

| Command/File        | Purpose                                                              | Notes                                                                 |
| :------------------ | :------------------------------------------------------------------- | :-------------------------------------------------------------------- |
| `/var/log/boot.log` | Shows messages from the boot process                                 | Managed by `systemd` or `init` scripts depending on the distribution. |
| `/var/log/wtmp`     | Binary log of all login/logout activities                            | Viewed with `last` command.                                           |
| `/var/log/btmp`     | Binary log of failed login attempts                                  | Viewed with `lastb` command (requires root).                          |
| `last`              | Shows successful login history (reads `/var/log/wtmp`)               | Example: `last -adF`                                                  |
| `lastb`             | Shows failed login attempts (reads `/var/log/btmp`)                  | Must be run with root privileges.                                     |
| `dmesg`             | Prints kernel ring buffer messages (boot-time messages, driver logs) | Useful for debugging hardware/kernel issues.                          |

---

# Journal System (systemd-journald)

`systemd-journald` is a logging service for systemd-based systems. It collects and stores logs from:

- The kernel
- Initrd
- Services (units)
- Applications

### Key Commands

| Command                                 | Purpose                                                                    |
| :-------------------------------------- | :------------------------------------------------------------------------- |
| `journalctl`                            | View all collected journal entries.                                        |
| `journalctl -u SERVICE_NAME`            | Show logs related to a specific service (unit), e.g., `journalctl -u sshd` |
| `journalctl -b`                         | Show logs from the current boot.                                           |
| `journalctl --since "YYYY-MM-DD HH:MM"` | Show logs starting from a specific time.                                   |
| `journalctl --vacuum-time=7d`           | Remove logs older than 7 days.                                             |
| `journalctl --disk-usage`               | Check the disk space used by journal logs.                                 |

### Important Journal Files/Paths

| Path                         | Description                                                                   |
| :--------------------------- | :---------------------------------------------------------------------------- |
| `/var/log/journal/`          | Persistent storage location for journal logs if enabled.                      |
| `/run/log/journal/`          | Volatile storage (cleared on reboot) if persistent storage is not configured. |
| `/etc/systemd/journald.conf` | Configuration file for journald behavior.                                     |

**Note:**
To enable persistent journaling, ensure `/var/log/journal/` exists:

```bash
sudo mkdir -p /var/log/journal
sudo systemctl restart systemd-jjournald
```

---

# Syslog and rsyslog

Before `systemd`, logging was usually handled via `syslog` daemons like `rsyslog` or `syslog-ng`.

### Syslog Basics

- Syslog is a standard protocol (RFC 5424) for sending log messages in an IP network.
- Programs send log entries to `/dev/log` socket, and syslog daemon writes them to files based on severity and facility.

### Rsyslog

- `rsyslog` is the default syslog daemon in many distributions.
- It provides advanced features like:
  - Filtering
  - Message forwarding (TCP/UDP)
  - Writing logs to different files

### Important Syslog/rsyslog Files

| Path                    | Description                                 |
| :---------------------- | :------------------------------------------ |
| `/etc/rsyslog.conf`     | Main configuration file for rsyslog daemon. |
| `/etc/rsyslog.d/*.conf` | Additional rsyslog configuration snippets.  |
| `/var/log/syslog`       | Main system log (Debian/Ubuntu).            |
| `/var/log/messages`     | Main system log (RHEL/CentOS/Fedora).       |
| `/var/log/auth.log`     | Authentication logs (Debian/Ubuntu).        |
| `/var/log/secure`       | Authentication logs (RHEL/CentOS/Fedora).   |

### Commands

- Restart rsyslog:

  ```bash
  sudo systemctl restart rsyslog
  ```

- Check rsyslog status:

  ```bash
  sudo systemctl status rsyslog
  ```

---

# Log Management with logrotate

`logrotate` automatically rotates, compresses, and removes old log files.

**Purpose**: Prevent logs from using too much disk space.

### Important Files

| Path                  | Description                              |
| :-------------------- | :--------------------------------------- |
| `/etc/logrotate.conf` | Global configuration file for logrotate. |
| `/etc/logrotate.d/`   | Per-application logrotate rules.         |

### Key Concepts

- **Rotation**: Create a new log file and archive the old one.
- **Compression**: Gzip older logs to save space.
- **Retention**: Keep only a certain number of old log files.
- **Scheduled Execution**: Usually run daily via cron (`/etc/cron.daily/logrotate`).

### Example: Manual Logrotate Run

```bash
sudo logrotate -f /etc/logrotate.conf
```

### Common Logrotate Directive Example

```bash
/var/log/syslog {
    rotate 7
    daily
    missingok
    notifempty
    compress
    delaycompress
    postrotate
        /usr/lib/rsyslog/rsyslog-rotate
    endscript
}
```

---

# Summary Overview

| Topic       | Summary                                                                |
| :---------- | :--------------------------------------------------------------------- |
| Boot Logs   | `/var/log/boot.log`, early boot messages.                              |
| Login Logs  | `wtmp`, `btmp`, viewed via `last` and `lastb`.                         |
| Kernel Logs | `dmesg`, shows messages from the kernel ring buffer.                   |
| Journald    | `journalctl` commands, `/var/log/journal/` for persistent logs.        |
| Syslog      | Traditional text-based logging system, managed by rsyslog.             |
| Logrotate   | Automatic log file rotation and compression via `/etc/logrotate.conf`. |

---

# Issues

## Log Spamming in my I3WM Working Environment

### Conky

- Command in conky write stderr to log, causing numerous log spamming
- Solution: redirect stderr to `/dev/null` instead of writing to journal log
  ```
  exec cat /proc/cpuinfo 2> /dev/null
  execi 3 curl ipinfo.io/ip 2> /dev/null
  execi 3 curl ipinfo.io/ip 2> /dev/null
  ```

### Parcellite

- Parcellite floods stderr when sync clipboard failed
- Solution: redirect stderr to `/det/null` when starts parcellite in i3
  ```
  i3-msg exec 'parcellite 2> /dev/null'
  ```
