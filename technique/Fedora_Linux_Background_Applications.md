# Fedora Linux Background Applications
- Background application auto-activate after startup
- Reference
    - https://linux.die.net/man/
    - https://www.freedesktop.org/software/systemd/man/index.html
    - https://www.mankier.com/

Table of Contents
=================

* [Fedora Linux Background Applications](#fedora-linux-background-applications)
* [Table of Contents](#table-of-contents)
* [Context](#context)
   * [systemd: systemd system and service manager](#systemd-systemd-system-and-service-manager)
   * [systemd --user](#systemd---user)
   * [abrtd: Manage problems handled by ABRT](#abrtd-manage-problems-handled-by-abrt)
   * [Miscellaneous](#miscellaneous)

Created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc)

# Context

## systemd: systemd system and service manager
- systemd-journald: Journal service
- systemd-udevd: Device event managing daemon
- systemd-oomd: A userspace out-of-memory (OOM) killer
- systemd-resolved: Network Name Resolution manager
- systemd-logind: Login manager
- systemd-machined: Virtual machine and container registration manager

## systemd --user
- at-spi-bus-launcher:
- ap-spi2-registryd:
- dbus-broker: D-Bus message broker
- dconf-service: D-Bus service for writes to the dconf database
- flatpak-portal:
- flatpak-session-helper:
- gvfsd: Main daemon for gvfs
- gvfsd-fuse: Fuse daemon for gvfs
- ibus-portal:
- obexd:
- pipewire: The PipeWire media server
- pipewire-pulse: The PipeWire PulseAudio replacement
- wireplumber:
- xdg-desktop-portal:
- xdg-document-portal:
- xdg-desktop-portal-gnome:
- xdg-desktop-portal-gtk:
- xdg-permission-store:

## abrtd: Manage problems handled by ABRT
- abrt-dump-journal-core: Extract coredumps from systemd-journal
- abrt-dump-journal-oops: Extract oops from systemd-journal
- abrt-dump-journal-xorg: Extract Xorg crashes from systemd-journal

## Miscellaneous
- accounts-daemon:
- alsactl: advanced controls for ALSA soundcard driver
- atd: run jobs queued for later execution
- auditd: The Linux Audit daemon
- avahi-daemon: The Avahi mDNS/DNS-SD daemon
- bluetoothd: Bluetooth daemon
- bwrap: container setup utility
- chronyd: chrony background daemon
- colord:
- crond: daemon to execute scheduled commands
- gdm: The GNOME Display Manager
- gssproxy: GssProxy Daemon
- lower-memory-monitor:
- mcelog: Decode kernel machine check log on x86 machines
- ModemManager: mobile broadband modem management daemon
- NetworkManager: network management daemon
- packagekitd:
- polkitd: PolicyKit daemon
- pcscd: PC/SC Smart Card Daemon
- rngd: Check and feed random data from hardware device to kernel
- rtkit-daemon: Security Enhanced Linux Policy for the rtkit_daemon processes
- sshd: OpenSSH daemon
- switcheroo-control: Launch a command on a specific GPU
- thermald: start Linux thermal daemon
- touchegg:
- udisks-daemon: udisks Daemon
- uresourced:
- upowerd: UPower Daemon
- wpa_supplicant: Wi-Fi Protected Access client and IEEE 802.1X supplicant
