# HelixDots
My helix editor dotfiles.

# My thoughs on helix
## General
- I like how everything needs much less configuration as things such as git integration are setup out of the box
- It feels like my editor is helping me as I go like autosuggesting commands
- In helix I have to type more letters but the command is more memorable EG: vgld in helix vs D in neovim (https://github.com/helix-editor/helix/issues/165)

## Appereance
- The file picker does not have rounded corners
- Git signs looks much nicer
- Status bar looks nicer
- Helix includes good themes out of the box
- I like how LSP diagnostics are placed in the top right corner making them much easier to see

## Writing text
- The LSP is slightly better

## Editing text
- I like being able to use x and X to quickly make visual line selections
- Using find and replace is much easier as helix shows me exactly what I'm doing as I do it and I generally love using multiple cursors

## Navigating text
- I think both helix and neovim do a good job of this

## Missing some functionality
- I cannot set global tab size options (https://github.com/helix-editor/helix/issues/3159)
- The jumplist cannot be saved across multiple sessions
- You cannot remove items from the jumplist without exiting the session (https://github.com/helix-editor/helix/issues/4757)
- When you search for things helix should show how many results their are (https://github.com/helix-editor/helix/issues/2811)
- There should be an error when formatting fails (https://github.com/helix-editor/helix/issues/6736)
- I want to be able to hide the blankline below the status bar
### Things that will probably get solved with plugins (https://github.com/helix-editor/helix/discussions/3806)
- No git diff viewer integration (https://github.com/helix-editor/helix/issues/227)
- No undotree
### Problems with my file tree
- There should be 3 panes
- There should be a search to filter the list
- There should only be one key to open files *and* directories
- You should be able to move multiple lines (EG: `5j`)
- When you navigate to the previous directory, the cursor should be moved to the entry for the previous directory
