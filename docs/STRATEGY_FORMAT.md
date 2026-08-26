# Lootrun strategy file format

Ferutils uses TOML for Lootrun strategy profiles. The App bundles a complete default file and copies it to the user data folder on first launch.

## Metadata

```toml
schema_version = 1
strategy_version = "2026.08.26"
name = "Ferutils balanced lootrun strategy"
```

- `schema_version`: parser format. Do not change it unless the App adds a new schema.
- `strategy_version`: strategy revision label.
- `name`: profile name.

## Thresholds

`[thresholds]` defines phase boundaries, setup requirements, safety limits, and the score at which a good choice is kept instead of using a Reroll.

## Score tables

- `[beacon_base]`: normal Beacon scores
- `[opening_bonus]`: adjustments before `opening_end`
- `[mission_base]`: Mission starting bonuses
- `[trial_tier]`: Trial tier starting scores
- `[goal_bonus.NAME]`: Beacon adjustments for the selected goal

Every Beacon starts with a common score of 20. Higher scores are recommended first; negative values reduce priority. Conditional game rules and safety checks remain enforced by the App.

Valid goal names are `PULLS`, `BOXES`, `REROLLS`, `SACRIFICES`, and `SHORT`.

## Updating

1. Close Ferutils App.
2. Back up the current TOML file.
3. Replace it with the new strategy file.
4. Start the App.

Missing fields use bundled defaults. Invalid TOML or an unsupported `schema_version` is rejected and the bundled strategy is used for that session. The invalid user file is not deleted.
