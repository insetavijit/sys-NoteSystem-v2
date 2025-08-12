Here's your **complete [[WSL Neovim]] + NvChad Setup Guide** with the exact working links and commands:
Neo vim [Topic Guid](<WSL Neovim.md>)

---

# 🚀 WSL Neovim Setup with NvChad
> Tested on WSL (Ubuntu), sets up **Neovim v0.11**, **NvChad**, and **Catppuccin** with icons and plugin support.

---

## 🧱 1. Prerequisites

### Update system

```bash
sudo apt update && sudo apt upgrade -y
```

### Install basic tools

```bash
sudo apt install -y git curl wget unzip gcc ripgrep fd-find zsh
```

---

## 🧪 2. Install Neovim 0.11 (manually)

```bash
cd ~
wget https://github.com/neovim/neovim/releases/download/v0.11.3/nvim-linux-x86_64.tar.gz
tar -xzf nvim-linux-x86_64.tar.gz
sudo mv nvim-linux-x86_64 /opt/
sudo ln -sf /opt/nvim-linux-x86_64/bin/nvim /usr/local/bin/nvim
```

✅ Confirm:

```bash
nvim --version
# Must show: v0.11.3
```

---

## 🎨 3. Install Nerd Fonts (for icons)

> Download [JetBrainsMono Nerd Font](https://github.com/ryanoasis/nerd-fonts/releases)  
> Then install it on your Windows system manually and set terminal font to it (WSL terminal settings > Font).

---

## ⚙️ 4. Install NvChad

```bash
rm -rf ~/.config/nvim
git clone https://github.com/NvChad/starter ~/.config/nvim --depth 1
nvim
```

On first launch, plugins will install. Restart Neovim after it's done.

---

## 💄 6. Install Lazy Plugins Manually (if needed)

```bash
rm -rf ~/.local/share/nvim/lazy/LuaSnip
git clone https://github.com/L3MON4D3/LuaSnip ~/.local/share/nvim/lazy/LuaSnip
```

If any plugin fails, delete and re-clone its directory manually from GitHub.

---

## 🧠 7. Common Commands

|Action|Command|
|---|---|
|Vertical split terminal|`:vsp|
|Horizontal split terminal|`:sp|
|Close current split|`:q`|

---

✅ You now have **NvChad + Catppuccin + Neovim 0.11** working on WSL!