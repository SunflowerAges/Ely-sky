# Configuration

Ely-sky separates mechanics, presentation, integrations, rewards, and generated data into dedicated files.

## `config.yml`

Controls primary race behavior and presentation mechanics, including:

- countdown and recovery timing;
- gliding and protection behavior;
- course editor limits;
- checkpoint sizing;
- Boost Portal defaults and limits;
- private course rendering and route guidance;
- title timing;
- leaderboard and replay retention;
- ghost presentation defaults.

## `competition.yml`

Controls Casual and Competitive presentation, including:

- Personal Best and Server Best visibility;
- public ranks and player names;
- Rival and leaderboard-player ghost availability;
- Server Best identity presentation;
- ranking eligibility;
- finish and rank-change messaging.

Each course may use `INHERIT`, `CASUAL`, or `COMPETITIVE`.

## `equipment.yml`

Controls whether racers use their own equipment or temporary loan equipment supplied for the run.

## `integrations.yml`

Controls optional provider integrations and player-name formatting. See [Integrations](INTEGRATIONS.md).

## `rewards.yml`

Optional rewards are disabled by default. Supported qualifying triggers include:

- first finish;
- personal best;
- server record;
- rank improvement;
- configured rank milestones.

Rewards may use Vault money and/or configured console commands when enabled.

## `messages.yml`

Contains player/admin messages, countdown and finish titles, and HUD wording.

## `gui.yml`

Controls menu titles, sizes, slots, materials, names, lore, glow, and navigation.

Slot expressions support numeric slots plus:

```text
center
bottom:<column>
row:<row>:<column>
```

Row and column values are zero-based.

## Reloading

Use:

```text
/elyskyadmin reload
```

Ely-sky validates reloadable configuration before applying it. Review console warnings when a configured value is rejected or a fallback is used.
