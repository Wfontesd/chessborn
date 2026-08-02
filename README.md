# Chessborn — playable web build

**▶ Play: https://wfontesd.github.io/chessborn/**

Chess where every piece carries its own history. Each piece holds a stable army
slot and earns XP from the captures *it* makes, across the duels of a
tournament — reaching a mandatory class choice at level 2 and mastery at
level 3. Progression persists between duels and across sessions.

It is real 8×8 chess underneath: castling, en passant, promotion, king-safety
filtering, checkmate and stalemate. The rules engine matches published perft
values on the standard, Kiwipete, en-passant and promotion positions.

## About this repository

This repo contains **only the exported web build**. It is generated output —
do not edit it by hand. The Godot 4.7 source lives in a separate private
repository.

## How it is built

Exported from Godot 4.7 with the `Web` preset, with **thread support
disabled**. That matters: Godot web builds that use threads require
`SharedArrayBuffer`, which needs `Cross-Origin-Opener-Policy` and
`Cross-Origin-Embedder-Policy` headers. GitHub Pages cannot set custom
headers, so the single-threaded template is what makes this playable here at
all.

```
godot --headless --path <source> --export-release "Web" build/web/index.html
```

`.nojekyll` is present so GitHub Pages serves the files as-is rather than
running them through Jekyll.

## Controls

Mouse, or fully keyboard-operable: arrow keys move the board cursor,
Enter/Space selects and plays, Escape clears a selection, Tab reaches the
command buttons. The board exposes per-square screen-reader descriptions.

It is hot-seat — you play both sides. There is no AI opponent yet.
