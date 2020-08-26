# nlua.nvim

Lua Development for Neovim

## Required Plugins

You should install the following plugins.


```vim
" Obviously install this plugin...
Plug 'tjdevries/nlua.nvim'

" If you want to use built-in LSP (requires Neovim HEAD)
"   Currently only supported LSP, but others could work in future if people send PRs :)
Plug 'neovim/nvim-lsp'
Plug 'nvim-lua/completion.nvim'

" This is required for syntax highlighting
Plug 'euclidianAce/BetterLua.vim'

" TODO: Making your Lua Folds as tidy as a nice Manilla Folder 
Plug 'tjdevries/manillua.nvim'
```

## Example Completions

![ExampleCompletions](./media/example_completions.png)


## TODO:

https://github.com/bfredl/nvim-luadev

- [x] `gf` should work with `require` and other items
- [x] Set `path` correctly for lua.
    - [ ] See if we can get `checkpath` to work.
        - It seems like it should, but not sure how to make that happen
        - I think this requires some understanding of `suffixesadd`
- [~] `K` should figure out if you're:
    - on a vim.fn style function
    - on a vim.api style function
    - on a vim.$something function
    - or on a lua built-in style function
    - Status:
        - It works when you write out the full names... but that doesn't seem super great
        - Kind of words when you type the whole name, but could have name clashes? Not clear.
- [ ] Add a `completion.nvim` source for currently available globals.
    - This won't be as good as something like sumneko, because that does actual analysis.
        But it could be good for finding all the things in `vim.api.*` etc.
- [ ] `include` should handle all the crazy ways you can make strings in lua.
- [ ] better text object support
    - Consider trying this out w/ tree sitter at some point...
- [ ] Add some "switch to test file" or other kind of thing
    - Could use projections, could use alternate.vim, ...?
- [ ] Set up for lua-formatter, cause that's really nice.
    - [x] Check if sumneko can do lua formatting...
        - Not currently supported as far as I can see
    - [ ] Add a "hack" for tempfile (opt-in) that formats the whole file, but we just replace the stuff we want to replace correctly. Could probably work... 90%ish time? We'd have to see.
