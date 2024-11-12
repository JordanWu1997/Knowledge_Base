# Fedora flatpak

- Flatpak is an application for linux application sandboxing
- References
  - https://github.com/flatpak/flatpak

# Table of Contents

- [Fedora flatpak](#fedora-flatpak)
- [Context](#context)
  - [Flatpak Basic](#flatpak-basic)
    - [Flatpak Local](#flatpak-local)
    - [Flatpak remote](#flatpak-remote)

Created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc)

# Context

## Flatpak Basic

### Flatpak Local

- Search package name
  - `flatpak search <package_name>`
- List all installed packages
  - `flatpak list`
- Install package system (default)
  - `flatpak install --system <package_name>`
- Install package user
  - `flatpak install --user <package_name>`
- Run package
  - `flatpak run <full_package_name>`
- Update all installed package
  - `flatpak update`
- Uninstall package
  - `flatpak uninstall <package_name>`
- Uninstall all unused packages
  - `flatpak uninstall --unused`

### Flatpak remote

- List configured remote repositories programs
  - `flatpak remote-ls`
- List configured remote repositories
  - `flatpak remotes`
- Add remote repository
  - `flatpak remote-add <remote_repository`
- Delete remove repository
  - `flatpak remote-delete`
