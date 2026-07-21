# No More Orphans

No More Orphans is an ARK: Survival Ascended ArkApi plugin that captures a player's current shoulder pet into an SCS pod or vanilla cryopod during the transfer-server flow.

It does not scan open inventories or capture just because a player opens a transmitter. It waits for the transfer confirmation/upload server path before trying to capture the shoulder pet.

Version 0.56 keeps the same transfer-button behavior as the pre-update build and carries the ASA 91.17 / ASA Server API 2.01 compatibility fix for transfer captures. It avoids the broken `AShooterPlayerController.GetPlayerInventoryComponent()` offset by adding captured pods through the live character inventory field, and it resolves the player character through the controller pawn path. Temporary vanilla cryopods are marked by the plugin, cleanup now starts at 3 seconds instead of immediately hammering the inventory, and the plugin forces an item refresh after adding a generated vanilla cryopod to help the client rebuild the cryopod display.

Download:
[ChongBong0420/NoMoreOrphans](https://github.com/ChongBong0420/NoMoreOrphans)

## Included Files

- `NoMoreOrphans.dll`
- `PluginInfo.json`
- `config.json`
- `README.md`
- `LICENSE`

No source code is included in this public package.

## Requirements

- ARK: Survival Ascended dedicated server
- ArkApi / ASA Server API 2.01 or newer
- Tested on ASA 91.17 with ASA Server API 2.01
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

## Config

Use `CaptureMode` to choose the capture type:

```json
"CaptureMode": "SCS"
```

or:

```json
"CaptureMode": "Cryo"
```

`CaptureOnTransferButton` controls whether No More Orphans captures when the transfer-server confirmation dialog or upload path fires.

## Commands

No player or admin commands are registered by this build.

## Troubleshooting

If the plugin loads but does not capture during transfer, check `ArkApi.log` for:

```text
NoMoreOrphans transfer trigger fired:
```

That line shows which transfer/upload hook fired.

If startup or transfer capture fails after a Wildcard update, check `ArkApi.log` for an `API][critical] Failed to get the offset` line and report the exact function name. If the missing function is `AShooterPlayerController.GetPlayerInventoryComponent()`, update to version 0.56 or newer.

## License

No More Orphans is copyright (c) 2026 Michael Henderson, also known as Chong,
and published under Safe Mode Software. It is released for personal, private,
non-commercial use only. You may install and use it for personal use, but you
may not distribute modified copies, share repackaged versions, or profit from it
without prior written permission.

See `LICENSE` for the full terms.
