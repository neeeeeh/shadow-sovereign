# 暗影君临 / Shadow Reign

Playable mobile-first HTML5 idle action RPG, version 0.1.0. Original dark fantasy characters, environments, and synthesized audio. Static ES modules with Canvas 2D rendering; no runtime dependencies or server-side save data.

## Run

Serve `dist` with a static HTTP server. The hosted project uses the static directory in `.openai/hosting.json`. Open `index.html` through HTTP rather than the filesystem because the game uses ES modules.

## Play

Tap **进入地下城** to unlock audio and enter combat. Movement and attacks are automatic. Basic skills can be automatic or manual; **君王领域** is manual and requires full rage. The top-right expansion control switches between battle with management and immersive battle. 1×/2× changes simulation speed.

- Hunter: allocate four stats and promote E through Monarch ranks.
- Equipment: drops, five rarities, one-tap best loadout, enhancement and low-tier salvage.
- Skills: unlock at levels 1, 3 and 10; level 5 adds piercing energy, five-hit assassination or domain restraint.
- Shadows: first guaranteed extractions after floors 3, 6 and 10. Independently acting melee guard, rushing wolf and piercing ranged mage. Train with crystals and evolve with duplicate marks. Formation capacity grows at floors 6, 10, 20, 35 and 50; later extra slots add duplicate reinforcement actors.
- Dungeons: three waves per floor, elites every 3 floors, boss every 5, altar resources every 7. New illustrated regions each 10 floors; courtyard wolves inflict bleeding, library casters use a second-height projectile. Regions repeat after four chapters while numeric difficulty continues.
- Boss: delayed aimed ground slam, phase-two ritual that heals and summons unless interrupted with skill/critical damage; enraged shockwave projectiles.
- Awakening: level 10 and floor 10 unlock a three-wave trial. Completion grants 25% attack/health, 10 stat points, crystals and formation capacity.
- Abyss: repeatable increasingly difficult challenge from floor 15.

A defeat retains all earned progression and retries. Floor completion restores part of health. The dungeon panel can hold a floor for farming.

## Persistence

`shadow-reign-save-v1` in localStorage, saved every five seconds and on lifecycle changes. Previous serialized save retained as backup. Saves include profile, skill levels, equipment, inventory, shadows, formation, wave/floor and offline timestamp. Offline settlement grants gold, XP and crystals, capped at 8 hours, without advancing floors. Export/import JSON via Settings enables manual cross-device backup. There is no account/cloud sync.

## Source layout

- `dist/state.js`: data, balance curves, inventory, stat calculations and persistence.
- `dist/engine.js`: combat state machines, actor timing, projectiles, AI and Canvas rendering.
- `dist/ui.js`: touch interface, settings, management and lifecycle.
- `dist/audio.js`: original procedural score and effects.
- `dist/icons.js`: consistent original SVG icon set.
- `dist/assets`: generated original illustrations and sprite atlases.
- `check-core.mjs`: focused headless core-loop smoke check, using the production engine and state functions.

## Current scope

One playable hunter, three ordinary enemy families and one boss family. Three illustrated locations plus a throne palette variation, three shadow types, endless stat scaling and repeatable challenges. This first version does not include multiplayer, payments, a native Android package or a large authored story campaign.
