# Shell Shortcut
- https://www.howtogeek.com/howto/ubuntu/keyboard-shortcuts-for-bash-command-shell-for-ubuntu-debian-suse-redhat-linux-etc/#:~:text=Ctrl%2BY%3A%20Paste%20the%20last,you%20cut%20from%20the%20clipboard.

Table of Contents
=================

* [Shell Shortcut](#shell-shortcut)
* [Table of Contents](#table-of-contents)
* [Context](#context)
   * [Controls](#controls)
      * [Ctrl+c](#ctrlc)
      * [Ctrl+z](#ctrlz)
      * [Ctrl+d](#ctrld)
      * [Ctrl+[s/q]](#ctrlsq)
   * [Move in command line](#move-in-command-line)
      * [Ctrl+[a/e]](#ctrlae)
      * [Ctrl+[f/b]](#ctrlfb)
      * [Alt+[f/b]](#altfb)
   * [Edit in command line](#edit-in-command-line)
      * [Ctrl+h](#ctrlh)
      * [Alt+d](#altd)
      * [Alt+t](#altt)
      * [Ctrl+[k/u]](#ctrlku)
      * [Ctrl+y](#ctrly)
   * [History](#history)
      * [Ctrl+r](#ctrlr)
      * [Ctrl+o](#ctrlo)
      * [Ctrl+g](#ctrlg)
   * [Fish-only shortcut](#fish-only-shortcut)
      * [Alt+[e/v]](#altev)
      * [Alt+c](#altc)
      * [Alt+l](#altl)
      * [Alt+w](#altw)

Created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc)

# Context
Mostly bash shell shortcuts mixed with some fish shell shortcuts.
My current working shell is `fish, version 3.3.1`
which support most of shortcuts in bash shell

## Controls

### `Ctrl+c`
- Interrupt current process by sending `SIGINT` signal to process

### `Ctrl+z`
- Suspend current process by sending `SINGTSTP` signal to process
- Continue process by `fg` command

### `Ctrl+d`
- Close bash shell by sending `EOF` marker to shell

### `Ctrl+[s/q]`
- Stop/Resume all output to terminal screen

## Move in command line

### `Ctrl+[a/e]`
- Move to end/beginning of the line

### `Ctrl+[f/b]`
- Move to next/prev character

### `Alt+[f/b]`
- Move to next/prev word

## Edit in command line

### `Ctrl+h`
- Delete prev character (same as backspace)

### `Alt+d`
- Delete till end of line

### `Alt+t`
- Swap current word with previous word

### `Ctrl+[k/u]`
- Cut till the end/beginning of the line

### `Ctrl+y`
- Yank (paste) cut contents

## History

### `Ctrl+r`
### `Ctrl+o`
### `Ctrl+g`

## Fish-only shortcut

### `Alt+[e/v]`
- Open external editor to edit command

### `Alt+c`
- FZF fuzzy finder

### `Alt+l`
- List all directories

### `Alt+w`
- Short help on previous command