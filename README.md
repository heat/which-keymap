# which-keymap

A browser-based cheat sheet for two-keystroke IntelliJ keymaps, with a
which-key.nvim-inspired layout and a Catppuccin Mocha theme.

**Live demo:** https://heat.github.io/which-keymap/

## What it does

- Loads an IntelliJ `<keymap>` XML and groups every two-chord shortcut by
  its first-keystroke prefix (`Ctrl+B`, `Ctrl+D`, …).
- Each group is rendered as a panel with rows of the form `[key] → action`,
  with alternate keystrokes (e.g. `Ctrl+1` vs `1`) dimmed on the right.
- A hero search filters by action, mnemonic, or shortcut text.
- A capture mode lets you press a real keyboard shortcut and the list
  narrows to matching rows — like "Find Action by Shortcut" in IntelliJ.
- OS toggle swaps modifier names/glyphs between Win/Linux and macOS.
- Loads the default Mnemonic Keymap from
  [dmimat/intellij-mnemonic-keymap](https://github.com/dmimat/intellij-mnemonic-keymap)
  on first open; you can also point it at any other keymap XML URL or paste
  one in.

## Local development

It's a single static `index.html`. Open it directly in a browser, or serve
it with anything:

```sh
python3 -m http.server 8000
# or
npx serve .
```

Tailwind CSS is loaded via the Play CDN (`cdn.tailwindcss.com`) so there
is no build step. For production, replace the CDN script with a proper
Tailwind build:

```sh
npx tailwindcss -i input.css -o output.css --minify
```

The color palette and semantic aliases live inside the inline
`tailwind.config = { ... }` block at the top of the file.

## Deploy to GitHub Pages

1. Push to GitHub (see below).
2. In the repository **Settings → Pages**, pick **Deploy from a branch**,
   branch `main`, folder `/ (root)`.
3. The site goes live at `https://<user>.github.io/which-keymap/`.

## Credits

- Keymap data: [dmimat/intellij-mnemonic-keymap](https://github.com/dmimat/intellij-mnemonic-keymap)
- UI inspiration: [folke/which-key.nvim](https://github.com/folke/which-key.nvim)
- Palette: [Catppuccin](https://github.com/catppuccin/catppuccin)

## License

MIT
