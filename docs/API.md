# API

Ely-sky registers `com.sunnysdreamworld.elysky.api.ElySkyApi` through Bukkit's `ServicesManager`.

```java
ElySkyApi api = Bukkit.getServicesManager().load(ElySkyApi.class);
```

`ElySkyApi.API_VERSION` is `1`.

## Service methods

The API supports:

- course listing and lookup by UUID/name/key;
- privacy-aware leaderboard views (anonymous entries expose `Optional.empty()` for the player UUID);
- personal, ranked, and server best times;
- rank lookup;
- active-run/course lookup;
- starting a course for a player;
- invalidating an active run.

API methods are synchronous and must be called from the server thread. Personal-best lookup for an
offline player may read that player's saved record from disk.

## Events

Package: `com.sunnysdreamworld.elysky.api.event`

- `RacePrepareEvent`
- `RaceStartEvent`
- `RingPassEvent`
- `RecordSubmitEvent`
- `RaceFinishEvent`
- `ServerRecordEvent`
- `RaceEndEvent`

Lifecycle events include the course UUID, immutable course key, and competitive revision so
integrations can identify the exact run even if the display name or course geometry changes later.

`RecordSubmitEvent` is cancellable. Cancelling it lets moderation/anti-cheat integrations reject the
result before PB/leaderboard mutation without taking over race movement or timing.
