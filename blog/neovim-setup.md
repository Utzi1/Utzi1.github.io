# Getting Started with Neovim

**Posted:** 2026-05-14

Neovim is a modern fork of Vim that maintains backward compatibility while adding powerful new features. Here's how to get started.

## Installation

### macOS
```bash
brew install neovim
```

### Ubuntu/Debian
```bash
sudo apt install neovim
```

### From Source
```bash
git clone https://github.com/neovim/neovim.git
cd neovim && make CMAKE_BUILD_TYPE=Release && sudo make install
```

## Basic Configuration

Create your config file at `~/.config/nvim/init.vim` (or `init.lua` for Lua config):

```lua
-- Basic settings
vim.opt.number = true          -- Show line numbers
vim.opt.relativenumber = true  -- Relative line numbers
vim.opt.expandtab = true       -- Use spaces instead of tabs
vim.opt.shiftwidth = 2         -- 2 spaces per indent
vim.opt.tabstop = 2            -- Tab displays as 2 spaces
```

## Essential Keybindings

| Action | Command |
|--------|---------|
| Enter insert mode | `i` |
| Exit insert mode | `Esc` |
| Save file | `:w` |
| Quit | `:q` |
| Search | `/pattern` |
| Replace | `:%s/old/new/g` |

## Plugin Management

Use a plugin manager like **vim-plug** or **packer.nvim**:

### With vim-plug
```bash
curl -fLo ~/.local/share/nvim/site/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

Then in `init.vim`:
```vim
call plug#begin()
Plug 'nvim-treesitter/nvim-treesitter'
Plug 'nvim-lualine/lualine.nvim'
call plug#end()
```

## Next Steps

- Explore plugin ecosystems
- Customize your theme
- Learn advanced motions
- Join the Neovim community

---

[← Back to Blog](index.md) | [← Home](../index.md)
