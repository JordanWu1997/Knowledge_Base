# X Power Tools - Chris Tyler

# Table of Contents

- [X Power Tools - Chris Tyler](#x-power-tools---chris-tyler)
  - [Table of Contents)](#table-of-contents)
  - [Context](#context)
    - [1.1 Basics of X window system](#11-basics-of-x-window-system)
    - [1.5 X GUI 7 Layer Structure](#15-x-gui-7-layer-structure)
    - [6.3 Get window information (xwininfo)](#63-get-window-information-xwininfo)
    - [6.4 Check X server configuration (xset)](#64-check-x-server-configuration-xset)
    - [6.6 Modify keyboard repeat rate (xset)](#66-modify-keyboard-repeat-rate-xset)
    - [6.7 Modify mouse move speed acceleration (xset)](#67-modify-mouse-move-speed-acceleration-xset)

Created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc)

# Context

## 1.1 Basics of X window system

- Portable, network-based display system working on almost all operating system (OS)

## 1.5 X GUI 7 Layer Structure

- 7 layer from client to server
  - Client
    - Packed by toolkit (GTK) to simply communication between client and server, including
      - Application (e.g. Gimp)
        - User-end application
      - Desktop environment (e.g. Gnome)
        - System tray, panel, icons
      - Window and compositor manager (e.g. Compiz)
        - Window location and decoration
      - Session manager (e.g. gnome-session)
        - Manage session
      - Display manager (e.g. gdm)
        - User login interface
  - Server
    - X window server (e.g. xorg)
      - Control hardware and firmware
    - Network transmission (e.g. TCP/IP)
      - Transmission between layers

## 6.3 Get window information (xwininfo)

- Interactively select window to get window information
  - Including window size, location, and etc.

## 6.4 Check X server configuration (xset)

- Read and modify X server configuration
  - Get current configuration (in terminal)

    ```bash
    xset -q
    ```

  - Example output from my laptop thinkpad 13 (in terminal)

    ```bash
    Keyboard Control:
      auto repeat:  on    key click percent:  0    LED mask:  00000002
      XKB indicators:
        00: Caps Lock:   off    01: Num Lock:    on     02: Scroll Lock: off
        03: Compose:     off    04: Kana:        off    05: Sleep:       off
        06: Suspend:     off    07: Mute:        off    08: Misc:        off
        09: Mail:        off    10: Charging:    off    11: Shift Lock:  off
        12: Group 2:     off    13: Mouse Keys:  off
      auto repeat delay:  300    repeat rate:  40
      auto repeating keys:  00ffffffdffffbbf
                            fadfffefffedffff
                            9fffffffffffffff
                            fff7ffffffffffff
      bell percent:  50    bell pitch:  400    bell duration:  100
    Pointer Control:
      acceleration:  2/1    threshold:  4
    Screen Saver:
      prefer blanking:  yes    allow exposures:  yes
      timeout:  600    cycle:  600
    Colors:
      default colormap:  0x22    BlackPixel:  0x0    WhitePixel:  0xffffff
    Font Path:
      catalogue:/etc/X11/fontpath.d,built-ins
    DPMS (Energy Star):
      Standby: 600    Suspend: 600    Off: 600
      DPMS is Enabled
      Monitor is On
    ```

## 6.6 Modify keyboard repeat rate (xset)

- Modify keyboard repeat rate
  - In terminal,

    ```bash
    #_xset  [repeat rate] [start repeat time (ms)]  [repeat rate (/sec)]
    xset      r rate              300                     40
    ```

## 6.7 Modify mouse move speed acceleration (xset)

- Modify mouse move speed acceleration
  - Acceleration factor

    - When moving over acceleration threshold, mouse speed becomes acceleration factor times

  - Acceleration threshold

    - Pixel number / sampling time

  - In terminal

    ```bash
    #_xset  [mouse mode] [acceleration factor] [acceleration threshold]
    xset         m               10                      2
    ```
