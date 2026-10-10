# Arcade games

Every `.zip` in this folder shows up automatically on the Arcade page (`arcade.html`).

**Only shareware and freeware.** This repository is public, so anything here is shared with the world.

## Adding a game

1. Upload the game's `.zip` to this folder (on GitHub: *Add file → Upload files*).
2. That's it. The Arcade guesses which program to start.

## Optional: settings for every device

If a game needs a different start program or speed, add it to `games.json`:

```json
{
  "games": [
    { "file": "doom1.zip", "title": "Doom (shareware)", "exe": "DOOM.EXE", "speed": "fast" },
    { "file": "heretic.zip", "title": "Heretic (shareware)", "speed": "fast" },
    { "file": "tyrian2000.zip", "title": "Tyrian 2000" }
  ]
}
```

- `file`: the zip's exact file name
- `title`: name on the shelf
- `exe`: path inside the zip, e.g. `DOOM.EXE` or `GAME/START.BAT`
- `speed`: `auto`, `fast` (3D games), `slow` (very old games), or `custom` with `"cycles": 3000`

## On-screen controls (phone and tablet)

On a touch screen the Arcade shows a D-pad (arrow keys) and a few buttons. The 🎮 button
in the player bar switches them on or off. Without settings you get Space, Enter and Esc.
To give a game its own buttons, add `buttons` to its entry in `games.json`:

```json
{ "file": "skyroads.zip", "title": "SkyRoads",
  "buttons": [
    { "label": "Jump", "key": "Space", "big": true },
    { "label": "Enter", "key": "Enter" },
    { "label": "Esc", "key": "Esc" }
  ] }
```

Key names: `Space`, `Enter`, `Esc`, `Tab`, `Backspace`, `Up`, `Down`, `Left`, `Right`,
`PageUp`, `PageDown`, `Shift`, `Ctrl`, `Alt`, `F1`–`F10`, or any single letter or digit.

## CD games

Put the CD's files in a folder called `CD` at the top of the zip. The Arcade mounts it as drive D:.
CD music tracks can't be included, so those games run without their soundtrack.
