# Items Configuration

zWeed requires several items to be registered in your inventory system. Below is the full list of items with their configuration for **ox_inventory**.

> [!TIP]
> Copy these into your inventory's `items.lua` file. If you use a different inventory system, adapt the format accordingly.

## Required Items

| Item | Label | Weight | Stackable | Description |
|---|---|---|---|---|
| `fertilizer` | Fertilizer | 1200 | ❌ | Bag of soil / fertilizer for the pot |
| `weed_pot` | Pot | 1200 | ❌ | Placeable planting pot |
| `weed_bench` | Bench | 18000 | ❌ | Placeable packing station |
| `plastic_bag` | Plastic Bag | 1 | ✅ | Used for packing buds |
| `rollingpaper` | Rolling Paper | 1 | ✅ | Used for rolling joints |
| `scissors_weed` | Scissors | 1 | ✅ | Used for harvesting buds |
| `watering_can` | Watering Can | 1200 | ✅ | Fills with water, has durability |
| `seed_weed` | Weed Seed | 1 | ✅ | Seed to plant in a pot |

## ox_inventory Configuration

```lua
-- Place this in your ox_inventory items.lua file

["fertilizer"] = {
    label = "Fertilizer",
    weight = 1200,
    stack = false,
    close = false,
    consume = 0,
},

["weed_pot"] = {
    label = "Pot",
    weight = 1200,
    stack = false,
    close = false,
    consume = 0,
    buttons = {
        {
            label = "Place",
            action = function(slot)
                client.closeInventory()
                exports["zWeed"]:startPropPositioning(
                    `bzzz_growing_freepot_a`, slot,
                    { server = "zweed:createNewPlant" }
                )
            end
        }
    }
},

["weed_bench"] = {
    label = "Bench",
    weight = 18000,
    stack = false,
    close = false,
    consume = 0,
    buttons = {
        {
            label = "Place",
            action = function(slot)
                client.closeInventory()
                exports["zWeed"]:startPropPositioning(
                    `weed_bench`, slot,
                    { server = "zWeed:AddPackingStation" }
                )
            end
        }
    }
},

["plastic_bag"] = {
    label = "Plastic Bag",
    weight = 1,
    stack = true,
    close = false,
},

["rollingpaper"] = {
    label = "Rolling Paper",
    weight = 1,
    stack = true,
    close = true,
},

["scissors_weed"] = {
    label = "Scissors",
    weight = 1,
    stack = true,
    close = true,
},

["watering_can"] = {
    label = "Watering Can",
    weight = 1200,
    stack = true,
    close = true,
    durability = true,
    client = {
        export = "zWeed.useWateringCan"
    },
},

["seed_weed"] = {
    label = "Weed Seed",
    weight = 1,
    stack = true,
    close = true,
},
```

## Placeable Items

The `weed_pot` and `weed_bench` items use the **positioning system** (`client/positioning.lua`). When a player clicks the "Place" button in their inventory, the prop positioning mode activates:

- **Left Click** — Confirm placement
- **Scroll Wheel** — Rotate object (X axis by default)
- **SHIFT + Scroll** — Rotate on Z axis
- **CTRL + Scroll** — Rotate on Y axis
- **ESC** — Cancel placement

> [!IMPORTANT]
> The positioning system export `startPropPositioning` is registered via `exports('startPropPositioning', ...)`. Make sure `zWeed` is started before the inventory resource tries to call the export.
