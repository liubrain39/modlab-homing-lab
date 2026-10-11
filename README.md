# ModLab Homing Lab 0.1.0

A free, reproducible game-modding example from [ModLab — independent Universal Modder guides](https://modlabguides.online/).

**[Follow the Universal Modder tutorial and see the recorded test](https://modlabguides.online/workshop/mindustry-homing)** · **[Install Universal Modder](https://modlabguides.online/guides/install-universal-modder)**

A small single-player Mindustry mod, created with Codex and the Universal Modder workflow. Mindustry's official JSON content API supplies both turrets and their real bullet physics. This ZIP includes the editable source and original geometric turret sprites.

**[Free mod ZIP on itch.io](https://modlab-guides.itch.io/modlab-homing-lab)** · **[Watch the recorded lab on YouTube](https://www.youtube.com/watch?v=2ClBd7utWY8)**

The video is a montage of actual game-window captures, with English captions; it is not a continuous 24 fps recording.

## Requirements and cost

- Mindustry **160.7**, desktop. Verified on macOS 15.7, Apple M1 Max, the official itch.io Mac download with bundled Java 25.0.1.
- The author offers Mindustry free at https://anuke.itch.io/mindustry — select Download Now, then "No thanks, just take me to the downloads". Steam is a separate paid distribution; it is not required.
- No account, API key, paid assets, external mod loader, Java installation or coding agent is needed to run this ZIP. A coding agent may charge usage fees if you choose to rebuild or edit with AI.
- The supplied ZIP was tested in a clean profile. See https://modlabguides.online/workshop/mindustry-homing for current recorded results.

## Find this mod in-game

In Mindustry **160.7**, choose **Mods → Mod Browser**, search **ModLab**, then open **ModLab Homing Lab**. The detail page shows the Universal Modder description and **Install**, **Repo**, and **View Releases** controls.

We verified the search result and detail page on macOS 15.7 on October 11, 2026. We have not tested a fresh installation through the Mod Browser. Use the ZIP method below for the installation route we reproduced in a clean profile.

## Install and open

1. Back up existing Mindustry data. Use a fresh lab profile if you already play.
2. Choose **Mods → Open Folder**, quit the game, and copy this ZIP into that mods folder. Keep it zipped.
3. Launch the game again. The alternative **Mods → Import Mod → Import File** is built in, but our Mac file picker did not open; use the tested folder-copy method if that occurs.
4. From the main menu, choose **ModLab Homing Lab [F8]**, or press F8 (some Macs need Fn+F8).
5. The local arena supplies copper automatically. The left turret fires straight; the right has homingPower 0.08. A 30-second run counts launches and target damage events.
6. F8 restarts the temporary arena. F9 exits. Save and exit any other game before opening this lab. The lab refuses to replace another active world or run while connected to a server.

## Recorded result

On the documented macOS / Mindustry 160.7 setup, a 30-second run recorded **1 hit / 25 launches** for the straight lane and **24 hits / 25 launches** for the homing lane. The supplied ZIP was reproduced in a clean profile. These counts describe this controlled steering demonstration, not ordinary-game balance or a result guaranteed on other systems. [Read the verification record](evidence/mindustry-verification.json).

## What the comparison means

Both lanes have the same moving targets, fixed aim point, speed 2.7, damage 12, lifetime 105 ticks, reload 70 ticks and no splash. Guidance is the variable under test; color is only a label. Targets have extra health and scripted movement. The arena is a steering demonstration, **not a normal-game damage benchmark**. Counts can vary with engine timing. Try the turrets in a separate sandbox for normal automatic targeting.

`content/blocks/baseline.json` sets homingPower to 0. `content/blocks/homing.json` sets it to 0.08. `homingRange: 200` is in world units (25 tiles); `homingDelay: 8` is in simulation ticks. The helper script creates the arena and reports real engine events. It does not manufacture hit results.

## Edit one value

Extract the ZIP to a new folder, edit `content/blocks/homing.json`, then zip **the files inside the folder** so mod.json is at the ZIP root. With the game closed, replace the old ZIP in the mods folder, restart and compare. Keep the baseline unchanged. Suggested first experiment: homingPower 0.02 versus 0.08. These are experiment values, not guaranteed results on every build.

## Remove and recover

Press F9, then disable or remove **ModLab Homing Lab** in Mods and restart. Your ordinary game should open without the ModLab menu item. This demonstration does not save a campaign or overwrite an existing map. The optional `modlab-last-run.json` in the data folder is only a result log. For existing worlds that contain the new turrets, return to a backup created before installing the mod.

## File map

- `mod.json`: metadata
- `content/blocks/*.json`: two editable turrets and bullet definitions
- `scripts/main.js`: one-click local laboratory; F8/F9 controls; result log
- `sprites/*.png`: original ModLab geometric sprites

## Sources and licensing

Mindustry official modding guide: https://mindustrygame.github.io/wiki/modding/1-modding/
Mindustry v160.7 source: https://github.com/Anuken/Mindustry/tree/v160.7
Universal Modder revision used: 8370faa8e114baf33acdb23079aff552a7728c4b
This mod's original code and geometric sprites are MIT licensed. No game binaries or extracted game assets are included. Mindustry and Universal Modder are separate projects; ModLab is not affiliated with them.

