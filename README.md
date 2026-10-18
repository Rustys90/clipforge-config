# clipforge-config

Remote configuration for the **ClipForge Android** app. The app fetches
[`v1.json`](v1.json) at startup (with the APK-bundled copy as fallback), so
YouTube-side changes can be adapted **without shipping a new APK**.

## What's in `v1.json`

| Key | Purpose |
|---|---|
| `engineOrder` | Download engine try-order (first success wins) |
| `killSignals` | Error substrings that mean "this engine is dead, move on" |
| `poToken` | PO-token minter constants (endpoints, request key, API key, desktop UA) |

## Editing

Edit `v1.json` directly on GitHub (or push a commit). The app picks up the new
config on next start. Keep the JSON shape — the app ignores unknown keys but
requires the three above.

The PO-token values here are public constants observed in YouTube's BotGuard
traffic (the same values shipping implementations hardcode). They rotate
periodically — when minting breaks, refresh them from the latest references.

## License

MIT
