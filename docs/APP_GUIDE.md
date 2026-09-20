# Ferutils App guide

## Start

1. Start `FerutilsApp.exe`.
2. Wait for `MOD ○ Waiting`, then launch Minecraft.
3. Confirm that the status changes to `MOD ● Connected`.
4. Select `Lootrun`, `Item Manager`, or `Settings`.

## Lootrun

The Advisor ranks the choices visible in Minecraft from the current run state.

While the mod is connected, Beacon choices, selections, Challenge results, Mission choices, and Trial choices are synchronized when Wynntils exposes them. The player still makes every game action.

Any visible choice can be selected in the App. The recommendation has a larger action button, but it is not mandatory.

In-game Beacon Rerolls are detected automatically when the Wynncraft Reroll link is clicked. Complete Wynncraft Beacon prompts synchronize candidates after normal Challenges, Rerolls, and `/class` reloads; the Wynntils Beacon model is used as a fallback.

Loading a saved Lootrun state restores the current Beacon candidates from the connected mod automatically.

If synchronization stops, open `/class`, select `Reload game state` under `Run status`, then return to the Lootrun. The App waits for a complete Beacon set before replacing its phase and candidates.

Mission and Trial candidates are loaded automatically when available. Their manual picker opens only from the candidate selection button.

Select a goal under `Run status`. The selected goal remains active for later runs and App restarts.

Use the correction controls when a value could not be read. Use `Resume` when joining a run already in progress.

The editable strategy file is stored at:

`Documents\Ferutils\settings\lootrun-strategy.toml`

The complete latest strategy is bundled with the App and attached separately to each Release. Select another TOML file with `Settings` → `Lootrun strategy`. `Open strategy` opens the selected file. Restart the App after changing it. Schema 1 and 2 files are upgraded while keeping compatible settings.

After a Lootrun ends, select `Export run log` to save a JSON record. No file is created unless you select a save location.

See [Strategy file format](STRATEGY_FORMAT.md).

## Item Manager

Hover identified gear in Minecraft to view:

- Reference price
- Actual IDs and roll percentages
- Number of owned copies
- Role-based comparison with the relevant owned copy
- Separate `Not owned` and `Upgrade` decisions
- The IDs used for the comparison and their differences

Analysis continues after the cursor moves away. Earlier results remain in the Minecraft link history.

Hold `Left Alt` while hovering gear to register it. Identical stats are not registered twice. The registration key can be changed in the mod settings.

Hold `Right Alt` while hovering gear to remove its registration. This does not remove the Minecraft item or other owned copies. A backup is saved first. Both hotkeys can be changed in the mod settings (`O`).

Unowned gear is recommended for registration even with limited market samples. Market-value decisions use the price shown in the tooltip and the threshold in Settings.

The `Owned items` tab supports filtering, ID comparison, notes, JSON/CSV export, duplicate cleanup, reload, and re-analysis.

Price analysis uses matching item names across all available listing pages. Listings without ID data cannot contribute to ID-based estimates. Similarly named gear, such as Warp and Masterwork Warp, is not combined.

## Ingredients

Hover an Ingredient or search its name in the App to view its per-item price and stack total. Ingredients are not registered as owned gear.

## Settings

Save and restart the App and Minecraft after changing connection settings.

- `Language`: Auto, Japanese, or English
- `Data folder`: owned items, backups, exports, settings, and logs
- `Wynnventory API key`: market-price access
- `App host` and `App port`: mod connection
- `Item Manager link` and `Lootrun link`: enable or disable integration
- `Lootrun strategy`: selects a Lootrun strategy TOML file
- `Open strategy`: opens the selected strategy file
- `Open folder`: opens the current data folder
- `Back up`: creates an owned-item backup

## If data does not update

1. Confirm that the top bar shows `MOD ● Connected`.
2. Use matching App and mod versions.
3. Check that Item Manager and Lootrun integration are enabled.
4. Restart the App first, then Minecraft.
5. Review `logs\app-errors.log` in the data folder.

See the [mod guide](MOD_GUIDE.md) for Minecraft controls.
