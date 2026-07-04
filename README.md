# No More Orphans

No More Orphans is an ARK: Survival Ascended ArkApi plugin that automatically captures a player's current shoulder pet into a cryopod during the server-transfer flow.

The goal is simple: fewer forgotten shoulder pets when players travel between maps. This build does not scan open inventories or capture just because a player opens a transmitter; it hooks the transfer confirmation/upload server path instead.

Version 0.45 registers several transfer/upload hook points for Wildcard update compatibility. If transfer capture still fails, send the server log line that starts with `NoMoreOrphans transfer trigger fired:`.

## Included Files

- `NoMoreOrphans.dll`
- `PluginInfo.json`
- `config.json`
- `README.md`
- `LICENSE`

## Requirements

- ARK: Survival Ascended dedicated server
- ArkApi installed
- Super Cryo Storage installed when `CaptureMode` is set to `SCS`
- Vanilla cryopods, PCS-style cryopods, or another compatible cryopod item blueprint when `CaptureMode` is set to `Cryo`

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

No player or admin commands are registered by this build.

## Features

- Captures the player's current shoulder pet during the transfer-server process
- Supports Super Cryo Storage mode
- Supports vanilla/PCS-style cryopod mode through a configurable cryopod blueprint path
- Supports temporary vanilla cryopods that can be removed after the dino is released
- Does not scan open inventories
- Does not use loot-drop toggles or player commands
- Configurable capture mode, blueprint paths, cooldown, and messages

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

`CaptureOnTransferButton` controls whether No More Orphans captures when the transfer-server confirmation dialog opens.

## License

No More Orphans is copyright (c) 2026 Michael Henderson, also known as Chong,
and published under Safe Mode Software. It is released for personal, private,
non-commercial use only. You may install and use it for personal use, but you
may not distribute modified copies, share repackaged versions, or profit from it
without prior written permission.

See `LICENSE` for the full terms.
