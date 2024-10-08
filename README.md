# Ada language server LSP config

This configures [ALS](https://github.com/AdaCore/ada_language_server) to work with [LSP-config](https://github.com/neovim/nvim-lspconfig). 
The latter project has decided to no longer accept changes to the als.lua config, hence this plugin just copied that file and fixes it.
See the [discussion here](https://github.com/neovim/nvim-lspconfig/pull/1693) about removing server specifics.

Once installed, your `:LSPInfo` will show what GPR project is being used, and also an error if none is found.

## Note:

You need nvim-lspconfig >= 0.2 (which is not yet released).
In the mean time, switch from [neovim/nvim-lspconfig](https://github.com/neovim/nvim-lspconfig/)
to [TamaMcGlinn/nvim-lspconfig](https://github.com/TamaMcGlinn/nvim-lspconfig/). Otherwise,
autocomplete and find-references will not work, and, depending on which version of nvim-lspconfig you have,
you may get an error message about als being deprecated.

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

# Configuration

We recommend you also install [nvim-lsp-gpr-selector](https://github.com/TamaMcGlinn/nvim-lsp-gpr-selector)
to be able to select (and fuzzy search) gpr projects to use. In that case, all you need to enable the language
server is this in your init.lua:

```lua
require'lspconfig'.als.setup{}
```

An alternative way of setting the gpr project and environment is to pass a "settings" object to `als.setup{}`:

```lua
require('lspconfig').als.setup{
    settings = {
      ada = {
        projectFile = "project.gpr";
        scenarioVariables = { ... };
      }
    }
}
```
