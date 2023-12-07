# dired.nvim

A file browser inspired from Emacs Dired for neovim.

## Screenshots

![output](https://user-images.githubusercontent.com/24680989/216357118-d7d1ecaf-b7bd-4894-9b5e-1c71f40e0dc3.gif)

Different types of files in dired.nvim
![Screenshot from 2023-02-02 20-16-20](https://user-images.githubusercontent.com/24680989/216356401-ae181f74-2aee-434d-9ef6-abdb23ec29e2.png)
![Screenshot from 2023-02-02 20-15-57](https://user-images.githubusercontent.com/24680989/216356422-43a7f103-e82a-4d29-bf90-3278f61866f4.png)



## Installation

Requires [Neovim 0.6](https://github.com/neovim/neovim/releases/tag/v0.6.0) or
higher.

```lua
use {
    "X3eRo0/dired.nvim",
    requires = "MunifTanjim/nui.nvim",
    config = function()
        require("dired").setup {
            path_separator = "/",
            show_banner = false,
            show_hidden = true,
            show_dot_dirs = true,
            show_colors = true,
        }
    end
}
```

### Setup
You can require this plugin and use it like this.
```lua
require("dired").setup {
    path_separator = "/",
    show_banner = false,
    show_hidden = true
    keybinds = {
        dired_enter = "<cr>",
        dired_back = "-",
        dired_up = "_",
        dired_rename = "R",
        dired_create = "d",
        dired_delete = "D",
        dired_delete_range = "D",
        dired_copy = "C",
        dired_copy_range = "C",
        dired_copy_marked = "MC",
        dired_move = "X",
        dired_move_range = "X",
        dired_move_marked = "MX",
        dired_paste = "P",
        dired_mark = "M",
        dired_mark_range = "M",
        dired_delete_marked = "MD",
        dired_toggle_hidden = ".",
        dired_toggle_sort_order = ",",
        dired_toggle_colors = "c",
        dired_toggle_hide_details = "(",
        dired_quit = "q",
    }
}
```

## Usage

Run the command `:Dired` to open a buffer for your current
directory. Press `-` in any buffer to open a directory buffer for its parent.
Editing a directory will also open up a buffer, overriding Netrw.

Inside a directory buffer, there are the following keybindings:
* `<CR>`: Open the file or directory at the cursor.
* `d`   : Create new directories and files.
* `M`   : Mark directories and files (both in normal and visual mode).
* `C`   : Copy files.
* `X`   : Move files.
* `P`   : Paste files in current directory.
* `D`   : Delete directories and files (both in normal and visual mode).
* `R`   : Rename directories and files.
* `MD`  : Delete marked files.
* `MC`  : Copy marked files.
* `MX`  : Move marked files.
* `-`   : Open parent directory.
* `.`   : Toggle show_hidden.
* `,`   : Change sort_order.
* `c`   : Toggle colors

## TODO

1. Allow changing file permissions.
