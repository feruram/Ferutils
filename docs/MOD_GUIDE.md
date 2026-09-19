# Ferutils Mod guide

Start Ferutils App before Minecraft. The mod cannot perform market analysis by itself.

## Controls

- `O`: open Ferutils settings
- Hover identified gear: analyze price, IDs, and owned copies
- Hover an Ingredient: show its market price
- Hold `Left Alt` while hovering gear: register it as owned
- Hold `Right Alt` while hovering gear: remove that gear's registration

Keys can be changed on the Ferutils settings screen.

## Gear analysis

The tooltip first shows `Analyzing` or `Queued`, then displays the result. Processing continues after the cursor moves away, and multiple hovered items are handled in order.

Identical item name, actual IDs, Reroll count, and Shiny state are not registered twice.

Removing a registration does not remove the Minecraft item or other owned copies. A backup is saved in the App's data folder before removal.

Unowned gear is recommended for registration even when market samples are limited. Market-value decisions use the displayed price and the threshold set in the App.

## Tooltip states

- `Analyzing`: checking market and owned-item data
- `Queued`: waiting for an earlier analysis
- `Not owned`: no owned copy is available for comparison
- `Upgrade`: better than the relevant owned copy
- `Market candidate`: consider selling on the Trade Market
- `Blacksmith candidate`: consider selling to the Blacksmith
- `Owned`: identical stats are already registered
- `Unregistered`: the hovered gear's registration was removed
- `Not registered`: no matching registration was found to remove
- `UNTRADABLE`: market-price requests are skipped
- `App offline`: the App is not connected
- `Market API unavailable`: the App is connected but Wynnventory did not return usable data
- `Check API key`: Wynnventory rejected the API credentials
- `App response timed out`: the App did not respond in time

The line below an upgrade shows the ID used for the decision and its difference from the relevant owned copy.

## Lootrun link

The mod sends the run state exposed by Wynntils, including:

- Beacon choices and selections
- Challenge completion and failure
- Death
- Mission and Trial choice screens
- Lootrun start and end

Ferutils never clicks or selects a choice in Minecraft.

## Connection

Press `O` and select a connection mode.

- `Use App settings`: reads the App address and port. Use this normally.
- `Manual MOD settings`: uses the address and port entered in Minecraft.

The default is `127.0.0.1:8765`. Restart Minecraft after changing it.

## If the App is offline

1. Start Ferutils App before Minecraft.
2. Use matching App and mod versions.
3. Select `Use App settings` in the mod settings.
4. Check that the App shows `MOD ● Connected`.

See the [App guide](APP_GUIDE.md) for desktop controls.
