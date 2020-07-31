# CentOs 7 Step-By-Step

#### Fri, 31st July, 2020

## 1. Update & upgrade
```bash
> sudo yum -y update && sudo yum -y upgrade
```

## 2. Remap Capslock to Ctrl

```bash
# either in .bashrc or .zshrc
> vi .bashrc

# type in the following command
> setxkbmap -option "ctrl:nocaps"

> source .bashrc # or .zshrc
```

## 3. Configure common settings

```bash
# install dnf
~ sudo yum -y install dnf

# Logout and login 
> gnome-session-quit
```

## [4. Configure repository >>](./system/repos)

Then, we can install `ntfs-3g` to mount NTFS filesystem.

```bash

# install `ntfs-3g`
~ sudo dnf -y install epel-release
~ sudo dnf -y install ntfs-3g

```

## [5. Change to zsh shell >>](./system/shell)

## [6. Add `menuentry` for Windows 7 >>](./system/menuentry)

## [7. Configure httpd >>](./webserver/httpd)

## [8. Configure PHP >>](./lang/php)

## [9. Configure MySQL 5.7 >>](./db/mysql57)

## [10. Others](./others/ceratropic)
