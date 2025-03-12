# stashdown.nvim

A Lightweight Markdown Note Taking Tool for Neovim. The idea behind this plugin is to mirror the
functionality of the ill-fated note taking app stashpad. Instead of running it in a separate appliaction
though, here it's a part of your neovim editor editing simple markdown files. When in a notes file,
simply invoke the new entry functionality and you'll have a timestamped note created with insert mode
ready to input text.

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

Basic commands available through Neovim's command interface, or in lua

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
:Stashdown ne
```

Lua:

```lua
local sd = require("stashdown.nvim")
sd.new_entry(buff_num)
```

4. Archive currently open file:

Vim Command:

```bash
:Stashdown a
```

Lua:

```lua
local sd = require("stashdown.nvim")
sd.archive_file()
```
