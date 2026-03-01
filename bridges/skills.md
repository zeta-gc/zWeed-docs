# Skills Bridge

## API (Server-Side Only)

| Function | Parameters | Returns | Description |
|---|---|---|---|
| `Bridge.Skills.HasSkill` | `source, skillName` | `boolean` | Check if player has skill |
| `Bridge.Skills.PerformAction` | `source, action, data` | — | Track skill XP/progress |
| `Bridge.Skills.GetHarvestLevel` | `source` | `number` | 0=none, 1=basic, 2=advanced |
| `Bridge.Skills.GetCraftingLevel` | `source` | `number` | Crafting efficiency level |

## Default Mode (`none`)

When skills are set to `'none'`, all functions return defaults (no skill bonuses). Harvest quality is determined randomly.
