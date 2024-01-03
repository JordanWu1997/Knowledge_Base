Tags: #gnome #keyboard #mouse #touchpad #system #shortcuts #workflow #setup

---

# Post-installation Setup for GNOME

## I. Tweak Window Appearance
- Tweak window appearance to get the best of GNOME

### Gnome-tweak

#### 1. Installation
- Install gnome-tweaks: `dnf install gnome-tweaks`

#### 2. window titlebar - titlebar action (in gnome-tweaks)
- Secondary-click: set to Menu

#### 3. window titlebar - titlebar buttons:
- Maximize button: set to on
- Minimize buttons: set to on

## II. Change Mouse & Touchpad Actions
- Change mouse & touchpad action to get natural scrolling, faster moving and etc.

### Mouse & Touchpad (in Gnome Settings)

#### 1. Mouse
- Mouse Speed: set to 75% of the bar
- Natural Scrolling: set to off

#### 2. Touchpad
- Natural Scrolling: set to on
- Touchpad Speed: set to 75% of the bar
- Tap to Click: set to on

## III. Change Keyboard Shortcut
- Change application shortcut to fit in my keyboard-driven workflow

### Gnome-terminal

#### 1. File
- New Tab: change to `Ctrl+t`

#### 2. View
- Zoom In: change to `Ctrl+=`

### Keyboard (in Gnome Settings)

#### 1. Launchers
- Home Folder: change to `Ctrl+Alt+0`
- Launch web browser: change to `Ctrl+Alt+-`

#### 2. Navigation
- Hide all normal windows: change to `Super+Shift+z`
- Move to workspace on the left: change to `Super+Shift+grave`
- Move to workspace on the right: `Super+grave`
- Move window one workspace to the left: change to `Alt+Shift+grave`
- Move window one workspace to the right: change to `Alt+grave`
- Move window one monitor down: change to `Super+Shift+[`
- Move window one monitor to the left: change to `Super+Shift+,`
- Move window one monitor to the right: change to `Super+Shift+.`
- Move window one monitor up: change to `Super+Shift+]`
- Switch applications: change to `Alt+Tab`
- Switch system controls: change to `Super+Ctrl+Tab`
- Switch system controls directly: set to disabled
- Switch windows directly: change to `Super+n`
- Switch windows of an app directly: change to `Super+i`
- Switch windows of an application: change to `Alt+q` (for now)

#### 3. System
- Focus the actikve notification: change to `Ctrl+Space`
- Lock screen: change to `Super+Shift+Esacpe`
- Log out: change to `Ctrl+Alt+q`
- Show all appliations: change to `Super+d`
- Show notification list: change to `Ctrl+Shift+Space`

#### 4. Typing
- Switch to next input source: change to `Ctrl+Alt+Space`
- Switch to previous input source: change to `Ctrl+Alt+Shift+Space`

#### 5. Windows
- Close window: change to `Super+Shift+q`
- Hide window: change to `Super+Shift+z`
- Lower window below other windows: change to `Super+z`
- Maximize window: change to `Super+Shift+k`
- Raise window above other windows: change to `Super+Shift+g`
- Raise window if covered, otherwise lower it: change to `Super+g`
- Resize window: change to `Ctrl+Alt+r`
- Restore window: change to `Super+Shift+j`
- Toggle fullscreen mode: change to `Super+f`
- Toggle maximization state: change to `Ctrl+Alt+f`
- View split on left: change to `Super+Shift+h`
- View split on right: change to `Super+Shift+l`

#### 6. Custom Shortcuts
- Open terminal (w/ FISH): set to `Super+Return`
- Open terminal (w/ BASH): set to `Super+Shift+Return`
- Ranger: set to `Ctrl+Alt+2`
- Pulsemixer: set to `Ctrl+Alt+3`
- Htop: set to `Ctrl+Alt+4`

## IV. Extensions
- Note `chrome-gnome-shell` must be installed first

### Add touchpad gesture for x11
- https://github.com/JoseExposito/gnome-shell-extension-x11gestures
- Note `touchegg` must be installed from github first

### Add hot edge to bottom of screen
- https://github.com/jdoda/hotedge

### Vim-style navigation for application switcher
- https://github.com/koko-ng/vim-altTab

### Window tiling
- https://gitlab.com/lundal/tactile

### Window focus
- https://github.com/martinhjartmyr/gnome-shell-extension-focus-changer
