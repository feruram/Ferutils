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

After removal, analysis updates automatically. With no owned copies left, the item shows `Not owned`; otherwise it is compared with the remaining owned copies.

Unowned gear is recommended for registration even with limited market samples. Market-value decisions use the price shown in the tooltip and the threshold in Settings.

Regular and Masterwork gear are priced separately. Existing owned items use the current ID ranges when re-analyzed; no re-registration is needed. Estimates reflect observed asking prices, not guaranteed sale prices.

Gear and Ingredients with the same name are analyzed separately.

- `★ Melee`, `★ Mobility`, etc.: a role's best owned copy. Tied leaders share the badge.
- `★ Overall IDs`: the highest overall ID rolls when no role is known.
- `vs Spell #353`: the role and registration number used for comparison.
- Zero differences against the same copy are hidden. `Equal` means matching rolls; `Comparison: missing IDs` means a comparison is unavailable.

The `Owned items` tab supports filtering, ID comparison, notes, JSON/CSV export, duplicate cleanup, reload, and re-analysis.

Price analysis uses matching item names across all available listing pages. Listings without ID data cannot contribute to ID-based estimates. Similarly named gear, such as Warp and Masterwork Warp, is not combined.

### Organize owned items

In `Owned items`, select an `Organize` filter. Use `Refresh analysis` for up-to-date comparisons.

- **Outclassed in known roles:** one owned copy matches or exceeds every ID used by the market-supported roles, with at least one improvement. Any loss in other IDs is shown separately.
- **Outclassed in all IDs:** one owned copy matches or exceeds every variable ID, with at least one improvement. No market-supported role is required.
- **Roles unresolved:** review items with several copies of the same name. The default minimum is 3; change the count beside the filter.

Select a candidate to see its reference registration number, actual IDs, and percentage-point differences. `Compare with reference` selects both copies together. Comparisons follow the usual ID roll direction; special builds may value different stats. Missing or incompatible stats never establish dominance.

These are review candidates, not disposal instructions. Nothing is deleted automatically. Existing registration-removal controls affect the App inventory only, not Minecraft items. General-purpose stat preferences are not used to declare an item inferior.

### Optional price weights

- Open `Settings` → `Item Manager rules`, enable `Wynnpool price weights` and/or `Nori price weights`, save, and restart the App. Both are off by default.
- Weights describe community preferences, not guaranteed sale prices. Official Wynncraft data supplies ID ranges, not price weights.
- Current catalogs cover Mythic gear. Other gear keeps the usual estimate unless an exact, compatible scale becomes available.
- Weighted estimates require enough complete samples and lower validation error. Missing IDs, unsupported rolls, Shiny gear, or unavailable weight services use the usual model.
- Item details show the selected source and scale, or why the usual model was retained. Prices reflect observed listings, not confirmed sales.
- Turn both options off to restore the usual estimation method. Ingredients and ownership-comparison weights are unchanged.

## Ingredients

Hover an Ingredient or search its name in the App to view its per-item price and stack total. Ingredients are not registered as owned gear.

## Settings

Save and restart the App and Minecraft after changing connection settings.

- `Language`: Auto, Japanese, or English
- `Data folder`: owned items, backups, exports, settings, and logs
- `Wynnventory API key`: market-price access
- `Wynnpool price weights` and `Nori price weights`: optional price-estimation aids; save and restart the App
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
