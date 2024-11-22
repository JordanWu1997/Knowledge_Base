Tags: #SystemD
Vimwiki: :SystemD:

# SystemD

## Predecessor: `SystemV` (`SysV`)

- https://askubuntu.com/questions/903354/difference-between-systemctl-and-service-commands
- https://kaige.org/2019/07/24/systemctl-VS-sysctl-VS-service-VS-init-d/

### Introduction

- Tools for start/stop/reload services, also wrappers for `/etc/init.d/` scripts
- Nowadays, `sysV` has been replaced by `systemd` in most distros, but `systemd` provides backward compatibility by wrapping `sysV` commands

### Usage

- `service start/stop/reload <SERVICE>`
  - start/stop/reload service
- `chkconfig <SERVICE>`
  - check if service is enabled

## Systemd

- https://blog.beck-yeh.idv.tw/linux/systemd/
- https://linux.vbird.org/linux_basic/centos7/0560daemons.php
- https://systemd.io/
- https://www.jinbuguo.com/systemd/systemd.unit.html
- https://www.liquidweb.com/kb/what-is-systemctl-an-in-depth-overview/
- https://www.liquidweb.com/kb/what-is-systemctl-an-in-depth-overview/
- https://www.techtarget.com/searchnetworking/tip/20-systemctl-commands-for-system-and-service-management

### Service Execution Priority: from High to Low

1. `/etc/systemd/system/`: scripts within it starts at startup
   - For administrator customization
2. `/run/systemd/system/`
   - Unit files generate during runtime
3. `/usr/lib/systemd/system/`
   - Default unit files provided by packages

### TODO: Unit Filetypes

- Service (`.service`)
- Socket (`.socket`): for inter-process communication (IPC), wake up inactive service when needed
- Target (`.target`): groups of units (services, sockets, and etc.)
- Mount/Automount (`.mount`/`.automount`)
- Path (`.path`): detect specific files or directories
- Timer (`.timer`): anacrontab-like service in systemd

### TODO: Unit Configuration File

- `[Unit]`
  - `After`
  - `Before`
  - `BindsTo`
  - `Conflicts`
  - `PartOf`
  - `Requires`
  - `Requisite`
  - `Wants`
- `[Service]`
  - `ExecStart`
  - `ExecStop`
  - `ExecReload`
  - `Restart`
- `[INSTALL]`
  - `RequiredBy`
  - `WantedBy`
  - `Alias`

### Service (Daemon) Status

- Status
  - `active (running)`: process is actively running
  - `active (exited)`: task completed and exited successfully
  - `active (waiting)`: service is active but waiting for event or condition to proceed
  - `inactive`: service is not active
- Default Status
  - `enabled`: service starts automatically at startup or required
  - `disabled`: service will not start automatically but manually
  - `static`: service cannot be enabled or disabled directly
    - Service lack of `[INSTALL]` section in configuration file
    - Typically used as dependencies
  - `masked`: service is completely disabled and cannot be started

### Target (Runlevels in SysV)

- `poweroff.target`
  - SysV Runlevel 0: Halt
- `rescue.target`
  - SysV Runlevel 1: Single-user Mode (for administrative or recovery functions only)
- `multi-user.target`
  - SysV Runlevel 2: Multi-user Mode (but most distros leave this level undefined)
  - SysV Runlevel 3: Extend Multi-user Mode (Console only, No GUI)
  - SysV Runlevel 4: Preserved for personal customization
- `graphic.target`
  - SysV Runlevel 5: Graphical Mode
- `reboot.target`
  - SysV Runlevel 6: Reboot

### TODO: Login File

- `/etc/systemd/logind.conf`

## TL;DR Systemd Usage

- `systemctl list-units`
  - Default behavior for `systemctl` command without arguments
  - List active service status sorted by unit-file types
- `systemctl list-unit-files`
  - List all services on system
  - Add `--type=<UNIT_TYPE>` to filter specific type of unit
  - Add `--state=<UNIT_STATE>` to filter specific state of unit
- `systemctl list-dependencies <UNIT>`
  - Show unit `<UNIT>` dependency tree
  - Add `--reverse` to change to show what service requires `<UNIT>`
- `systemctl status <UNIT>`
  - Show unit `<UNIT>` status and dependencies in tree
- `systemctl show <UNIT>`
  - Show unit properties e.g. environment variables
- `systemctl enable <SERVICE>`
  - Create soft link `/etc/systemd/system/<SERVICE>` to `/usr/lib/systemd/system/<SERVICE>`
- `systemctl disable <SERVICE>`
  - Remove soft link `/etc/systemd/system/<SERVICE>`
- `systemctl mask <SERVICE>`
  - Create soft link `/etc/systemd/system/<SERVICE>` to `/dev/null`
- `systemctl unmask <SERVICE>`
  - Unlink `/etc/systemd/system/<SERVICE>` to `/dev/null`
- `systemctl editor <SERVICE>`
  - Overwrite default configuration by adding changes in `/etc/systemd/system/<SERVICE>.d/overwrite.conf`
  - Add `--full` to edit the default configuration file instead
- `systemctl daemon-reload`
  - Apply changes to services
- `systemctl isolate <TARGET>`
  - Switch to mode `<TARGET>`
  - Apply changes to services
- `systemctl status --failed`
  - Show services failed to start
- `systemctl reset-failed`
  - Restart all failed services
- `systemd-analyze`
- `systemd-analyze`
  - Show systemd startup time
  - Add `blame` to show service by service
