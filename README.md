# Mac Setup

My personal configuration files and system dependencies for a complete Mac development environment.

## Includes
- **Shell**: Zsh + Starship + Plugins (autosuggestions, highlighting, vi-mode, fzf-tab)
- **Terminal**: Ghostty
- **Multiplexer**: Tmux (vim-tmux-navigator, vi copy mode)
- **Editor**: Neovim (config tracked separately in `~/.config/nvim`)
- **Fuzzy Finder**: fzf + fzf-tab (fuzzy completions, Ctrl+R history, Ctrl+T file picker)
- **Modern CLI**: eza (aliased to `ls`, `ll`, `la`)
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
- **Plugins included**:
  - `tmux-plugins/tpm`: Plugin manager
  - `egel/tmux-gruvbox`: Dark theme
  - `tmux-plugins/tmux-prefix-highlight`: Visual indicator for prefix key
- Press `Prefix + I` in tmux to install plugins.
- **Navigation**: Uses vim-tmux-navigator for seamless Ctrl+hjkl between tmux panes and Neovim splits.
- **Copy mode**: vi-style with `v` to select, `y` to yank to system clipboard.
- **Clipboard**: OSC 52 (`set -s set-clipboard on`) for clipboard pass-through over SSH.

### 3. Ghostty
- Link the config: `mkdir -p ~/Library/Application\ Support/com.mitchellh.ghostty/ && ln -s ~/mac-setup/ghostty/config ~/Library/Application\ Support/com.mitchellh.ghostty/config`

### 4. Starship
- Link the config: `ln -s ~/mac-setup/starship/starship.toml ~/.config/starship.toml`

### 5. Zsh
- Link the config: `ln -s ~/mac-setup/zsh/zshrc ~/.zshrc`
- **Plugins**: zsh-autosuggestions, zsh-syntax-highlighting, zsh-vi-mode, fzf, fzf-tab
- **Aliases**: `ls`/`ll`/`la` are mapped to `eza` with icons and git status
- **fzf-tab**: Fuzzy tab completions with eza previews for `cd`
- Note: This setup sources `~/.local.zshrc` for machine-specific configs not tracked in git.
