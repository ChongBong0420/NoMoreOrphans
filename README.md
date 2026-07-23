# No More Orphans

No More Orphans is an ARK: Survival Ascended ArkApi plugin that captures a player's current shoulder pet into an SCS pod or vanilla cryopod during the transfer-server flow.

It does not capture just because a player opens a transmitter. It waits until the player starts the server-transfer flow before trying to capture the shoulder pet.

Version 0.59 is the current public release. It supports SCS mode and vanilla cryopod mode, including optional temporary vanilla cryopods.

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

`CaptureOnTransferButton` controls whether No More Orphans captures during server transfer.

## Commands

No player chat commands are registered by this build.

Server owners can use `nmodebug on`, `nmodebug off`, or `nmodebug status` in the server console when troubleshooting.

## Troubleshooting

If the plugin loads but does not capture during transfer, update to the newest release and check the server log for No More Orphans messages. Include those log lines when reporting an issue.

## License

No More Orphans is copyright (c) 2026 Michael Henderson, also known as Chong,
and published under Safe Mode Software. It is released for personal, private,
non-commercial use only. You may install and use it for personal use, but you
may not distribute modified copies, share repackaged versions, or profit from it
without prior written permission.

See `LICENSE` for the full terms.
