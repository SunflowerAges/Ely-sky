# Migration

## From legacy SunnysElytra builds

Legacy builds stored runtime data under `plugins/SunnysElytra/`. Ely-sky can import supported legacy data when the new `plugins/ElySky/` location does not already contain active Ely-sky data.

Before migrating a production server:

1. Stop the server.
2. Back up both plugin directories.
3. Install the current Ely-sky release.
4. Start the server and review migration output in the console.
5. Verify courses and records before removing any old deployment files.

The legacy directory is not intended to be manually merged into the new runtime directory while the server is running.

## Current data

Current Ely-sky data is stored under:

```text
plugins/ElySky/
```

Course keys and player UUIDs provide stable identities across supported renames and maintenance operations. Derived indexes and leaderboards have administrative repair commands when needed.
