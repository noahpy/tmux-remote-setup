
# Tmux Remote Setup
This repo provied a setup script / guide for installing and configuring tmux with nvim.
It is a relatively minimal setup, that the user can extend on.
This setup installs plugins such that one can navigate between panes with Ctrl+[H,J,K,L].
Installation commands may vary depending on the distribution.
The respective config file can be found in the configs folder.

## Quick Start
You can simply enter the cloned repo and run:
```
./setup.sh && source ~/.bashrc
```
If you want to run the commands manually, follow the setup guide below.

## Setup Guide
### Neovim
Install [neovim](https://github.com/neovim/neovim)
```
sudo apt install neovim
```
Install [vim-plug](https://github.com/junegunn/vim-plug) for neovim:
```
curl -fLo ~/.local/share/nvim/site/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```
Copy the neovim config:
```
cp <PATH_TO_REPO>/configs/neovim/init.vim ~/.config/nvim/init.vim
```
Install plugins:
```
nvim -c PlugInstall
```

### Tmux
Install [tmux](https://github.com/tmux/tmux)
```
sudo apt install tmux
```
Install [tmux plugin manager](https://github.com/tmux-plugins/tpm)
```
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```
Copy the tmux config file from this repo:
```
cp <PATH_TO_REPO>/configs/tmux.conf ~/.config/tmux/tmux.conf
```
Then source it:
```
tmux source ~/.config/tmux/tmux.conf
```
To install the plugins run:
```
tmux
```
And then execute <prefix>+I (prefix default is Ctrl-b).
Aliasing (also done in bashrc):
```
alias tmux="tmux -f ~/.config/tmux/tmux.conf"
```

### Bashrc
Extend the default bashrc :
```
cat <PATH_TO_REPO>/configs/bashrc-extend.sh >> ~/.bashrc
```

