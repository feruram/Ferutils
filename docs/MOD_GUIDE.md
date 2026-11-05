# Ferutils Mod guide

Start Ferutils App before Minecraft. The mod cannot perform market analysis by itself.

## Updating

Ferutils 0.9.9 supports Wynntils 4.2.16 and keeps compatibility with 4.2.6 (Fabric, Minecraft 1.21.11).

If Minecraft crashes with `LootrunModel.getBeacons()` / `NoSuchMethodError`, close Minecraft, remove the old Ferutils JAR from your profile's `mods` folder, and install `ferutils-0.9.9.jar` from the [latest release](https://github.com/feruram/Ferutils/releases/latest). Keep only one Ferutils JAR. No data reset is needed.

## Controls

- `O`: open Ferutils settings
- Hover identified gear: analyze price, IDs, and owned copies
- Hover unidentified gear: show market prices for its possible items
- Hover an Ingredient: show its market price
- Hold `Left Alt` while hovering gear: register it as owned
- Hold `Right Alt` while hovering gear: remove that gear's registration

Keys can be changed on the Ferutils settings screen.

## Gear analysis

The tooltip first shows `Analyzing` or `Queued`, then displays the result. Processing continues after the cursor moves away, and multiple hovered items are handled in order.

Identical item name, actual IDs, Reroll count, and Shiny state are not registered twice.

Removing a registration does not remove the Minecraft item or other owned copies. A backup is saved in the App's data folder before removal.

The tooltip automatically returns to normal analysis after removal: `Not owned` if no owned copies remain, or a comparison with the remaining copies. Price and ID differences are refreshed automatically.

Unowned gear is recommended for registration even when market samples are limited. Market-value decisions use the displayed price and the threshold set in the App.

### Unidentified gear

Under `Ferutils: Candidates · Identified market`, each possible item shows its typical identified asking price. Final IDs are still unknown, so this is not an ID-specific estimate or the unidentified item's sale price.

- `No market data`: no matching identified listings are available.
- `Untradable`: no market-price request is made.
- Amounts beside Wynntils' level labels are identification costs.

These items are not registered as owned gear. Candidate prices also appear when Wynntils' guesses are disabled.

The short summary shows the mean and highest quote among priced candidates, followed by priced candidates / all candidates. Equal prices appear only once. Summary amounts are rounded to one decimal place in one currency unit; individual candidate quotes retain their detailed amounts.

- `30le · 3/4`: three candidates at 30le, one without a usable quote.
- `Avg 30le / Max 35le · 3/4`: the three priced candidates average 30le and reach 35le.
- `Avg 5.3le / Max 1stx · 12/12`: mostly cheap candidates with one valuable outcome.
- `1stx · 1/12`: only one candidate is priced; the other eleven remain unknown.

Missing prices are excluded from the mean, not treated as zero. The fraction is data coverage, not a drop probability. Quotes are typical identified asking prices, not best-roll values or the unidentified item's sale price. Identification fees are not deducted. Unknown candidates could be worth more or less, so a partial mean is not the whole item's expected return.

## Tooltip states

- `Analyzing`: checking market and owned-item data
- `Queued`: waiting for an earlier analysis
- `Not owned`: no owned copy is available for comparison
- `Upgrade`: better than the relevant owned copy
- `Market candidate`: consider selling on the Trade Market
- `Blacksmith candidate`: consider selling to the Blacksmith
- `Owned`: identical stats are already registered
- `UNTRADABLE`: market-price requests are skipped
- `App offline`: the App is not connected
- `Market API unavailable`: the App is connected but Wynnventory did not return usable data
- `Check API key`: Wynnventory rejected the API credentials
- `App response timed out`: the App did not respond in time

The line below an upgrade shows the ID used for the decision and its difference from the relevant owned copy.

- `★ Melee`, `★ Mobility`, etc.: a role's best owned copy. A copy can lead several roles; ties share the badge.
- `★ Overall IDs`: the highest overall ID rolls when no role is known.
- `vs Spell #353`: the role and registration number used for comparison. ID differences are shown beside the rolls.
- A representative compared with itself has no nonzero differences. `Equal` means matching rolls; `Comparison: missing IDs` means a comparison is unavailable.

## Lootrun link

Mission candidates are filled automatically, including offers with two detected names. After a Mission is selected, active-objective and immediately active Missions both return the Advisor to Beacon selection. Open the candidate-selection button only when a manual correction is needed.

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
