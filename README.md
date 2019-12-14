This is a workaround to make Jupyter Lab's vim mode use my own Dvorak-compatible keybindings, e.g. navigation with htns rather than hjkl. Also works with the jupyterlab-vim extension.

To use this: Overwrite all the CodeMirror vim.js files with the new-vim.js in this repo (renaming new-vim.js to vim.js). There are multiple files like this. To overwrite all files that happen to be named 'vim.js': `find / -name 'vim.js' -exec echo cp ./new-vim.js "{}" \;` Make sure you're not screwing anything up (every vim.js should be inside a directory `codemirror/keymap/`), then rerun without that `echo` to actually do it. Then rebuild Jupyter Lab, by running `jupyter lab build`.

Remappings:
* `hjkl` -> `htns`
* `HJKL -> `HTNS`
* Default `s` and `S` bindings in normal and visual mode removed (no
  substitutes)
* `^` and `$` have `H` and `S` as aliases; `H` for moveToTopLine has been removed, no substitutes
* In a search, `k` jumps to next match, instead of `n`
* `;` now does the same thing as `:`

