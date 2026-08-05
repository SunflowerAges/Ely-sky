# Installation

## Requirements

- Paper 26.2
- Java 25

Optional integrations are not required for normal racing.

## Install Ely-sky

1. Download the latest official Ely-sky JAR from this repository's Releases page.
2. Stop the Minecraft server.
3. Place the JAR in the server's `plugins/` directory.
4. Start the server.
5. Confirm Ely-sky enables successfully in the console.
6. Review the generated files under `plugins/ElySky/`.

## First course

Create a course with:

```text
/elyskyadmin create Canyon Run
```

Follow the in-world editor, finish the course, test it, then publish it:

```text
/elyskyadmin test Canyon Run
/elyskyadmin open Canyon Run
```

See [Admin Guide](ADMIN_GUIDE.md) for the full editor workflow.

## Updating

Before updating a production server:

1. Stop the server.
2. Back up `plugins/ElySky/`.
3. Replace the old Ely-sky JAR with the new release.
4. Keep only one Ely-sky JAR in `plugins/`.
5. Start the server and review console output for migration or configuration warnings.

Do not manually merge generated runtime files while the server is running.
