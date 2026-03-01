# Bridge System

zWeed uses a **bridge pattern** to decouple game logic from specific third-party resources. This allows the script to work with any combination of inventory, target, notification, framework, and skill systems.

## How It Works

1. On resource start, `bridge/_loader.lua` auto-detects which systems are available
2. Each bridge file has a **guard check** — only the matching adapter initializes
3. All game logic calls `Bridge.*` functions instead of direct exports

## Architecture

```
bridge/
├── _loader.lua          # Auto-detection & Locale system
├── inventory/
│   ├── ox_inventory.lua # Full implementation
│   ├── qb-inventory.lua # Stub
│   └── custom.lua       # Template
├── target/
│   ├── ox_target.lua    # Full implementation
│   ├── qb-target.lua    # Stub
│   └── custom.lua       # Template
├── notify/
│   ├── ox_lib.lua       # Full implementation
│   ├── qb-core.lua      # Full implementation
│   ├── okokNotify.lua   # Full implementation
│   └── custom.lua       # Template
├── framework/
│   ├── esx.lua          # Full implementation
│   ├── qb-core.lua      # Stub
│   └── standalone.lua   # Full implementation
└── skills/
    ├── none.lua         # Default (no skills)
    ├── peakville.lua    # Full implementation
    └── custom.lua       # Template
```

## Creating a Custom Bridge

See the [Developer Guide](../developer-guide.md) for step-by-step instructions on creating custom adapters.
