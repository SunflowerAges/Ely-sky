# Commands and Permissions

## Player commands

| Command | Purpose |
| --- | --- |
| `/elysky` | Open the Ely-sky player menu. |
| `/elysky start <course-key>` | Start a course directly. |
| `/elysky restart` | Restart the current course. |
| `/elysky leave` | Leave the current run. |

Alias: `/esky`

## Administrative command

Administrative actions use `/elyskyadmin` with alias `/esa`.

See [Admin Guide](ADMIN_GUIDE.md) for the complete authoring, record, testing, and maintenance syntax.

## Permissions

| Permission | Purpose | Default |
| --- | --- | --- |
| `elysky.use` | Player access | true |
| `elysky.competition.rank` | Eligible runs may enter shared rankings | true |
| `elysky.admin` | All administrative capabilities | op |
| `elysky.admin.author` | Create and edit courses | op |
| `elysky.admin.control` | Open and close courses | op |
| `elysky.admin.inspect` | List, test, and validate courses | op |
| `elysky.admin.delete` | Delete/archive courses | op |
| `elysky.admin.records` | Moderate records | op |
| `elysky.admin.diagnostics` | Create diagnostics | op |
| `elysky.admin.reload` | Reload configuration | op |
| `elysky.admin.repair-index` | Rebuild derived indexes | op |
