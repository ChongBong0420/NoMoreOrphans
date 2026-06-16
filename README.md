# No More Orphans

No More Orphans is an ARK: Survival Ascended ArkApi plugin that automatically captures a player's current shoulder pet into an SCS pod or vanilla cryopod when the player opens configured transmitter-style inventories.

The goal is simple: fewer forgotten shoulder pets when players use transmitters, terminals, obelisks, and other configured inventory targets.

## Included Files

- `NoMoreOrphans.dll`
- `PluginInfo.json`
- `config.json`
- `README.md`
- `LICENSE`

## Requirements

- ARK: Survival Ascended dedicated server
- ArkApi installed
- Super Cryo Storage installed on the server when `CaptureMode` is set to `SCS`

## Install

Create this folder if it does not already exist:

```text
ShooterGame/Binaries/Win64/ArkApi/Plugins/NoMoreOrphans/
```

Place the included files in that folder:

```text
NoMoreOrphans/
  NoMoreOrphans.dll
  PluginInfo.json
  config.json
  README.md
  LICENSE
```

Restart the server after installing or replacing the plugin files.

## Player Command

Players can use this chat command to toggle whether No More Orphans should also work on loot drops for them:

```text
/nmodrops
```

This toggle is per player and does not require admin permissions.

## Config

Use `CaptureMode` to choose the capture type:

```json
"CaptureMode": "SCS"
```

or:

```json
"CaptureMode": "Cryo"
```

When `CaptureMode` is `Cryo`, `TemporaryVanillaCryopods` controls whether vanilla cryopods created by No More Orphans are removed after the dino is successfully uncryoed.

By default, loot drops are disabled globally:

```json
"AllowLootDrops": false
```

Players who want loot-drop behavior can toggle it for themselves with `/nmodrops`.

## License

No More Orphans is copyright (c) 2026 Michael Henderson, also known as Chong,
and published under Safe Mode Software. It is released for personal, private,
non-commercial use only. You may install and use it for personal use, but you
may not distribute modified copies, share repackaged versions, or profit from it
without prior written permission.

See `LICENSE` for the full terms.
