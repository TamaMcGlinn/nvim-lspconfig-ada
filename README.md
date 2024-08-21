# Ada language server LSP config

This configures [ALS](https://github.com/AdaCore/ada_language_server) to work with [LSP-config](https://github.com/neovim/nvim-lspconfig). 
The latter project has decided to no longer accept changes to the als.lua config, hence this plugin just copied that file and fixes it.
See the [discussion here](https://github.com/neovim/nvim-lspconfig/pull/1693) about removing server specifics.

Once installed, your `:LSPInfo` will show what GPR project is being used, and also an error if none is found.

You might also want to install [nvim-lsp-gpr-selector](https://github.com/TamaMcGlinn/nvim-lsp-gpr-selector)
to be able to select (and fuzzy search) gpr projects to use.

# Installation

### Using vim-plug

Add the following line to your init.vim or init.lua file within the plug call block:

```vim
Plug 'TamaMcGlinn/nvim-lspconfig-ada'
```

Then, run :PlugInstall in NeoVim to install the plugin.

### Using lazy.nvim

In your init.lua, add the following snippet:

```lua
require("lazy").setup({
    { "TamaMcGlinn/nvim-lspconfig-ada" },
})
```
