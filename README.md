# Stashdown.nvim - A Lightweight Markdown Note Taking Tool for Neovim

## Install

To install stashdown.nvim, you can use either Neovim's built-in package manager or clone the repository directly.

### Using Neovim's Package Manager
1. If you're using Neovim 0.9 or later with Lua support installed:
```bash
lua -c 'print(require("plug"))'
```
2. Clone this plugin and add it to your Neovim configuration:
```bash
git clone https://github.com/yourusername/stashdown.nvim.git
~/.config/nvim/pluginSTALL --source git@github.com:yourusername/stashdown.nvim.git
```

### Requirements
- Neovim 0.9 or later with Lua support
- Modern version of Lua

## Key Features

- **Create New Files**: Quickly create new markdown files with titles and timestamps
- **Insert Images**: Add images to your notes with automatic file naming and organization
- **Archive Notes**: Automatically move notes to an archive directory when they're done
- **Markdown Support**: Built-in support for creating and editing markdown formatted notes

## Usage

Basic commands available through Neovim's input interface:

1. Create new note:
```bash
:call stashdown#setup "nf"
```

2. Insert image:
```bash
:call stashdown#insert_image "ii"
```

3. New entry in current buffer:
```bash
:call stashdown#new_entry "ne"
```

4. Archive file:
```bash
:call stashdown#archive_file "a"
```

## Configuration

While not strictly required, you can configure the plugin by editing your Neovim configuration file:

```lua
vim.fn(u) -- Lua function to be implemented
```

## Documentation

Here are the main functions available in stashdown.nvim:

- `new_file`: Creates a new markdown file with title and metadata
- `new_entry`: Adds a new entry to the current buffer with date formatting
- `insert_image`: Handles image file location and organization
- `archive_file`: Archives notes into defined directory structure
- `copy_file`: Auxiliary function for file copying (not directly user-facing)

## Example Workflows

1. Create a note:
```bash
:call stashdown#setup "nf"
```

2. Add an image to your note:
```bash
:call stashdown#insert_image "ii"
```

3. When done with the note:
```bash
:call stashdown#archive_file "a"
```

This plugin provides a flexible yet lightweight way to manage your markdown notes directly within Neovim.
