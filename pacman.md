# Pacman
Arch's package manager. The flags aren't very obvious, so here are the most common ones.

### Install a package
* `sudo pacman -S <package-name>`

### Remove a package
* `sudo pacman -Rns <package-name>`
This will remove the package, its dependencies, and all config files.

### Upgrade your system
1. `sudo pacman -Syy` - this will first update the repositories
2. `sudo pacman -Syu` - actually upgrade all installed packages.

Guide: https://kaosx.us/docs/pacman/
