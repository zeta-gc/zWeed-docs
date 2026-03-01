# Configuration

All configuration is centralized in `config.lua` at the root of the resource.

## Bridge Selection

```lua
Config.Inventory = 'auto'    -- 'ox_inventory' | 'qb-inventory' | 'custom'
Config.Target    = 'auto'    -- 'ox_target' | 'qb-target' | 'custom'
Config.Notify    = 'auto'    -- 'ox_lib' | 'qb-core' | 'okokNotify' | 'custom'
Config.Framework = 'auto'    -- 'esx' | 'qb-core' | 'standalone'
Config.Skills    = 'none'    -- 'none' | 'peakville' | 'custom'
```

Set to `'auto'` for automatic detection. The system checks which resources are started and picks the appropriate bridge.

## Locale

```lua
Config.Locale = 'en'  -- 'en' or 'it'
```

Add new locales by creating `locales/xx.lua`.

## Growth Settings

| Setting | Default | Description |
|---|---|---|
| `TickInterval` | 20 | Seconds between growth ticks |
| `SecondsForFullGrowth` | 10800 | Total growth time (3 hours) |
| `SecondsForFullWaterDrain` | 5400 | Water drain time (1.5 hours) |
| `AnimLength` | 600.0 | Growth animation length |
| `DeathAfterHours` | 3 | Hours without water before death |
| `AutoSaveInterval` | 60 | DB save interval |

## Item Names

All item names are configurable. Change them to match your server's item definitions:

```lua
Config.Items = {
    Pot            = 'weed_pot',
    Soil           = 'fertilizer',
    WateringCan    = 'watering_can',
    PlasticBag     = 'plastic_bag',
    WeedBag        = 'weed_bag',
    Grinder        = 'grinder',
    GrindedWeed    = 'grinded_marijuana',
    RollingPaper   = 'rollingpaper',
    Scissors       = 'scissors_weed',
    PackingBench   = 'weed_bench',
}
```

## Plant Types

Define new plant types with unique models and items:

```lua
Config.PlantTypes = {
    seed_weed = {
        label       = 'Cannabis',
        potModel    = 'bzzz_growing_freepot_a',
        plantModel  = 'weed_growing',
        budModel    = 'h4_prop_h4_weed_bud_02b',
        harvestItem = 'weed_bud',
        seedItem    = 'seed_weed',
        budBones    = {6, 7, 8, 9, 10, 11, 12},
    },
}
```

## Fertilizers

```lua
Config.Fertilizers = {
    ['fertilizer_speed'] = {
        label            = 'Speed Boost',
        multiplier_speed = 2.0,
        multiplier_yield = 1.0,
    },
    ['fertilizer_yield'] = {
        label            = 'Yield Boost',
        multiplier_speed = 1.0,
        multiplier_yield = 2.0,
    },
}
```

## Planting Zone

Restrict planting to a polygon zone (optional):

```lua
Config.PlantingZone = {
    points = {
        vector3(x1, y1, 0),
        vector3(x2, y2, 0),
        -- ...
    },
    thickness = 2000,
}
```

Set to `nil` for no restriction.
