# My Frequently Used Program Shortcut

## Table of Contents
* [My Frequently Used Program Shortcut](#my-frequently-used-program-shortcut)
   * [Context](#context)
      * [Vim/Neovim (Text editor)](#vimneovim-text-editor)
      * [Tmux (Terminal Multiplexer)](#tmux-terminal-multiplexer)
      * [Fish (Shell)](#fish-shell)
         * [Command line input](#command-line-input)
         * [Miscellaneous function](#miscellaneous-function)
         * [Reference](#reference)
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
         * [Plugins - Miscellaneous](#plugins---miscellaneous)
         * [Plugins - Vimium](#plugins---vimium)
            * [Page/History navigation](#pagehistory-navigation)
            * [Tabs manipulation](#tabs-manipulation)
            * [Miscellaneous](#miscellaneous)
         * [Website - Youtube](#website---youtube)

Created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc)

## Context

### Vim/Neovim (Text editor)
- https://github.com/JordanWu1997/Vim_Tmux_Config

### Tmux (Terminal Multiplexer)
- https://github.com/JordanWu1997/Vim_Tmux_Config

### Fish (Shell)

#### Command line input
- [Alt]+[Left/Right]: Move word
- [Alt]+[Up/Down]: Prev/Next arguments
- [Ctrl]+[u/k]: Delete to the beginning/end of line
- [Ctrl]+[d/h]: Delete next/prev character
- [Ctrl]+[w]: Delete previous word
- [Alt]+[d]: Delete next word
- [Ctrl]+[d]: If there is nothing in command, it will close entire terminal
- [Ctrl]+[c]: Cancel entire line input

#### Miscellaneous function
- [Ctrl]+[l]: Clear screen
- [Ctrl]+[r]: History fuzzy finder (FZF)
- [Alt]+[e/v]: Open external editor ($EDITOR)
- [Alt]+[p]: Page output (add &| less in the end of line)
- [Alt]+[c]: FZF fuzzy finder (FZF)
- [Alt]+[l]: List all directories (ls -D in command line)
- [Alt]+[w]: Short help on current word

#### Reference
- https://devhints.io/fish-shell

### Zathura (PDF Viewer)

#### General mode
- ([Shift])+[j/k]: Scroll (page)/line down/up
- ([Shift])+[h/l]: Scroll left/right
- [Ctrl]+[d/u]: PageDown/PageUp
- [Space]: Scroll page down
- [a]: Adjust window in best-fit mode
- [s]: Adjust window in width mode
- [d]: Adjust window in two-page mode
- [f]: Open URL in default web-browser (xdg-open)
- [Ctrl]+[r]: Recolor (greyscale and invert colors)
- [Shift]+[r]: Reload document
- [-]: Zoom out (-)
- [Shift]+[=]: Zoom in (+)
- [/]: Search mode
- [Shift]+[;]: Enter command
- [Ctrl]+[m]: Toggle inputbar
- [Ctrl]+[n]: Toggle statusbar
- \[F11\]: Fullscreen

#### Index mode
- [Tab]: Switch to index mode
- [j/k]: Move to next/prev entry
- ([Shift])+[h]: Collapse (all) entries
- ([Shift])+[l]: Expand (all) entries
- [Space]: Open select entry

#### Presentation mode
- [F5]: Switch to normal mode
- [Space]: Next page
- [Backspace]: Previous page

#### Reference
- https://defkey.com/zathura-shortcuts?filter=basic

### Jupyter-lab (Python notebook)

#### Built-in function
- [Alt]+[w]: Close current tab
- [Ctrl]+[Enter]: Run cell
- [Shift]+[Enter]: Run cell and create new empty cell
- [Ctrl]+[/]: Comment selected lines
- [Ctrl]+[Shift]+[[/]]: Move to left/right tab
- [Ctrl]+[b]: Toggle left panel
- [Ctrl]+[p]: Command palette

#### Reference
- https://jupyterlab.readthedocs.io/en/stable/user/interface.html
- https://blog.ja-ke.tech/2019/01/20/jupyterlab-shortcuts.html
- https://morioh.com/p/19eb8d900dc1

### Brave-browser (Chromium-based web-browser)
Brave browser only support either Ctrl or Alt as component of shortcut

#### Built-in function
Brave built-in shortcut. Most of them used __Ctrl__ as prefix
- [F5]: Reload current page
- [F6]: Go to URL insert line
- \[F11\]: Full screen tab
- [Ctrl/Alt]+[#Number]: Go to tab number #
- [Ctrl]+([Shift])+[Tab]: Move to (prev)/next tab
- [Ctrl]+[w]: Kill current tab
- [Ctrl]+[t]: Open new tab
- [Ctrl]+[Shift]+[t]: Open last tab
- [Ctrl]+[n]: Open new window
- [Ctrl]+[Shift]+[n]: Open new private window
- [Ctrl]+[d]: Add to bookmark
- [Ctrl]+[h]: History
- [Ctrl]+[j]: Downloads

#### Plugins - Miscellaneous
Brave plugin shortcut: brave://extensions/shortcuts, to keep it simple try to use __Alt__ as prefix.
- [Alt]+[Shift]+[b]: Activate Bitwarden (Bitwarden - Free Password Manager)
- [Alt]+[Shift]+[c]: Activate Cluster (Cluster - Window & Tab Manager)
- [Alt]+[Shift]+[d]: Activate Google Dictionary (Google Dictionary (by Google))
- [Alt]+[Shift]+[t]: Activate Google Translate (Google Translate)
- [Alt]+[Shift]+[x]: Merge all split tab into current window (Merge Windows)
- [Alt]+[x]: Split tab to new window (Tab to Window/Popup - Keyboard Shortcut)
- [Alt]+[j/k]: Merge tab to next/prev window (Tab to Window/Popup - Keyboard Shortcut)
- [Alt]+[s]: Suspend/Unsuspend active tab (The Marvellous Suspender)
- [Alt]+[p]: Pause/Unpause suspension of active tab (The Marvellous Suspender)
- [Alt]+[d]: Activate/Deactivate dark mode (Dark Reader)
- [Alt]+[Shift]+[s]: Suspend all other tabs in active window (The Marvellous Suspender)
- [Alt]+[Shift]+[u]: Unsuspend al tabs in active window (The Marvellous Suspender)
- [Alt]+[Shift]+[v]: Activate Vimium (Vimium)

#### Plugins - Vimium
Vim-like navigator in web page

##### Page/History navigation
- [h/j/k/l]: Scroll left/down/up/right
- [Shift/g]+[g]: Move to top/bottom of tab
- [d/u]: Scroll down/up in tab
- [r]: Reload page
- [y]+[y]: Copy current tab URL
- ([Shift])+[p]: Open copy URL in (new) tab
- [g]+(Shift)+[u]: Go up to (root of) URL hierarchy
- [g]+[i]: Go to text input on the page
- ([Shift])+[f/;]: Open link in (new) tab
- [Alt]+[f/;]: Open multiple links in new tab
- [Shift]+[h/l]: Go back/forward history

##### Tabs manipulation
- [t]: Create new tab
- [Shift]+[j/k]: Move down/up
- [g]+[0/$]: Go to first/last tab of current window
- [y]+[t]: Copy current tab URL and open in tab
- [Alt]+[m]: Mute/Unmute current tab
- [x/X]: Kill/Restore tab
- [Shift]+[w]: Split tab to new window
- [Alt]+[Shift]+[,/.]: Move tab to left/right

##### Miscellaneous
- [/]: Search in current tab
- [n/N]: Go to prev/next match
- ([Shift])+[o]: Open input URL in (new) tab
- ([Shift])+[b]: Open bookmark in (new) tab
- [Shift]+[t]: Search open tabs and move to selected tab
- [g]+(Shift)+[e]: Edit current URL and open in (new) tab
- [Shift]+[/]: Show Vimium help

#### Website - Youtube
- [f]: Full screen player
- [Shift]+[,/.]: Dec/Inc play speed
- [,/.]: Play backward/forward frame by frame
- [1-9]: Move to portion of playing content
- [Home/End]: Beginning/End of playing content
- [c]: Open CC caption
- [i]: Open mini player
- [m]: Mute player
- [Up/Down]: Inc/Dec play player sound
- [Left/Right]: Fast backward/forward playing content
- [Space]: Pause playing content
