# Sofle layout tuned for Neovim (`nvim-optimized` branch)

This branch tweaks [config/sofle.keymap](../config/sofle.keymap) to match heavy **Neovim** use alongside your `~/.config/nvim` setup (Space leader, Ctrl window nav, Alt buffer index, F-keys for split resize).

## Base layer (thumb cluster)

| Left (outside → inside) | Center | Right (inside → outside) |
|-------------------------|--------|---------------------------|
| **GUI** | | |
| **Alt** | | **Alt** |
| **Ctrl** | | |
| **Space** | **Lower** / **Raise** | **Enter** |
| | | **Space** |
| | | **GUI** |

Changes from `main`:

1. **Inner-left Ctrl** — fixes duplicate **Alt**; matches the printed diagram and makes **Ctrl+h/j/k/l** (window focus) easier with **Ctrl** under the left thumb and letters on the right hand.
2. **Second Space** (replaces Shift+Space macro) — Neovim **leader is Space**; a Space under the right thumb makes **leader + key** sequences natural when the left thumb is on **Lower/Raise** or **Enter**.

## What stays on the matrix (your nvim habits)

| Neovim chord | Keyboard |
|--------------|----------|
| `<Space>` leader | Either thumb **Space** |
| `<C-hjkl>` windows | **LCTRL** (pinky **or** thumb) + **HJKL** |
| `<S-h>`, `<S-l>` buffers | **Shift** (outer pinky keys) + **H** / **L** |
| `<A-1>` … `<A-0>`, `<A-p>` | **Alt** (thumbs) + number row |
| `<A-S-h>`, `<A-S-l>` (Barbar move) | **Alt** + **Shift** + **H** / **L** |
| `<F5>`–`<F8>` split resize | **Lower** layer: **F5**–**F8** on the top row |

## Lower layer

- **F1–F12** on rows 1–2 (F12 on inner right of row 2) for function keys and tooling.
- **Symbols** row: `~ = - + { } [ ] ; : \` for coding / shell.
- **A** key (home row, same position as base **A**): **tmux prefix** `Ctrl+B` macro while **Lower** is held (if you use tmux alongside nvim). Left Shift on Lower stays transparent to the base Shift binding.
- **Pipe** `|` and **F11** on the right side of row 3.

## Raise layer

Unchanged: Bluetooth, arrows, edit shortcuts (undo/cut/copy/paste), **Alt/Ctrl/Shift** taps for combos that do not conflict with nvim when you momentarily switch layers.

## Encoders

Default: volume and **PgUp/PgDn** — handy for scrolling docs or popups without leaving the home row.

## Optional next steps (not in this branch)

- **Home-row mods** (hold `A` = Ctrl, etc.) — powerful but needs tuning to avoid misfires.
- **Dedicated “Code” layer** with `&kp LC(H)` … if you want window keys without nvim mappings (only useful outside nvim).
- Pin **ZMK revision** in `config/west.yml` for reproducible CI builds.

## Flash / build

Use your existing GitHub Actions workflow or local ZMK build; shield targets are unchanged (`sofle_left` / `sofle_right`).
