# CentOs 7 Step-By-Step

#### Fri, 31st July, 2020

## 1. Update & upgrade
```bash
> sudo yum -y update && sudo yum -y upgrade
```

## 1.1 Remap Capslock to Ctrl
```bash
# either in .bashrc or .zshrc
> vi .bashrc

# type in the following command
> setxkbmap -option "ctrl:nocaps"

> source .bashrc # or .zshrc
```

## 2. Configure common settings
```bash
# install dnf
> sudo yum -y install dnf

# Logout and login 
> gnome-session-quit

# Install repositories
> sudo yum -y install yum-plugin-priorities 
> sudo yum -y install epel-release 
> sudo yum -y install centos-release-scl-rh centos-release-scl 
> sudo yum -y install http://rpms.famillecollet.com/enterprise/remi-release-7.rpm 

# install vim-enhanced
```

## 2. Change to zsh shell
```bash
> sudo dnf -y install zsh
> sudo chsh -s /bin/zsh [user]
> gnome-session-quit
> echo $SHELL

# make sure wget and git are installed
> dnf install -y wget git

# start installing oh-my-zsh
wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh

# edit .zshrc
> vi .zshrc 

# type the remapping command
~ setxkbmap -option "ctrl:nocaps" # then :wq to save and quit vim
~ source .zshrc
```


