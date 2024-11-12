# Knowledge_Base

Place that stores my knowledge and shares it to everyone else.

- This repository is actually a  backup for my [vimwiki](https://github.com/vimwiki/vimwiki) files.
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
    - `01.jpg`
    - `02.mp4`
    - ...
  - `project 1`
    - `topic 1`
      - `note_1.md`
    - `topic 2`
      - `note_2.md`
    - `idea_3.md`
  - `project 2`
  - ...

## Rules

### Naming

- Filename should not contains any spaces and dots, use underscore to replace them
- Wiki-related directory should start with lowercase characters
  - e.g. `diary`, `resources`
- User-created filename/directory should start with uppercase characters
  - e.g. `project 1`, `project 2`

### Storing

- Files that are __NOT__ notes should be stored under `resources` directory
- The `resources` directory should __NOT__ contains any subdirectories

### Linking

- Use direct file reference `[note](rel_path_to_note)` instead of markdown note linking `[[note]]`
  - Then when you move your notes here and there, you can use vim-wiki to update link for you
- When linking notes, use __relative path__ for vim-wiki link interconnection adaptivity
  - Same reason as above one
- When linking other files that are not notes, use __absolute path__ `[file](abs_path_to_file)`
  - Normally, they should all just stays in `resources` directory under wiki root directory

### Publishing

- Use `pandoc` to export markdown note file and embed resources to HTML file
