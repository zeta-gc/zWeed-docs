# Developer Guide

## Creating a Custom Bridge

### Step 1: Copy the Template

For example, to create a new inventory bridge for `qs-inventory`:

1. Copy `bridge/inventory/custom.lua`
2. Rename to `bridge/inventory/qs-inventory.lua`
3. Change the guard check:

```lua
if Bridge._inventory ~= 'qs-inventory' then return end
```

### Step 2: Implement the Functions

Replace each function body with your system's API calls:

```lua
function Bridge.Inventory.Search(source, searchType, item)
    return exports['qs-inventory']:Search(source, searchType, item)
end

function Bridge.Inventory.AddItem(source, item, count, metadata)
    return exports['qs-inventory']:AddItem(source, item, count, nil, metadata)
end
-- ... etc
```

### Step 3: Update Config

In `config.lua`:
```lua
Config.Inventory = 'qs-inventory'
```

### Step 4: Update Detection (Optional)

In `bridge/_loader.lua`, add to the detection map:
```lua
Bridge._inventory = detectBridge(Config.Inventory, {
    ['ox_inventory']   = 'ox_inventory',
    ['qb-inventory']   = 'qb-inventory',
    ['qs-inventory']   = 'qs-inventory',  -- NEW
})
```

## Adding a New Locale

1. Create `locales/xx.lua`
2. Copy `locales/en.lua` as a template
3. Translate all strings
4. Set `Config.Locale = 'xx'`

## Adding a New Plant Type

In `config.lua`:

```lua
Config.PlantTypes.seed_tobacco = {
    label       = 'Tobacco',
    potModel    = 'your_pot_model',
    plantModel  = 'your_plant_model',
    budModel    = 'your_bud_model',
    harvestItem = 'tobacco_leaf',
    seedItem    = 'seed_tobacco',
    budBones    = {6, 7, 8, 9, 10},
}
```

Register the corresponding items in your inventory system.
