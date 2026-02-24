# Mac Setup

My personal configuration files and system dependencies for a complete Mac development environment.

## Includes
- **Shell**: Zsh + Starship + Plugins (autosuggestions, highlighting, vi-mode)
- **Terminal**: Ghostty
- **Multiplexer**: Tmux
- **Editor**: Neovim (config tracked separately in `~/.config/nvim`)
- **Packages**: Managed via Homebrew (`Brewfile`)

## Installation

### 1. Homebrew & Packages
First, install Homebrew and all required packages (including Zsh plugins, Tmux, etc.):
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
cd ~/mac-setup
brew bundle
```

### 2. Tmux
- Link the config: `ln -s ~/mac-setup/tmux/tmux.conf ~/.tmux.conf`
- Install TPM: `git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm`
- Press `Prefix + I` in tmux to install plugins.

### 3. Ghostty
- Link the config: `mkdir -p ~/Library/Application\ Support/com.mitchellh.ghostty/ && ln -s ~/mac-setup/ghostty/config ~/Library/Application\ Support/com.mitchellh.ghostty/config`

### 4. Starship
- Link the config: `ln -s ~/mac-setup/starship/starship.toml ~/.config/starship.toml`

### 5. Zsh
- Link the config: `ln -s ~/mac-setup/zsh/zshrc ~/.zshrc`
- Note: This setup sources `~/.local.zshrc` for machine-specific configs not tracked in git.
