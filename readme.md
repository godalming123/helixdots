# HelixDots

My [helix](https://github.com/helix-editor/helix) dotfiles.

# Installation

## Install helix

> [!NOTE]
> These dotfiles require [macro keybindings](https://helix-editor.com/news/release-25-01-highlights/#macro-keybindings), which are only available on helix 25.01 and newer.

### From a package manager

See [here](https://docs.helix-editor.com/package-managers.html).

### From source

#### Install rust (if not already installed)

```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

#### Download helix source code

```
git clone https://github.com/helix-editor/helix.git
cd helix
```

#### Compile helix from source

```
cargo install --path helix-term --locked
ln -Ts $PWD/runtime ~/.config/helix/runtime
```

## Install the dotfiles

```
git clone https://github.com/godalming123/helixdots.git ~/.config/helix
```

# My thoughts on helix

## General

- I like how everything needs much less configuration, for example git integrations are setup out of the box
- It feels like my editor is helping me as I go like auto suggesting commands
- In helix I have to type more letters but the command is more memorable EG: `vgld` in helix vs `D` in neovim (https://github.com/helix-editor/helix/issues/165)

## Appearance

- The file picker does not have rounded corners, unlike telescope in neovim
- Git signs look much nicer than they do in neovim
- The status bar looks nicer than it does in neovim
- Helix includes good themes out of the box, but neovim does not
- LSP diagnostics are placed either below the line of code or in the top right corner, both of which are easier to see than neovim where they are crammed after the lines of code

## Writing text

- The LSP is slightly better in helix than it is in neovim

## Editing text

- I like being able to use x and X to quickly make visual line selections
- Multiple cursors is a really useful feature that vim/neovim needs a plugin for, but helix has out-of-the-box:
  - This makes using find/replace much easier since helix shows you exactly what you're doing as you do it, rathor than having to remember a regex command in vim/neovim to do find/replace

## Navigating text

- I think both helix and neovim do a good job of this

## Sometimes PRs that that make objective improvements take their time to get merged

- Add a way to only show the horizontal or vertical position in statusline ([ISSUE](https://github.com/helix-editor/helix/discussions/10282), [PR](https://github.com/helix-editor/helix/pull/10883))

## Missing some functionality

- Show the context of the currently visible buffer ([ISSUE](https://github.com/helix-editor/helix/issues/396), [PR](https://github.com/helix-editor/helix/pull/6118))
- Compositor components key remapping for picker:
  - Be able to save a picker item to the jumplist without leaving the picker ([ISSUE](https://github.com/helix-editor/helix/issues/12822))
  - Be able to create multiple cursors from picker items
  - Be able to scroll the picker preview
  - Be able to revert git changes from the git changes picker
- Muli cursor across multiple buffers ([ISSUE](https://github.com/helix-editor/helix/issues/4335), [PR](https://github.com/helix-editor/helix/pull/4381#issuecomment-1382831419))
- Be able to undo/redo motions/selections ([DISCUSSION](https://github.com/helix-editor/helix/discussions/12905))
- Be able to effectively jump across projects and files within projects:
  - Code cannot be folded ([ISSUE](https://github.com/helix-editor/helix/issues/1840))
  - The jumplist cannot have directories in it
  - The jumplist cannot be saved across multiple sessions
  - You cannot set a keybinding that opens items from the jumplist directly
    - This could work by changing `Ctrl-s`, so that you also specify a keybinding for the item that gets created in the jumplist
    - Then, from any file in that project, you would be able to press `Ctrl-j + that keybinding` to jump straight there
    - One keybinding (maybe space) could be reserved to specify that the jumplist item does not have a keybinding associated with it
    - Maybe these jumplist items without keybindings associated could also be tempoarary, and the items with keybindings would be saved across helix sessions
  - You cannot remove items from the jumplist without exiting the session ([ISSUE](https://github.com/helix-editor/helix/issues/4757))
    - Compositor components key remapping: My preferred solution to this would be to have a keybinding to delete the selected item from the jumplist picker
- `]d` does not work with multi cursor ([ISSUE](https://github.com/helix-editor/helix/issues/12906))
- There isn't a register for the absolute path of the document ([ISSUE](https://github.com/helix-editor/helix/issues/12881), [PR](https://github.com/helix-editor/helix/pull/12887))
- The behavior of the `repeat_last_motion` command (`alt-.`) is unintuative ([ISSUE](https://github.com/helix-editor/helix/issues/8761#issuecomment-1803145453))
- When you search for things, helix should show how many results there are ([ISSUE](https://github.com/helix-editor/helix/issues/2811))
- Be able to hide the blankline below the status bar when it is empty ([DISCUSSION](https://github.com/helix-editor/helix/discussions/10818), [PR](https://github.com/helix-editor/helix/pull/12204))
- Some of these issues are marked with "compositor components key remapping", because it might might be good to implement key remapping for compositor components first ([ISSUE](https://github.com/helix-editor/helix/issues/5505))

### Things that will probably get solved with plugins ([plugins discussion](https://github.com/helix-editor/helix/discussions/3806), [plugins PR](https://github.com/helix-editor/helix/pull/8675))

- No git diff viewer integration ([ISSUE](https://github.com/helix-editor/helix/issues/227))
- No undotree
