# No More Orphans

No More Orphans is an ARK: Survival Ascended ArkApi plugin for servers using Super Cryo Storage. It automatically places a player's current shoulder pet into an SCS pod when the player opens configured transmitter-style inventories.

The goal is simple: fewer forgotten shoulder pets when players use transmitters, terminals, obelisks, and other configured inventory targets.

## Included files

- `NoMoreOrphans.dll`
- `NoMoreOrphans.dll.arkapi`
- `PluginInfo.json`
- `config.json`
- `LICENSE`

## Requirements

- ARK: Survival Ascended dedicated server
- ArkApi installed
- Super Cryo Storage installed on the server

## Install

Create this folder if it does not already exist:

```text
ShooterGame/Binaries/Win64/ArkApi/Plugins/NoMoreOrphans/
```

Place the included files in that folder:

```text
NoMoreOrphans/
  NoMoreOrphans.dll
  NoMoreOrphans.dll.arkapi
  PluginInfo.json
  config.json
  LICENSE
```

Restart the server after installing or replacing the plugin files.

## Player command

Players can use this chat command to toggle whether No More Orphans should also work on loot drops for them:

```text
/nmodrops
```

This toggle is per player and does not require admin permissions.

## Config

The included `config.json` controls whether the plugin is enabled, which inventories are treated as valid targets, whether loot drops are allowed by default, cooldown timing, SCS blueprint paths, and player loot-drop preferences.

By default, loot drops are disabled globally:

```json
"AllowLootDrops": false
```

Players who want loot-drop behavior can toggle it for themselves with `/nmodrops`.

## License

No More Orphans is released for personal/private non-commercial use under the included license.

Copyright (c) 2026 Michael Henderson.
Also known as Chong.
Published by Safe Mode Software.
