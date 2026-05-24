# vim-pi-complete

A simple Neovim plugin to mimic Cursor's selection prompt and Zed's editor assist feature using the pi coding agent's Non-Interactive mode.

## Pi as your LLM

Currently the plugin expects `pi` to be installed and ready to use. 

## How to use

Select a visual block/line/selection and then type `:Pi <you prompt here>`. The selection will be replaced with the model's output.
You can give any kind of prompt, but the agent has no edit tools, so it can only reply with the new text, and it's instructed to do so.
There is no visual feedback on submit, but if an error happens you will see it.

Just select, prompt and send. Then hope for the best. Each "prompt" is it's own individual session, there is no continuation (you can resume from pi itself).

## How to install

I know there are many package managers, so please use any that you know, and if I need to make changes to support it, file an issue or PR.

Here's how to do it without any package manager:

```bash
cd ~/.config/nvim/pack/local/start
git clone <this repo>
```

And restart your nvim :D
