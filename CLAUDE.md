# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A GitHub Pages site (`https://rueckerconsult.github.io/`) hosting seven arcade games as browser games. Pure static HTML — no build system, no dependencies, no framework. A `.nojekyll` file disables Jekyll processing.

## Structure

- `index.html` — arcade landing page linking to the four games
- `pacman/index.html` — Pac-Man (1980): tile-based maze, four ghosts with classic scatter/chase targeting (Blinky/Pinky/Inky/Clyde), power pellets, ghost house logic
- `space-invaders/index.html` — Space Invaders (1978): 5×11 formation, destructible pixel shields, UFO, accelerating march
- `asteroids/index.html` — Asteroids (1979): vector-style ship physics, splitting rocks, saucer
- `frogger/index.html` — Frogger (1981): lane-based traffic/river, logs and turtles, five home slots, timer
- `tekken/index.html` — "Iron Fist", a Tekken-style fighter: best-of-3 rounds, punch/kick/block with startup/active/recovery frames, vs-CPU AI or local 2-player
- `bonk/index.html` — "Bonk Arena", a Megabonk/Vampire-Survivors-style roguelite: infinite scrolling arena, 5 levelable auto-attacking weapons (orbit hammers, thrown hammers, lightning, aura, boomerang), 7 passives, XP gems, level-up choices, scaling hordes and bosses, floating virtual joystick for mobile
- `shooter/index.html` — "Wave Gunner 3D", a comic-style first-person shooter with a software raycasting engine (DDA over a grid map, z-buffered billboard sprites, distance fog, parallax sky): scaling waves with multi-boss waves every 5th, 6 hitscan/projectile weapons found in chests/drops, shrines granting random blessings, powerup drops (nuke, insta-kill, double damage, rapid fire, freeze, medkit), crits, hitmarkers, 3D-projected damage numbers, gravity-based blood particles, pointer-lock mouse look with pitch (y-shearing), twin-touch mobile controls with on-screen fire button, fullscreen mode on mobile, exploding chain-reaction barrels, day/dusk/night sky cycle, multikill banners, minimap

Each game is a single self-contained HTML file: inline CSS and one inline `<script>` rendering to a `<canvas>`. Shared conventions across all games: a `snd()` WebAudio beep helper (audio context lazily created on first input), `requestAnimationFrame` loop with delta-time capped at 50 ms, a `state` string machine (`start` / `play` / `gameover` plus game-specific states), keyboard + touch input, hi-scores in `localStorage` (`<game>-hi` keys), German UI text.

## Commands

No build, lint, or test tooling. To preview locally: `python3 -m http.server` and open `http://localhost:8000`.

To syntax-check a game's script: extract the inline `<script>` body to a file and run `node --check` on it.

## Conventions

- Keep games dependency-free and self-contained in their own directory.
- UI copy is German; code identifiers and comments are English.
- Don't add a `CNAME` file or change the Pages publishing setup without confirmation.
