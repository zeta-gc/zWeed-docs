# Installation

## Step 1: Download and Extract

Place the `zWeed` folder into your server's `resources` directory:

```
resources/
└── [scripts]/
    └── zWeed/
```

## Step 2: Database Setup

Run the SQL install script on your database:

```sql
-- Run: sql/install.sql
```

This creates two tables:
- `plants` — Stores all plant data
- `weed_packing_stations` — Stores packing station positions

If upgrading from v1, run `migration_v2.sql` instead.

## Step 3: Configure

Edit `config.lua` to match your server:

```lua
Config.Inventory = 'ox_inventory'  -- or 'qb-inventory', 'custom'
Config.Target    = 'ox_target'     -- or 'qb-target', 'custom'
Config.Notify    = 'ox_lib'        -- or 'qb-core', 'okokNotify', 'custom'
Config.Framework = 'esx'           -- or 'qb-core', 'standalone'
Config.Skills    = 'none'          -- or 'peakville', 'custom'
Config.Locale    = 'en'            -- or 'it'
```

Set to `'auto'` for automatic detection (recommended).

## Step 4: Add Items

Register the following items in your inventory system:

| Item Name | Label |
|---|---|
| `weed_pot` | Flower Pot |
| `fertilizer` | Potting Soil |
| `watering_can` | Watering Can |
| `seed_weed` | Cannabis Seed |
| `fertilizer_speed` | Speed Fertilizer |
| `fertilizer_yield` | Yield Fertilizer |
| `weed_bud` | Weed Bud |
| `plastic_bag` | Plastic Bag |
| `weed_bag` | Packed Weed |
| `grinder` | Grinder |
| `grinded_marijuana` | Ground Weed |
| `rollingpaper` | Rolling Paper |
| `weed_tier1` / `weed_tier2` / `weed_tier3` | Joint (Tier 1/2/3) |
| `scissors_weed` | Scissors |
| `weed_bench` | Packing Bench |

## Step 5: Start

Add to your `server.cfg`:

```cfg
ensure ox_lib
ensure oxmysql
ensure zWeed
```

Restart and verify the console prints bridge detection results.
