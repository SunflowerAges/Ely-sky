# Admin Guide

Administrative commands use `/elyskyadmin` with alias `/esa`.

## Course authoring

```text
/elyskyadmin create <name>
/elyskyadmin edit <name>
/elyskyadmin start
/elyskyadmin finish
/elyskyadmin move <ring>
/elyskyadmin move boost <number>
/elyskyadmin insert <ring>
/elyskyadmin remove <ring>
/elyskyadmin remove boost <number>
/elyskyadmin trail refresh [ring]
/elyskyadmin rename <new name>
/elyskyadmin set <description|icon|difficulty|permission|competition> <value>
/elyskyadmin done
```

`create` begins at Start placement. Course names may contain spaces. `rename` and `set` act on the course currently open in the editor.

### Editor controls

```text
Left-click                 Place/confirm
Right-click                Undo/cancel
Sneak + scroll             Change size
Ctrl/Sprint + left-click   Place Boost Portal
Ctrl/Sprint + sneak+scroll Adjust Boost Portal strength
```

Boost Portals are route elements rather than timed checkpoints and do not change ring numbering.

## Course management

```text
/elyskyadmin list
/elyskyadmin open <name-or-key>
/elyskyadmin close <name-or-key>
/elyskyadmin test <name-or-key>
/elyskyadmin validate [name-or-key]
/elyskyadmin delete <name-or-key>
```

New courses are closed until opened. `test` runs the normal course without recording attempts, personal bests, leaderboard results, or rewards.

Destructive course and record actions use confirmation where appropriate.

## Record administration

```text
/elyskyadmin records inspect <course-key> <player>
/elyskyadmin records remove <course-key> <player>
/elyskyadmin records reset <course-key>
/elyskyadmin records rebuild <course-key>
/elyskyadmin repair-leaderboard <course-key|all>
```

## Maintenance

```text
/elyskyadmin diagnostics
/elyskyadmin reload
/elyskyadmin repair-index
```

`diagnostics` creates a support report intended to help troubleshoot plugin/platform/configuration/integration/course status without including course coordinates, player inventories, IP addresses, or credentials.
