# Fedora DNF
- Dandified Yum (DNF) is package manager for RPM distro
- References
    - https://docs.fedoraproject.org/en-US/quick-docs/dnf-system-upgrade/
    - https://docs.pagure.org/copr.copr/how_to_enable_repo.html
    - https://dnf-plugins-core.readthedocs.io/en/latest/copr.html
    - https://docs.fedoraproject.org/en-US/modularity/installing-modules/
    - https://dnf.readthedocs.io/en/latest/command_ref.html#repoquery-command-label
    - https://docs.fedoraproject.org/en-US/Fedora/23/html/System_Administrators_Guide/sec-Managing_DNF_Repositories.html

Table of Contents
=================

* [Fedora DNF](#fedora-dnf)
* [Table of Contents](#table-of-contents)
* [Context](#context)
   * [DNF Basic](#dnf-basic)
   * [DNF Advanced](#dnf-advanced)
      * [DNF History](#dnf-history)
      * [DNF Group](#dnf-group)
      * [DNF Repository](#dnf-repository)
      * [DNF COPR](#dnf-copr)
      * [DNF Module](#dnf-module)
   * [DNF System Upgrade](#dnf-system-upgrade)

Created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc)

# Context

## DNF Basic
- List all installed packages:
    - `dnf list installed`
- Search package name (no regrex support):
    - `dnf search <fuzzy_package_name>`
- Search package provides input package name:
    - `dnf provides <package_name>`
- Check package detailed information:
    - `dnf info <package_name>`
- Install package (root authentication is needed):
    - `dnf install <package_name>`
- Uninstall package (root authentication is needed):
    - Uninstall package:
        - `dnf remove <package_name>`
    - Uninstall but skip unused packages removal:
        - `dnf remove --no-autoremove`
    - Auto-remove non-dependent packages_name:
        - `dnf autoremove`
    - Clean package installation packet and other cache:
        - `dnf clean all`
- Update RPM package:
    - Check changelog of RPM package:
        - `dnf changelog <package_name>`
    - Check update:
        - `dnf check-update --refresh`
    - Update (root authentication is needed):
        - `dnf update`
    - Update but skip specific package:
        - `dnf update --exclude <package_name>`
- Downgrade RPM package (root authentication is needed):
    - `dnf downgrade <package_name`

## DNF Advanced

### DNF History
History command/index of DNF

- List DNF history with command and index:
    - `dnf history`
- Rollback to step in DNF history with index:
    - `dnf history rollback <history_ID>`

### DNF Group
Group packed package

- List available groups:
    - `dnf grouplist`
- Check group detailed information (quotation is needed for group name):
    - `dnf group info <group_name>`
- Install group (root authentication is needed):
    - `dnf group install <group_name>`
- Uninstall group (root authentication is needed):
    - `dnf group remove <group_name>`
- Update group (root authentication is needed):
    - `dnf groupupdate`

### DNF Repository
Repository for DNF, where packages are stored

- Manipulate DNF repository:
    - List all repository:
        - `dnf repolist`
    - Add repository (root authentication is needed):
        - `dnf config-manager --add-repo <repository_url>`
    - Enable repository (root authentication is needed):
        - `dnf config-manager --set-enabled <reposity_name>`
    - Disable repository (root authentication is needed):
        - `dnf config-manager --set-disabled <reposity_name>`
- Advanced search in repository:
    - List all available package in repository:
        - `dnf repoquery`
    - List multiple versions of package:
        - `dnf repoquery --show-duplicates`
    - List packed files in the package:
        - `dnf repoquery --list <package_name>`
    - List unsatisfied dependency of package:
        - `dnf repoquery --unsatisfied`
    - List required dependency (one-line) for package:
        - `dnf repoquery packages_name> --requires`
    - List all dependency and packages provides them (detailed) for package:
        - `dnf repoquery <packages_name> --deplist`
    - List package dependency (forward dependency, including requires/recommends/suggests)
        - `dnf repoquery <package_name> --depends`
    - List package dependency requirement for package
        - `dnf repoquery --whatrequires <package_name>`
    - List package dependency (reverse weak dependency, including requires only)
        - `dnf repoquery --whatsupplements <package_name>`

### DNF COPR
Cool Other Package Repo (COPR), repository hosted by other users

- Search COPR:
    - `dnf copr search <project_name>`
- Enable COPR (root authentication is needed):
    - `dnf copr enable <user_name/project_name>`

### DNF Module
- List all module:
    - `dnf module list`

## DNF System Upgrade
Upgrade Fedora system with dnf e.g. (F34 -> F35)

1. Install dnf-plugin-system-upgrade (root authentication is needed):
    - `dnf install dnf-plugin-system-upgrade`
2. Download needed data (root authentication is needed):
    - `dnf install system-upgrade download --releasever=<Fedora_version>`
3. Reboot and start upgrade system (root authentication is needed):
    - `dnf system-upgrade reboot`
