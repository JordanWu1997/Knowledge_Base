# Fedora Linux Background Applications
- Background applications auto-activated after startup
- Reference
    - https://linux.die.net/man/
    - https://www.freedesktop.org/software/systemd/man/index.html
    - https://www.mankier.com/

# Context

## Control Group (CGroup)
```
/
├─init.scope
│ └─ ...
├─system.slice
│ ├─ ...
...
│ └─ ...
└─user.slice
  └─user-1000.slice
    ├─session-2.scope
    │ ├─ ...
    ...
    │ └─ ...
    └─user@1000.service
      ├─app.slice
      │ ├─ ...
      ...
      │ └─ ...
      ├─init.scope
      └─session.slice
        ├─ ...
        ...
        └─ ...
```

## CGroup System Slice
```
/
├─init.scope
│ └─ ...
├─system.slice
│ ├─ ...
...
│ └─ ...
```

### init.scope

### system.slice
- `ModemManager.service`: Modem Manager
- `NetworkManager.service`: Network Manager
- `abrt-journal-core.service`: Create ABRT problems from coredumpctl message
- `abrt-oops.service`: ABRT kernel log watcher
- `abrt-xorg.service`: ABRT Xorg log watcher
- `abrtd.service`: Manage problems handled by Automated Bug Reporting Tool (ABRT)
- `accounts-daemon.service`: Account Service
- `alsa-state.service`: Manage Sound Card State (restore and store)
- `atd.service`: Deferred execution scheduler
- `auditd.service`: Security Auditing Service
- `avahi-daemon.service`: Avahi mDNS/DNS-SD daemon
- `bluetooth.service`: Bluetooth service
- `chronyd.service`: Network Time Protocol (NTP) client/server
- `colord.service`: color profiles management
- `crond.service`: Command Scheduler
- `dbus-broker.service`: D-Bus System Message Bus
- `fail2ban.service`: Fail2Ban Service
- `firewalld.service`: dynamic firewall daemon
- `gdm.service`: GNOME Display Manager
- `gssproxy.service`: GSSAPI Proxy Daemon
- `libvirtd.service`: Virtualization Daemon
- `lower-memory-monitor.service`: Low Memory Monitor
- `mcelog.service`: Machine Check Exception Logging Daemon
- `packagekit.service`: PackageKit Daemon
- `pcscd.service`: PC/SC Smart Card Daemon
- `polkit.service`: Authorization Manager
- `preload.service`: Adaptive readahead daemon
- `rngd.service`: Hardware RNG Entropy Gatherer Daemon
- `rsyslog.service`: System Logging Service
- `rtkit-daemon.service`: RealtimeKit Scheduling Policy Service
- `sshd.service`: OpenSSH server daemon
- `switcheroo-control.service`: Switcheroo Control Proxy service
- `systemd-journald.service`: Journal service
- `systemd-logind.service`: User Login Management
- `systemd-machined.service`: Virtual Machine and Container Registration Service
- `systemd-oomd.service`: Userspace out-of-memory (OOM) killer
- `systemd-resolved.service`: Network Name Resolution
- `systemd-udevd.service`: Rule-based manager for device events and files
- `thermald.service`: Thermal Daemon Service
- `touchegg.service`: Touchegg Daemon
- `udisks2.service`: Disk Manager
- `upower.service`: Daemon for power management
- `uresourced.service`: User resource assignment daemon
- `wpa_supplicant.service`: Wi-Fi Protected Access (WPA) supplicant

## CGroup User Slice
```
└─user.slice
  └─user-1000.slice
    ├─session-2.scope
    │ ├─ ...
    ...
    │ └─ ...
    └─user@1000.service
      ├─app.slice
      │ ├─ ...
      ...
      │ └─ ...
      ├─init.scope
      └─session.slice
        ├─ ...
        ...
        └─ ...
```

### user-1000 slice

#### session-2.scope

#### user@1000.service

##### app.slice
- `at-spi-dbus-bus.service`: Accessibility services bus
- `dbus-broker.service`: D-Bus Message Bus
- `gvfs-daemon.service`: Virtual filesystem service
- `pipewire-pulse.service`: PipeWire PulseAudio
- `pipewire.service`: The PipeWire Media Service
- `wireplumber.service`: Multimedia Service Session Manager
- `xdg-desktop-portal.service`: Portal service
- `xdg-document-portal.service`: flatpak document portal service

##### session.slice
- `flatpak-portal.service`: flatpak portal
- `flatpak-session-helper.service`: flatpak session helper
- `xdg-desktop-portal-gnome.service`: Portal service (GNOME implementation)
- `xdg-desktop-portal-gtk.service`: Portal service (GTK/GNOME implementation)
- `xdg-permission-store.service`: sandboxed app permission store
