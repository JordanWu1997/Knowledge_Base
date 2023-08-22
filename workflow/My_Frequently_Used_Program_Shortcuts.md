# My Frequently Used Program Shortcut
- Keyboard-driven workflow setup

Table of Contents
=================

* [My Frequently Used Program Shortcut](#my-frequently-used-program-shortcut)
* [Table of Contents](#table-of-contents)
* [Context](#context)
   * [Gnome (Desktop Environment)](#gnome-desktop-environment)
      * [Navigation](#navigation)
      * [Window](#window)
      * [Application](#application)
      * [Miscellaneous](#miscellaneous)
   * [I3 (Window Manager)](#i3-window-manager)
   * [Vim/Neovim (Text editor)](#vimneovim-text-editor)
   * [Tmux (Terminal Multiplexer)](#tmux-terminal-multiplexer)
   * [Rofi (Application/Window Selector)](#rofi-applicationwindow-selector)
   * [Kitty (Terminal Emulator)](#kitty-terminal-emulator)
   * [Fish (Shell)](#fish-shell)
      * [Command line input](#command-line-input)
      * [FZF](#fzf)
      * [Miscellaneous function](#miscellaneous-function)
      * [Reference](#reference)
   * [Ranger (File manager)](#ranger-file-manager)
      * [Normal mode](#normal-mode)
         * [Pane navigation](#pane-navigation)
         * [Tab navigation](#tab-navigation)
         * [Combination key action](#combination-key-action)
         * [Fn-key shortcuts](#fn-key-shortcuts)
         * [Vim-like mark](#vim-like-mark)
         * [Miscellaneous](#miscellaneous-1)
      * [Console mode](#console-mode)
   * [Htop (System Monitor)](#htop-system-monitor)
   * [Feh (Image Viewer)](#feh-image-viewer)
   * [Zathura (PDF Viewer)](#zathura-pdf-viewer)
      * [General mode](#general-mode)
      * [Index mode](#index-mode)
      * [Presentation mode](#presentation-mode)
      * [Reference](#reference-1)
   * [Jupyter-lab (Python notebook)](#jupyter-lab-python-notebook)
      * [Built-in function](#built-in-function)
      * [Reference](#reference-2)
   * [Brave-browser (Chromium-based web-browser)](#brave-browser-chromium-based-web-browser)
      * [Built-in function](#built-in-function-1)
         * [Tabs and windows](#tabs-and-windows)
         * [Browser](#browser)
         * [Address bar](#address-bar)
         * [Webpage](#webpage)
      * [Extension - Vimium](#extension---vimium)
         * [Page/History navigation](#pagehistory-navigation)
         * [Tabs manipulation](#tabs-manipulation)
         * [Miscellaneous](#miscellaneous-2)
      * [Extension - Read Aloud (Text to speech)](#extension---read-aloud-text-to-speech)
      * [Extension - Marvellous Suspender](#extension---marvellous-suspender)
      * [Extension - Tab to window / Merge windows](#extension---tab-to-window--merge-windows)
      * [Extension - Youtube Playback Speed Control](#extension---youtube-playback-speed-control)
      * [Extension - Miscellaneous](#extension---miscellaneous)
      * [Website - Youtube](#website---youtube)
      * [Website - Notion](#website---notion)
      * [Reference](#reference-3)
   * [Spotify-TUI (Spotify TUI)](#spotify-tui-spotify-tui)
   * [Parcellite (Clipboard Manager)](#parcellite-clipboard-manager)
   * [IBUS (Input Utility)](#ibus-input-utility)
   * [Emailspring (Email Client)](#emailspring-email-client)

Created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc)

# Context

## Gnome (Desktop Environment)

### Navigation
- [Ctrl]+[Alt]+[h/l]: Move to left/right workspace
- [Win]+[Shift]+[h/l]: Move window to left/right workspace
- [Ctrl]+[Alt]+[Shift]+[h/l]: Move window to left/right workspace

### Window
- [Win]+[Shift]+[q]: Close window
- [Win]+[-]: Minimize window
- [Win]+[k/j]: Maximize/Minimize window
- [Win]+[h/l]: Make window align to h/l
- [Ctrl]+[Alt]+[r]: Resize window with mouse
- [Win]+[f]: Toggle full screen mode
- [Win]+[Mouse]: Move current window

### Application
- [Alt]+[Tab]: Switch applications
- [Ctll]+[Alt]+[0]: Open file manager
- [Ctrl]+[Alt]+[-]: Open web-browser
- [Win]+[Enter]: Open terminal

### Miscellaneous
- [Win]+[d]: Search in overview mode
- [Win]+[Shift]+[Escape]: Lock screen
- [Win]+[Shift]+[i]: Enter command prompt
- [Win]+([Shift])+[Space]: (Prev)/Next input method
- [Alt]+[Space]: Show menu option
- [Win]+[a]: Show all applications
- [Win]: Enter overview mode

## I3 (Window Manager)
- https://github.com/JordanWu1997/I3_Sway_Config

## Vim/Neovim (Text editor)
- https://github.com/JordanWu1997/Vim_Tmux_Config

## Tmux (Terminal Multiplexer)
- https://github.com/JordanWu1997/Vim_Tmux_Config

## Rofi (Application/Window Selector)
- [Ctrl/Alt]+[h/j/k/l]: Move left/down/up/right
- [Ctrl/Alt]+[Space]: Open selected
- [Alt]+([Shift])+[Tab]: Open selected
- [Ctrl]+[Tab]: Switch mode (run/drun/window/windowcd)
- [Ctrl]+[g/[]: Exit

## Kitty (Terminal Emulator)
- [Ctrl]+[Shift]+[u]: Unicode input
- [Ctrl]+[Shift]+[m/p]: Dec/Inc opacity
- [Alt]+[Shift]+[m/p]: Min/Max opacity
- [Ctrl/Alt]+[Shift]+[d]: Restore to default opacity
- [Ctrl]+[Shift]+[-/+]: Dec/Inc font size
- [Ctrl/Alt]+[Shift]+[0]: Set font size to 1/20
- [Ctrl]+[Shift]+[Alt]+[0]: Restore to default font size
- [Ctrl]+[Shift]+[Alt]+[d]: Debug kitty configuration file
- [Ctrl]+[Shift]+[Alt]+[r]: Reload kitty configuration file
- [Ctrl]+[Shift]+[Win]+[1~6]: Change kitty colorscheme

## Fish (Shell)
- Recommended plugins: `bang-bang`, `fzf`

### Command line input
- [Ctrl]+[a/e]: Move to the beginning/end of line
- [Alt]+[Left/Right]: Move to prev/next word
- [Ctrl]+[b/f]: Move to prev/next character
- [Alt]+[Up/Down]: Prev/Next arguments
- [Ctrl]+[u/k]: Delete to the beginning/end of line
- [Ctrl]+[d/h]: Delete next/prev character
- [Ctrl]+[w]: Delete previous word
- [Alt]+[d]: Delete next word
- [Ctrl]+[d]: If there is nothing in command, it will close entire terminal
- [Ctrl]+[c]: Cancel entire line input
- [Ctrl]+[j]: Enter newline

### FZF
- [Ctrl]+[r]: FZF for history
- [Ctrl]+[o]: FZF for file and open with editor
- [Ctrl]+[t]: FZF for file/directory and copy to command line
- [Ctrl]+[g]: FZF for file and open with xdg-open
- [Alt]+[c]: FZF for directory and change to that directory
- [Ctrl/Alt]+[j/k]: Previous/Next FZF option

### Miscellaneous function
- [Ctrl]+[l]: Clear screen
- [Alt]+[e/v]: Open external editor ($EDITOR)
- [Alt]+[p]: Page output (add &| less in the end of line)
- [Alt]+[l]: List all directories (ls -D in command line)
- [Alt]+[w]: Short help on current word (similar to type)

### Reference
- https://devhints.io/fish-shell
- https://cheatography.com/myounkin/cheat-sheets/fish-shell/

## Ranger (File manager)

### Normal mode

#### Pane navigation
- [Shift]+[Grave]: Toggle view mode (current column only)
- [j/k]: Move down/up in current directory
- [h/l]: Move to parent/child directory
- [Shift]+[h/l]: Move to prev/next directory in history
- [Alt]+[j/k]: Scroll down/up in preview pane
- [f]: Find in current pane

#### Tab navigation
- [Ctrl]+[w]: Close current tab
- [Alt]+[h/l]: Move to prev/next tab
- ([Shift])+[Tab]: Move to (prev)/next tab
- [Alt]+[#Number]: Move to tab number #

#### Combination key action
- [Shift]+[m]+[...]: Modify line mode ...
- [g]+[...]: Go to ...
- [y]+[...]: Yank ...
- [p]+[...]: Paste ...
- [d]+[...]: Delete ...
- [c]+[...]: Search ...
- [o]+[...]: Sort ...
- [z]+[...]: Setting ...
- [.]+[...]: Filter stack ...
- [r]+[...]: Open selection with ...

#### Fn-key shortcuts
- [F1]: Show help
- [F2]: Rename directory/file (append)
- [F3]: Make new directory (mkdir)
- [F4]: Display file
- [F5]: Cyclic line number (absolute/relative/none)
- \[F6]: Copy
- \[F7]: Cut
- \[F8]: Paste
- [F9]: Move to trash (trash)
- \[F10]: Delete (rm)

#### Vim-like mark
- \[m]: mark
- [u]+[m]: un-mark
- [Grave/']: go to mark

#### Miscellaneous
- \[q]: Quit
- [x]: Close tab
- [Shift]+[x]: Restore closed tab
- [i]: Show file
- [e]: Edit file
- [f]: Search and go to directory
- [g]+[f]: Search with fzf and preview with cat
- [g]+[Shift]+[f]: Search with fzf and preview with tree
- [\/\]: Search
- [c]+[d]: Change directory
- [d]+[c]: Calculate cumulative usage
- [Space]: Select item under cursor
- ([u])+[v]: (Reversed) visual mode
- (u)+[Shift]+[v]: (De)Select all
- ([Shift])+[a]: Rename file (append)
- [Shift]+[i]: Rename file (insert)
- [Backspace]: Toggle hidden files
- [Shift]+[\/]: Show help
- [Shift]+[s]: Open shell within ranger
- [Shift]+[r]: Refresh current working directory
- [Ctrl]+[r]: Reset ranger
- [#]+[g]+[g]: Go to line #
- [#]+[#]+[#]+[=]: Chmod user/group/other to r/w/x (4/2/1)

### Console mode
- ([Shift])+[q]: Quit (all) tab
- [Ctrl]+[n/p]: Next/Prev command in console mode

## Htop (System Monitor)
- [Alt]+[h/j/k/l]: Scroll left/down/up/right
- [Shift]+[n/p/m/t]: Sort process on PID/CPU%/MEM%/TIME
- [t]: Tree view
- [+/-]: Expand/collapse tree
%%- [\*]: Toggle all tree
- [k]: Kill process
- [h]: Show help menu
- [u]: Display process owned by particular user
- [p]: Toggle program path
- [i]: Set IO priority
- [w]: Wrap process

## Feh (Image Viewer)
- [Shift]+[,/.]: Rotate image 90 degree (counter)clockwise
- [Shift]+[-/\]: Flip image (vertically/horizontally)
- [Ctrl]+[j/k]: Zoom in/out
- [Ctrl]+[-/=]: Zoom in/out (or [-/=])
- [Ctrl]+[0]: Zoom fit (or [Shift]+[=])
- [Shift]+[j/k]: Next/Prev image (or [n/p])
- [h/j/k/l]: Scroll left/down/up/right
- [d]: Toggle filename
- [g]: Toggle fixed geometry
- [m]: Toggle menu

## Zathura (PDF Viewer)

### General mode
- [h/j/k/l]: Scroll left/down/up/right
- [Shift]+[j/k]: Scroll page down/up or ([Space])
- [Ctrl]+[d/u]: PageDown/PageUp
- [a/s]: Adjust window in best-fit/width
- [d]: Toggle two-page/one-page mode
- [f/;]: Open URL in default web-browser (xdg-open)
- [Ctrl]+[o/i]: Jump backward/forward in jumplist (just like vim)
- [Ctrl]+[r]: Recolor (greyscale and invert colors)
- [Shift]+[r]: Reload document
- [Ctrl]+[j/k]: Zoom in/out (or [-/=])
- [Ctrl]+[-/=]: Zoom in/out (or [-/=])
- [Ctrl]+[0]: Zoom fit (or [Shift]+[=])
- [/]: Search mode
- [b]+[l]: List all bookmarks
- [b]+[m]: Add bookmark
- [b]+[d]: Delete bookmark
- [Shift]+[;]: Enter command
- [Ctrl]+[g]: Toggle statusbar
- \[F11\]: Fullscreen mode

### Index mode
- [Tab]: Switch to index mode
- [j/k]: Move to next/prev entry
- ([Shift])+[h]: Collapse (all) entries
- ([Shift])+[l]: Expand (all) entries
- [Space]: Open select entry

### Presentation mode
- [F5]: Switch to normal mode
- [Space]: Next page
- [Backspace]: Previous page

### Reference
- https://defkey.com/zathura-shortcuts?filter=basic

## Visidata (TUI data viewer)

### Sheet operation
- [Shift]+[s]: Open sheets sheet
- [g]+[S]: Go to sheet graveyard (trash can)
- [Shift]+[c]: Show column attributes
    - [d]: Delete column
    - [a]: Add column

### Navigation
- [h/j/k/l]: Go to left/down/up/right
- [g]+[h/j/k/l]: Jump to leftmost/bottom/top/rightmost
- [z]+[r]+[Number]: Jump to row number
- [z]+[c]+[Number]: Jump to column number

### Row/Column/Cell Operations
- [Shift]+[u]: Undo
- [Shift]+[r]: Redo
- [Shift]+[j/k]: Move current row down/up
- [Shift]+[h/l]: Move current column left/right
- [i]: Insert column
- [s]: Select
- [g]+[s]: Select all
- [u]: Unselect
- [g]+[u]: Unselect all
- [t]: Toggle current selection
- [d]: Delete
- [e]: Edit current cell
- [^]: Rename current column
- [[]: Sort ascending
- []]: Sort descending
- [q]: Quit current sheet

### Column Type
- [~]: Set column type to string
- [#]: Set column type to integer
- [%]: Set column type to float
- [$]: Set column type to currency
- [@]: Set column type to date
- [z]+[#]: Set column type to vlen
- [z]+[~]: Set column type to anytype

### Search
- [/]: Regex search
- [n/N]: Jump to next/previous matching row
- [c]: Jump to matching column
- [|]: Select row matches the current row
- [\]: Unselect row matches the current row

### Miscellaneous
- [Shift]+[f]: Show frequency table for current column
- [Ctrl]+[h]: Show help menu
- [Ctrl]+[q]: Force-quit

### Reference
- https://jsvine.github.io/intro-to-visidata/index.html

## Jupyter-lab (Python notebook)

### Built-in function
- [Alt]+[w]: Close current tab
- [Ctrl]+[Enter]: Run cell
- [Shift]+[Enter]: Run cell and create new empty cell
- [Ctrl]+[/]: Comment selected lines
- [Ctrl]+[Shift]+[/]: Move to left/right tab
- [Ctrl]+[b]: Toggle left panel
- [Ctrl]+[p]: Command palette

### Reference
- https://jupyterlab.readthedocs.io/en/stable/user/interface.html
- https://blog.ja-ke.tech/2019/01/20/jupyterlab-shortcuts.html
- https://morioh.com/p/19eb8d900dc1

## Brave-browser (Chromium-based web-browser)
Brave browser only support either Ctrl or Alt as component of shortcut

### Built-in function
Brave built-in shortcut. Most of them used __Ctrl__ as prefix

#### Tabs and windows
- [Ctrl]+([Shift])+[n]: Open new (private) window
- [Ctrl]+([Shift])+[t]: Open (last)/new tab
- [Ctrl/Alt]+[#Number]: Go to tab number #
- [Ctrl]+([Shift])+[Tab]: Move to (prev)/next tab
- [Ctrl]+([Shift])+[w]: Kill current (window)/tab
- [Alt]+[Left/Right]: Prev/Next page in history
- [Ctrl]+[Shift]+[a]: List all tabs

#### Browser
- [Alt]+[e]: Open browser main menu
- [Ctrl]+[Shift]+[b]: Hide bookmark bar
- [Ctrl]+[Shift]+[o]: Open bookmark manager
- [Ctrl]+[h]: History
- [Ctrl]+[j]: Downloads
- [Shift]+[Esc]: Open browser task manager
- [Ctrl]+([Shift])+[g]: Jump to (prev)/next search

#### Address bar
- [F6]: Go to address bar
- [Ctrl]+[e/k]: Search in Google

#### Webpage
- [Ctrl]+[p]: Print current page
- [Ctrl]+[s]: Save current page
- [F5]: Reload current page
- [Ctrl]+[r]: Reload current tab
- [Ctrl]+[d]: Add to bookmark
- [Ctrl]+[Shift]+[d]: Add all open tabs as bookmarks in a new folder
- \[F11\]: Toggle full-screen
- [Ctrl]+[Shift]+[-/=]: Zoom out/in
- [Ctrl]+[0]: Zoom default
- [Ctrl]+[Left/Down/Up/Right]: Move cursor left/down/up/right

### Extension - Vimium
Vim-like navigator in web page

#### Page/History navigation
- ([z])+[h/j/k/l]: Scroll (all page) left/down/up/right
- [Shift/g]+[g]: Move to top/bottom of tab
- [d/u]: Scroll down/up in tab
- [Shift]+[r]: Reload page
- [y]+[y]: Copy current tab URL
- ([Shift])+[p]: Open copy URL in (new) tab
- [g]+(Shift)+[u]: Go up to (root of) URL hierarchy
- [i]: Enter insert mode (disable vimium temporarily)
- [Ctrl]+[[]: Escape (e.g. escape insert mode)
- ([Shift])+[v]: Enter visual (line) mode, press c to change start point
- [v]+[c]: Enter caret mode
- [g]+[i]: Go to text input on the page
- ([Shift])+[f/;]: Open link in (new) tab
- [Alt]+[f/;]: Open multiple links in new tab
- [g]+[p/n]: Go to prev/next page
- [g]+([Shift])+[f]: Select (top of) next frame on page
- [m]: Create mark
- [Grave]: Go to mark
- [Shift]+[h/l]: Go back/forward history

#### Tabs manipulation
- [Shift]+[j/k]: Move to right/left tab
- [g]+[0/$]: Go to first/last tab
- [Shift]+[']: Go to previously visited tab
- [y]+[t]: Copy current tab URL and open in new tab (duplicate current tab)
- [g]+[Shift]+[p]: Pin/unpin current tab
- [Shift]+[m]: Toggle mute current tab
- ([Shift])+[x]: (Restore)/Kill tab
- [Ctrl]+([Shift])+[x]: Kill all tabs on the (left)/right
- [Alt]+[Ctrl]+[Shift]+[x]: Kill all other tabs
- [Shift]+[w]: Split tab to new window
- [Shift]+[,/.]: Move tab to left/right
- [Shift]+[\[/\]]: Move tab to left/right
- [Alt]+[Shift]+[,/.]: Move tab to the left/right end

#### Miscellaneous
- [t]: Search open tabs and move to selected tab
- ([Shift])+[o]: Open input URL in (new) tab
- ([Shift])+[b]: Open bookmark in (new) tab
- ([Shift])+[e]: Edit current URL and open in (new) tab
- [/]: Search in current tab
- [n/N]: Go to prev/next match
- [Shift]+[/]: Show Vimium help

### Extension - Read Aloud (Text to speech)
- [Alt]+[Shift]+[l]: Activate Read Aloud (Read Aloud: A Text to Speech Voice Reader)
- [Alt]+[,/.]: Forward/Backward
- [Alt]+[Space]: Play/Pause
- [Alt]+[Shift]+[Space]: Stop

### Extension - Marvellous Suspender
- [Alt]+[s]: Suspend/Unsuspend active tab
- [Alt]+[p]: Pause/Unpause suspension of active tab
- [Alt]+[Shift]+[s]: Suspend all other tabs in active window
- [Alt]+[Shift]+[u]: Unsuspend al tabs in active window

### Extension - Tab to window / Merge windows
- [Alt]+[Shift]+[x]: Merge all split tab into current window (Merge Windows)
- [Alt]+[x]: Split tab to new window (Tab to Window/Popup - Keyboard Shortcut)
- [Alt]+[j/k]: Merge tab to next/prev window (Tab to Window/Popup - Keyboard Shortcut)

### Extension - Youtube Playback Speed Control
- [a]: Decrease playspeed (-0.25)
- [s]: Increase playspeed (+0.25)
- [q]: Reset playspeed (1.0)

### Extension - Miscellaneous
Brave extension shortcut: brave://extensions/shortcuts, to keep it simple try to use __Alt__ as prefix.
- [Alt]+[Shift]+[b]: Activate Bitwarden (Bitwarden - Free Password Manager)
- [Alt]+[Shift]+[f]: Autofill last used login (Bitwarden - Free Password Manager)
- [Alt]+[Shift]+[d]: Activate Google Dictionary (Google Dictionary (by Google))
- [Alt]+[Shift]+[t]: Activate Google Translate (Google Translate)
- [Alt]+[Shift]+[v]: Activate Vimium (Vimium)
- [Alt]+[Shift]+[d]: Activate/Deactivate dark mode (Dark Reader)
- [Alt]+[Shift]+[o]: Activate OneTab Group (OneTab Group)
- [Alt]+[o]: Send current tab to OneTab Group (OneTab Group)
- [Alt]+[Shift]+[r]: Activate Nimbus (Nimbus - Screenshot and screen video recorder)
- [Alt]+[Shift]+[i]: Activate Mendeley Web Importer
- [Alt]+[Shifk]+[e]: Activate Invert! (Invert!)

### Extension - Backup (Not Used Anymore)
- [Alt]+[Shift]+[i]: Activate Visor (Visor)
- [Alt]+[Shift]+[a]: Activate Overleaf textarea (Overleaf textarea)

### Website - Youtube
- [f]: Full screen player
- [Shift]+[,/.]: Dec/Inc play speed
- [,/.]: Play backward/forward frame by frame
- [1-9]: Move to portion of playing content
- [Home/End]: Beginning/End of playing content
- [c]: Open CC caption
- [o]: Toggle CC caption text opacity
- [w]: Toggle CC caption background opacity
- [i]: Open mini player
- [m]: Mute player
- [Up/Down]: Inc/Dec play player sound
- [Left/j]: Fast backward playing content
- [Right/l]: Fast forward playing content
- [Space/k]: Pause playing content

### Website - Notion
- https://usethekeyboard.com/notion/
- https://www.notion.so/Learn-the-shortcuts-66e28cec810548c3a4061513126766b0

### Reference
- https://support.brave.com/hc/en-us/articles/360032272171-What-keyboard-shortcuts-can-I-use-in-Brave-

## Spotify-TUI (Spotify TUI)
- \[q\]: Quit/Back
- \[/\]: Search
- [d]: Manage play device
- [Space]: Toggle play/pause
- [-]: Decrease volume (-)
- [=]: Increase volume (+)
- [n/p]: Next/Prev track
- [Shift]+[,/.]: Fast backwards/forwards
- [s]: Save current playback to favorite
- [Shift]+[s]: Toggle shuffle play
- [r]: Recommended songs
- [Shift]+[r]: Repeat track/all
- ([Shift])+[a]: Jump to (artist)/album
- ([Shift])+[c]: Copy current playing url
- [w]: Follow an artist/playlist, save an album to library
- [Shift]+[d]: Delete saved album/playlist

## Parcellite (Clipboard Manager)
- [Ctrl]+[Alt]+[c]: Open clipboard history
- [Ctrl]+[Alt]+[p]: Open clipboard preference

## IBUS (Input Utility)
- [Ctrl]+[Alt]+[Space]: Toggle input method (Chewing/English)
- [Ctrl]+[0]: Show special character options

## Emailspring (Email Client)
- [j/k]: Previous/Next mail
- [PageDown/PageUp]: Scroll down/up mail content
- [s]: Star current mail
- [Ctrl]+[1]: Show all account mail
- [Ctrl]+[n+1]: Show #n user mail
