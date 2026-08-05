# Ely-sky

Ely-sky is a Paper plugin for virtual Elytra time trials built around a server's existing terrain. Courses are presented privately to each racer, allowing servers to create polished flight challenges without permanently filling the world with course structures.

Pick a course, fly it, improve your time, and optionally race against recorded ghosts or a competitive leaderboard.

## Highlights

- Private checkpoint rings and route guidance
- In-world course editor
- Configurable Boost Portals
- Personal Best and Server Best ghosts
- Rival and leaderboard-player ghosts
- Casual and Competitive course modes
- Revision-aware records and leaderboards
- Staff test mode, validation, record moderation, and diagnostics
- Optional loan Elytra and fireworks
- Optional PlaceholderAPI, MiniPlaceholders, Vault, and LuckPerms support
- Bukkit service API and race lifecycle events for integrations

Ely-sky is designed for independent time trials. Multiple players may use the same course at once, but runs are not synchronized races, lobbies, teams, or tournaments.

## Requirements

- Paper 26.2
- Java 25

Optional integrations:

- PlaceholderAPI
- MiniPlaceholders
- Vault with an economy provider
- LuckPerms

None of the optional integrations are required for normal racing.

## Download and installation

1. Download the latest `Ely-sky-<version>.jar` from **Releases**.
2. Place the JAR in your server's `plugins/` directory.
3. Start Paper once to generate Ely-sky's configuration files.
4. Create your first course with `/elyskyadmin create <name>`.

See [Installation](docs/INSTALLATION.md) for the complete first-run checklist.

## Player commands

```text
/elysky
/elysky start <course-key>
/elysky restart
/elysky leave
```

Alias: `/esky`

The menu is the normal player entry point. The command subcommands are also available for command-driven server setups.

## Quick course setup

```text
/elyskyadmin create Canyon Run
```

The editor begins at the course Start.

1. Stand where racers should spawn and face the launch direction.
2. Left-click to save Start.
3. Fly the route and left-click to place Ring 1, Ring 2, and so on.
4. Use Ctrl/Sprint + left-click to place a Boost Portal.
5. Use `/elyskyadmin finish`, position the Finish, and left-click.
6. Run `/elyskyadmin done`.
7. Test with `/elyskyadmin test Canyon Run`.
8. Publish with `/elyskyadmin open Canyon Run`.

See the [Admin Guide](docs/ADMIN_GUIDE.md) for the full authoring and maintenance workflow.

## Documentation

- [Installation](docs/INSTALLATION.md)
- [Admin Guide](docs/ADMIN_GUIDE.md)
- [Commands and Permissions](docs/COMMANDS_AND_PERMISSIONS.md)
- [Configuration](docs/CONFIGURATION.md)
- [Integrations](docs/INTEGRATIONS.md)
- [Public API](docs/API.md)
- [Migration](docs/MIGRATION.md)
- [Changelog](CHANGELOG.md)

## Source availability

Ely-sky is distributed as compiled software. Its implementation source is maintained privately and is not part of this repository.

This repository exists for official releases, documentation, issue tracking, and the supported public integration surface.

See [Terms](TERMS.md) for permitted use of official Ely-sky builds.

## Support

If you find a reproducible problem, open a bug report and include your Paper version, Java version, Ely-sky version, relevant console output, and the result of `/elyskyadmin diagnostics` when appropriate.
