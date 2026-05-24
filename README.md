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

I know there are many package managers, so please use any that you know. If I need to make changes to support one, file an issue or PR.

Here's how to do it without a package manager:

```bash
cd ~/.config/nvim/pack/local/start
git clone <this repo>
```

Then restart Neovim.
