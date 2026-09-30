# Ferutils

Ferutils is a Windows companion app and Fabric mod for Wynncraft.

Latest version: **0.8.15**

## Features

- Gear price and ID analysis
- Optional Wynnpool and Nori price-estimation weights
- Role-based comparison with owned gear
- Inventory organization with ID differences and reference copies
- Ingredient market prices
- Lootrun tracking and recommendations
- Automatic Minecraft-to-app synchronization
- Japanese and English UI

## Requirements

- Windows 10 or 11 (64-bit)
- Minecraft 1.21.11 with Fabric
- Wynntils 4.2.6 or later

Python, a Java development kit, and mod compilation are not required.

## Install

1. Open the [latest release](https://github.com/feruram/Ferutils/releases/latest).
2. Download `FerutilsApp-0.8.15-windows-x64.zip` and `ferutils-0.8.15.jar`.
3. Extract the App ZIP and start `FerutilsApp.exe`.
4. Place the mod jar in `%appdata%\.minecraft\mods`. Remove an older Mynntils or Ferutils jar first.
5. Start the App, then launch Minecraft.
6. Confirm that the App shows `MOD ● Connected`.

Windows may show an unknown-publisher warning because the App is not code-signed. Check that the file is named `FerutilsApp.exe`, then select `More info` and `Run anyway` if you trust this release.

## Guides

- [App guide](docs/APP_GUIDE.md)
- [Mod guide](docs/MOD_GUIDE.md)

## Wynnventory API key

The key is required for gear and Ingredient market prices.

1. Open [Wynnventory API Key](https://www.wynnventory.com/developer/api-key).
2. Enter `Ferutils` as the project name, your Discord username, and a short description of your intended use.
3. Select `Generate Key`.
4. Copy the displayed key. It is shown only once.
5. Open `Settings` in Ferutils App.
6. Paste the key into `Wynnventory API key`, then save and restart the App.

Do not share the key or include it in issues, logs, or screenshots.

## Language

- App: `Settings` → `Language`, then restart the App.
- Mod: follows the Minecraft language setting.

Japanese and English are included.

## Lootrun strategy

The App creates this editable file on first launch:

`Documents\Ferutils\settings\lootrun-strategy.toml`

The complete latest strategy is bundled with the App and attached separately to each Release. Select another TOML file from `Settings` → `Lootrun strategy`. Restart the App after changing it. Schema 1 and 2 files are upgraded while keeping compatible settings.

In-game Beacon Rerolls are detected automatically. Challenge completion and `/class` offer restoration do not consume a Reroll.

If Beacon synchronization stops, open `/class`, select `Reload game state` in Lootrun Advisor, then return to the Lootrun. A complete candidate set replaces the stale App phase and candidates.

Select a run goal in Lootrun Advisor. The selected goal remains active for later runs and App restarts.

See [Strategy file format](docs/STRATEGY_FORMAT.md).

## Updating

1. Close the App and Minecraft.
2. Extract the new App ZIP.
3. Replace the old Mynntils or Ferutils jar in the `mods` folder.

New installations use `Documents\Ferutils`. Existing Mynntils data folders and custom locations remain readable.

## Connection

The default address is `127.0.0.1:8765`. Normally no change is needed.

- App: `Settings` → `App host` and `App port`
- Mod: press `O` → connection mode

Restart both Minecraft and the App after changing the connection settings.

## Wynncraft rules

Read the [rules review](COMPLIANCE.md) and the [official Wynncraft rules](https://forums.wynncraft.com/threads/game-forum-rules.111874/) before use.
