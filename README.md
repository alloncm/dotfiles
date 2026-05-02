# My dotfiles

## Install 

```bash
# Install tools and deps
sudo apt install tmux
sudo apt install xclip
sudo snap install alacritty --classic
sudo apt install fzf

# Append our .bashrc configs
grep -qF '.bashrc.d' ~/.bashrc || cat >> ~/.bashrc << 'EOF'

# Load user configs
if [ -d "$HOME/.bashrc.d" ]; then
    for file in "$HOME/.bashrc.d"/*; do
        [ -f "$file" ] && source "$file"
    done
fi
EOF


# Install stow
sudo apt install stow

# At the repo root run:
stow -t ~/ */
```