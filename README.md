# SKYBREAKER 蒼穹雷霆

9:16 vertical arcade shooter. Static Canvas 2D application; no build step or dependencies. Deploy `dist/`.

## Files
- `dist/index.html`: Traditional Chinese UI, overlays and desktop pilot handbook.
- `dist/style.css`: responsive cabinet, mobile full-height layout and settings.
- `dist/game.js`: game loop, collision, three sectors and bosses, seeded procedural terrain, cached aircraft sprites, original Web Audio soundtrack and sound effects.
- `.openai/hosting.json`: Sites identity and static deployment directory.

## Controls
- WASD / arrows, or relative pointer dragging: movement; Shift: slow precision movement.
- Automatic fire; B / Space / on-screen button: bomb; P / Escape: pause.
- Casual mode: five lives and slower bullets; standard mode: three lives.
- Each sector has 43 seconds of waves followed by a boss. Clear all three to win.

## Data and sound
Only the best score and audio/motion preferences persist locally under `skybreaker-v1`. No account, server database, network gameplay, external soundtrack or copyrighted game assets. All aircraft and terrain are original Canvas drawings. Audio unlocks after a user gesture. If local storage is blocked, gameplay remains available without persistent records. Optional web fonts have system fallbacks.

## Preview
In the managed environment use `sites-preview start /workspace/sites/skybreaker`. Outside it, serve `dist` with any static HTTP server.

## Maintenance
Gameplay lives in `game.js`; `sectors`, `spawnWave`, `bossFire`, `update` control progression, patterns and difficulty. `AudioEngine` generates the soundtrack. Native canvas resolution is 540×960. Animation uses elapsed time with a bounded frame delta; effects and bullet arrays are cleaned every frame. Collision uses a 9px player hit radius indicated by the central dot.

## Limitations
Single player only; no cloud saves, online leaderboard, offline service worker or native installer. Best score is shared across both difficulty modes and stored on the current browser only. Fullscreen support depends on the browser. Touch drag requires one finger; the other can tap the bomb button.
