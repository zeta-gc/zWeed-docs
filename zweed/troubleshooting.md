# Troubleshooting

## Plants not spawning

1. Check that `oxmysql` is running and the `plants` table exists
2. Verify `sql/install.sql` was executed
3. Enable `Config.Debug = true` and check console for bridge detection messages
4. Ensure `ox_lib` is started before `zWeed`

## Bridge not detected

If console shows `NOT FOUND` for a bridge:
1. Ensure the dependency resource is started
2. If using manual config, verify the name matches exactly (e.g., `'ox_inventory'` not `'ox_inv'`)

## Interactions not appearing

1. Verify your target system is running (ox_target / qb-target)
2. Check that the required items exist in your inventory system
3. Ensure `Config.InteractionDistance` is appropriate

## NUI not showing

1. Check browser devtools (F8) for JavaScript errors
2. Ensure `ui/ui.html` is listed in `fxmanifest.lua` files section
3. Verify audio files are present in `ui/`

## Packing stations not saving

1. Check that the `weed_packing_stations` table exists in your database
2. Verify `oxmysql` connection is working
3. Check server console for SQL errors

## Notification errors

If you get `Bridge.Notify is nil`:
1. Check that `Config.Notify` matches an available adapter
2. Ensure the notification resource is started
3. Try setting to `'auto'` for detection

## Performance issues

1. Reduce `Config.PlantRenderDistance` (default: 70)
2. Reduce `Config.MaxConcurrentSpawns` (default: 5)
3. Increase `Config.TickInterval` to reduce tick frequency
