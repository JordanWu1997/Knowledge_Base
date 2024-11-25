# My Knowledge_Base

Place that stores my knowledge and shares it to everyone else.

- This repository is actually a backup for my [vimwiki](https://github.com/vimwiki/vimwiki) files.
  - For the note directory structures, you can check [./index.md](./index.md) (generated and read by vimwiki)
  - My personal favored usage is [neovim](https://github.com/neovim/neovim) + [my_vim_customization](https://github.com/JordanWu1997/Vim_Tmux_Config) + [vimwiki](https://github.com/vimwiki/vimwiki) (vim dominates!)
- Note that this repository contains lots of __unfinished note draft__ (but still updating)

## Wiki File Structure

- `Wiki`
  - `index.md`
  - `diary`
    - `2024-01-01.md`
    - ...
  - `resources`
    - `template`
    - `image`
      - `image_01.jpg`
    - `video`
      - `video_01.mp4`
    - ...
  - `notes`
    - `project 1`
      - `note_01.md`
      - `note_02.md`
      - `idea_03.md`
    - `project 2`
    - ...

## Rules

### Naming

- Filename should not contain any spaces and dots, use underscore to replace them
- Wiki-related directory should start with lowercase characters
  - e.g. `diary`, `resources`, `notes` etc.
- User-created filename/directory should start with uppercase characters
  - e.g. `project 1`, `project 2`

### Storing

- Notes should be stored under `notes` directory and organized into projects or topics
- Files that are __NOT__ notes should be stored under `resources` directory
- Files inside `resources` should be organized by their properties like image, video etc.

### Linking

- Use direct file reference e.g. \[README\](./README.md) instead of markdown note linking e.g. \[[README]\]
  - Then when you move your notes here and there, you can use vim-wiki to update link for you
- When linking notes, use __relative path__ for vim-wiki link interconnection adaptivity
  - Same reason as above one
- When linking other files that are not notes, use __relative path__ e.g. `[image](./resources/image/Communication_and_Interfaces_in_the_OSI_model.png)`
  - Normally, files that are not notes should all just stay in `resources` directory under wiki root directory
  - Here I don't use absolute path or vimwiki link since they breaks on Github pages or difference host machines
    - But the links will break on GitHub pages or different host machines
  - However, if you don't care about GitHub pages or just take note on single local machine
    - You can still use absolute path, but note that additional `/`/ must be inserted before absolute file path to prevent confusion with internal link

### Formatting

- https://github.com/executablebooks/mdformat
- https://github.com/sbdchd/neoformat

### Language Checking

- https://languagetool.org/
- https://github.com/dpelle/vim-LanguageTool/tree/master

### Publishing

- Use `pandoc` to export markdown note file and embed resources to HTML file
