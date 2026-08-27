# Lootrun strategy file format

Ferutils uses a TOML strategy file. Open it from `Settings` → `Open strategy`, close the App, replace or edit the file, then restart Ferutils.

## Header

```toml
schema_version = 3
strategy_version = "2026.08.27-policy"
name = "My strategy"
```

Schema 1 and 2 files are upgraded automatically. Invalid files are left unchanged and the bundled strategy is used for that session.

## What Schema 3 controls

- phase, setup, Reroll, and stop decisions
- Beacon, Mission, and Trial evaluation
- Boon, Challenge, and future action types
- conditional scores, warnings, and blocked choices
- Mission and Trial routes, synergies, conflicts, and route commitment
- goal-specific expected utility
- deterministic tie-breaks

Choices omitted from the strategy are still available. They keep their default score and are ranked normally.

## Conditions

```toml
when = "timer <= 180 and red_remaining > 0"
```

Conditions may use observed Lootrun values such as `completed`, `limit`, `remaining`, `timer`, `rerolls`, `pulls`, `curses`, `boon_count`, `missions`, `completed_trials`, `active_trial`, `goal`, and `risk`.

Supported operations include comparisons, membership, Boolean logic, arithmetic, set intersection and union, conditional expressions, and `abs`, `len`, `min`, `max`, and `round`.

Imports, file access, network access, arbitrary Python calls, attribute access, indexing, and comprehensions are rejected.

## Additional state and derived values

```toml
[state_defaults]
estimated_travel_seconds = 0
estimated_clear_seconds = 0
failure_probability = 0.0

[[derived]]
name = "time_pressure"
expression = "timer < estimated_travel_seconds + estimated_clear_seconds + 90"
```

Additional values must be declared in `state_defaults`. Values unavailable from Wynntils may be supplied manually, by a compatible mod event, or by a simulator.

## Policy rules

```toml
[[policy_rules]]
id = "green_during_red_pressure"
scope = "beacon"
actions = ["Green"]
priority = 20
when = "timer <= 180 and red_remaining > 0"
add = 80
reason = "Recover time before Red Challenges"
```

Available fields are `id`, `scope`, `actions`, `priority`, `when`, `add`, `set_score`, `utility`, `block`, `reason`, and `warning`.

## Routes

```toml
[[routes]]
id = "Dying Light + All In"
required_trials = ["Dying Light", "All In"]
synergy_missions = ["Redemption"]
conflicts = ["Another route"]
```

Routes may contain required or synergy Missions, Trials, and generic actions. Optional `active_when`, `complete_when`, and `commit_when` conditions can describe special route states.

## Expected utility

```toml
[[policy_rules]]
id = "challenge_value"
scope = "challenge"
utility = { pulls = "action_pulls", time_cost = "action_travel_seconds + action_clear_seconds", risk = "action_failure_probability" }

[utility_weights.PULLS]
pulls = 2.0
time_cost = -0.1
risk = -100.0
```

Utility dimensions are user-defined. Different goals may assign different weights.

## Technical limits

Ferutils can evaluate any deterministic rule over the state and candidates it receives. It cannot know unreported travel time, clear time, failure probability, or future server RNG. Exact multi-step simulation must calculate those estimates separately and provide them as state or candidate values.
