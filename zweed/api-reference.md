# API Reference

zWeed does not currently expose public exports. All interactions happen through the event system documented in [Events](events.md).

## Internal Modules

| Module | Side | Description |
|---|---|---|
| `client/main.lua` | Client | Plant visualization, interactions, minigames, sync |
| `client/packing.lua` | Client | Packing station minigame |
| `client/utils.lua` | Client | Shared utilities (quaternions, notifications, outlines) |
| `server/main.lua` | Server | Plant lifecycle, persistence, sync |
| `server/Plant.lua` | Server | Plant data class |
| `server/packing.lua` | Server | Packing station logic |

## Configuration API

The `Config` table and `Locale()` function are available globally across all scripts.

```lua
-- Access any config value
local interval = Config.TickInterval

-- Get localized string
local label = Locale('harvest') -- "Harvest" or "Raccogli"
```
