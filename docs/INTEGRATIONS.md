# Integrations

All integrations are optional and controlled from `integrations.yml`.

## PlaceholderAPI

Identifier: `elysky`

Core placeholders include:

```text
%elysky_course%
%elysky_course_key%
%elysky_is_racing%
%elysky_competition%
%elysky_revision%
%elysky_time%
%elysky_personal_best%
%elysky_server_best%
%elysky_rank%
%elysky_attempts%
%elysky_finishes%
%elysky_rival%
%elysky_rival_time%
```

Course-specific variants use the course key/name suffix for the supported record fields, for example
`%elysky_personal_best_canyon-run%`.

Competition privacy is enforced in placeholder output. Hidden ranks/names/bests are not exposed
through the expansion.

## MiniPlaceholders

Namespace: `elysky`

Current audience placeholders:

```text
<elysky_course>
<elysky_course_key>
<elysky_is_racing>
<elysky_rank>
```

## Vault

Vault is used only when enabled and an economy provider is available. Ely-sky does not provide an
economy.

Optional reward money is configured in `rewards.yml`. Ely-sky continues to check permissions through
Bukkit.

## LuckPerms

LuckPerms is optional presentation support for cached prefix/suffix metadata. It is not required for
Ely-sky permission checks.

`player-display.provider` may use `AUTO`, `LUCKPERMS`, `VAULT`, or `NONE` according to the values
accepted by `integrations.yml`.

## Reload behavior

Placeholder expansions register once when their provider is present. The live `enabled` setting
gates their output after `/elyskyadmin reload`; the plugin does not attempt to hot-load or
hot-unload third-party providers.
