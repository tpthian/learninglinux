[\[back\]](../)

# Change SHELL

Change SHELL from `bash` to `zsh`

```bash
~ sudo dnf -y install zsh
~ sudo chsh -s /bin/zsh [user]
~ gnome-session-quit
~ echo $SHELL

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

