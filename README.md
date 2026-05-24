# vim-pi-complete

A simple Neovim plugin that mimics Cursor's selection prompt and Zed's editor assist feature using the pi coding agent's non-interactive mode.

## Pi as your LLM

Currently, the plugin expects `pi` to be installed and ready to use. The arguments this extension sends are the prompt and the read-only tool list, and it sets the thinking level to minimal for speed.

## How to use

Select a visual block, line, or selection, and then type `:Pi <your prompt here>`. The selection will be replaced with the model's output.
You can give any kind of prompt, but the agent has no edit tools, so it can only reply with the new text, and it is instructed to do so.
There is no visual feedback on submit, but if an error occurs, you will see it.

Just select, prompt, and send. Then hope for the best. Each prompt is its own individual session; there is no continuation, though you can resume from pi itself.

## How to install

This plugin uses the standard Neovim plugin layout, so it should work with any plugin manager. Make sure the external `pi` executable is installed and available on Neovim's `$PATH`.

### lazy.nvim / LazyVim

Add a plugin spec like this:

```lua
-- ~/.config/nvim/lua/plugins/pi-complete.lua
return {
  "sacenox/vim-pi-complete",
  cmd = { "Pi" },
}
```

For local development, use `dir` instead:

```lua
return {
  dir = "~/src/vim-pi-complete",
  cmd = { "Pi" },
}
```

Note: when lazy-loading with `cmd = { "Pi" }`, the lowercase `:pi` abbreviation is only available after the plugin has loaded. Use `:Pi` to trigger loading, or define the abbreviation in `init`:

```lua
return {
  "sacenox/vim-pi-complete",
  cmd = { "Pi" },
  init = function()
    vim.cmd([[cabbrev pi Pi]])
  end,
}
```

### Native packages

Without a plugin manager:

```bash
cd ~/.config/nvim/pack/local/start
git clone https://github.com/sacenox/vim-pi-complete.git
```

Then restart Neovim.
