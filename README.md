# Stashdown.nvim - A Lightweight Markdown Note Taking Tool for Neovim

## Install

Using lazy.nvim allows us to manage the plugin. Use the following lazy config:

```lua
{
    "msyke/stashdown.nvim",
    config = function()
        local sd = require('stashdown')
        sd.setup()
    end,
    keys = {
        {
            "<leader>sdn",
            "<cmd>:Stashdown nf<CR>",
            mode = { "n" },
            desc = "Create a new stashdown markdonw file",
        },
        {
            "<leader>sde",
            "<cmd>:Stashdown ne<CR>",
            mode = { "n" },
            desc = "Create a new entry in the current markdown file",
        },
        {
            "<leader>sda",
            "<cmd>:Stashdown a<CR>",
            mode = { "n" },
            desc = "Archive the current file and all associated images",
        },
        {
            "<leader>sdi",
            "<cmd>:Stashdown ii<CR>",
            mode = { "n" },
            desc = "Insert an image into the current note file. Move the image into a folder associated with this note.",
        },
    },
}
```

### Requirements

- Neovim 0.9 or later with Lua support

## Key Features

- **Create New Files**: Quickly create new stashdown formatted markdown files with titles and timestamps
- **Insert Images**: Add images to your notes with automatic file naming and organization
- **Archive Notes**: Automatically move notes to an archive directory when they're done

## Usage

Basic commands available through Neovim's input interface, or in lua

1. Create new note:

Vim Command:
```bash
:Stashdown nf
```

Lua:
```lua
local sd = require("stashdown.nvim")
sd.new_file(file_name, doc_title)
```

2. Insert image:

Vim Command:
```bash
:Stashdown ii
```

Lua:
```lua
local sd = require("stashdown.nvim")
sd.insert_image(buff_num)
```

3. New entry in current buffer:

Vim Command:
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
