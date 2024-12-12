# HelixDots

My [helix](https://github.com/helix-editor/helix) dotfiles.

# Installation

## Install the dotfiles

```
git clone https://github.com/godalming123/helixdots.git ~/.config/helix
```

## Install rust (if not already installed)

```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

## Install helix

```
git clone https://github.com/helix-editor/helix.git
cd helix
cargo install --path helix-term --locked
ln -Ts $PWD/runtime ~/.config/helix/runtime
```

# My thoughs on helix

## General

- I like how everything needs much less configuration, for example git integrations are setup out of the box
- It feels like my editor is helping me as I go like auto suggesting commands
- In helix I have to type more letters but the command is more memorable EG: `vgld` in helix vs `D` in neovim (https://github.com/helix-editor/helix/issues/165)

## Appereance

- The file picker does not have rounded corners
- Git signs look much nicer
- The status bar looks nicer
- Helix includes good themes out of the box
- LSP diagnostics are placed in the top right corner which makes them much easier to see than vim/neovim where they are crammed after the lines of code

## Writing text

- The LSP is slightly better in helix than it is in vim/neovim

## Editing text

- I like being able to use x and X to quickly make visual line selections
- Multiple cursors is a really useful feature that vim/neovim needs a plugin for, but helix has out-of-the-box:
  - This makes using find/replace much easier since helix shows you exactly what you're doing as you do it, rathor than having to remember a regex command in vim/neovim to do find/replace

## Navigating text

- I think both helix and neovim do a good job of this

## Sometimes PRs that that make objective improvements take their time to get merged

- Add a way to only show just the horizontal or vertical position in statusline ([ISSUE](https://github.com/helix-editor/helix/discussions/10282) [PR](https://github.com/helix-editor/helix/pull/10883))

## Missing some functionality

- Be able to jump across projects/files within projects effectively:
  - Code cannot be folded ([ISSUE](https://github.com/helix-editor/helix/issues/1840))
  - The jumplist cannot have directories in it
  - The jumplist cannot be saved across multiple sessions
  - You cannot remove items from the jumplist without exiting the session ([ISSUE](https://github.com/helix-editor/helix/issues/4757))
- When you search for things helix should show how many results their are (https://github.com/helix-editor/helix/issues/2811)
- Be able to hide the blankline below the status bar when it is empty (https://github.com/helix-editor/helix/discussions/10818)

### Things that will probably get solved with plugins ([plugins discussion](https://github.com/helix-editor/helix/discussions/3806) [plugins PR](https://github.com/helix-editor/helix/pull/8675))

- No git diff viewer integration (https://github.com/helix-editor/helix/issues/227)
- No undotree
