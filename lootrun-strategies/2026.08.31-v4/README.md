# Ferutils Lootrun Strategy 2026.08.31 v4

An independently distributed Lootrun strategy for Ferutils 0.8.x.

## Included file

- `ferutils-lootrun-strategy-2026.08.31-v4.toml`: strategy data

## Installation

1. Close Ferutils App.
2. Back up the `lootrun-strategy.toml` file currently in use.
3. In Ferutils App, open `Settings` → `Lootrun strategy` and select the included TOML file.
4. Save the settings and restart Ferutils App.

## Compatibility

- Strategy schema: 3
- Tested with Ferutils App 0.8.1–0.8.7 strategy evaluator

## Policy changes

- Reduces excessive Blue recommendations in ordinary states.
- Prioritizes one-time, expiring, or route-defining Beacons such as Red, White, Orange, and Crimson over Mission objectives.
- Prepares Aqua extensions according to remaining Challenges and Orange duration.
- Secures Mission offers before Grey becomes less likely to appear.
- Suppresses Gambling Beast when supporting Missions are insufficient.
- Uses Potency instead of counts for Boon and Curse safety checks.

This strategy is updated through the separate `lootrun-strategy-v*` release series.

