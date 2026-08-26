# Mynntils

Mynntils is a Windows companion app and Fabric mod for Wynncraft.

Latest version: **0.6.0**

## Features

- Gear price and ID analysis
- Role-based comparison with owned gear
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

1. Open the [latest release](https://github.com/feruram/Mynntils/releases/latest).
2. Download `MynntilsApp-0.6.0-windows-x64.zip` and `mynntils-0.6.0.jar`.
3. Extract the App ZIP and start `MynntilsApp.exe`.
4. Place the mod jar in `%appdata%\.minecraft\mods`. Remove an older Mynntils jar first.
5. Start the App, then launch Minecraft.
6. Confirm that the App shows `MOD ● Connected`.

Windows may show an unknown-publisher warning because the App is not code-signed. Check that the file is named `MynntilsApp.exe`, then select `More info` and `Run anyway` if you trust this release.

## Guides

- [App guide](docs/APP_GUIDE.md)
- [Mod guide](docs/MOD_GUIDE.md)

## Wynnventory API key

The key is required for gear and Ingredient market prices.

1. Open [Wynnventory API Key](https://www.wynnventory.com/developer/api-key).
2. Enter `Mynntils` as the project name, your Discord username, and a short description of your intended use.
3. Select `Generate Key`.
4. Copy the displayed key. It is shown only once.
5. Open `Settings` in Mynntils App.
6. Paste the key into `Wynnventory API key`, then save and restart the App.

Do not share the key or include it in issues, logs, or screenshots.

## Language

- App: `Settings` → `Language`, then restart the App.
- Mod: follows the Minecraft language setting.

Japanese and English are included.

## Lootrun strategy

The App creates this editable file on first launch:

`Documents\Mynntils\settings\lootrun-strategy.toml`

It contains progress thresholds and score tables used by the Lootrun Advisor. Open it from `Settings` → `Open strategy`. Restart the App after replacing or editing the file.

## Updating

1. Close the App and Minecraft.
2. Extract the new App ZIP.
3. Replace the old Mynntils jar in the `mods` folder.

Owned items, settings, and the API key remain in `Documents\Mynntils` unless you selected another data folder.

## Connection

The default address is `127.0.0.1:8765`. Normally no change is needed.

- App: `Settings` → `App host` and `App port`
- Mod: press `O` → connection mode

Restart both Minecraft and the App after changing the connection settings.

## Wynncraft rules

Read the [rules review](COMPLIANCE.md) and the [official Wynncraft rules](https://forums.wynncraft.com/threads/game-forum-rules.111874/) before use.
