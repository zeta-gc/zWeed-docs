# FAQ

## Can I use this without ESX or QBCore?

Yes! Set `Config.Framework = 'standalone'` to use zWeed without any framework. Admin permissions use FiveM ace permissions instead.

## Does it work with qb-inventory?

A stub is included. You need to implement the actual API calls in `bridge/inventory/qb-inventory.lua` to match your specific qb-inventory version.

## Can I add more plant types?

Yes! Add new entries to `Config.PlantTypes` in `config.lua`. You'll need to register the corresponding seed and harvest items in your inventory system, and have the streamed models available.

## Can I restrict where players plant?

Yes, set `Config.PlantingZone` with polygon coordinates. Set to `nil` for no restriction.

## How do I change the growth speed?

Adjust `Config.SecondsForFullGrowth`. Default is 10800 seconds (3 hours). Lower = faster.

## Can I change the language?

Set `Config.Locale = 'it'` for Italian, or create a new locale file in `locales/`.
