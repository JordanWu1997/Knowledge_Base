# D-BUS: Interprocess Communication

- https://wiki.archlinux.org/title/D-Bus
- https://www.youtube.com/watch?v=3ZwzfZgU598

# Context

## Layers

- Layer 1: D-Bus Protocol
- Layer 2: libdbus
- Layer 3: D-Bus Daemon

## D-Bus Daemon

- System wide message bus
  - `/usr/share/dbus-1/system.conf`
- Per user login session message bus
  - `/usr/share/dbus-1/session.conf`
