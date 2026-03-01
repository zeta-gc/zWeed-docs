# Framework Bridge

## API (Server-Side Only)

| Function | Parameters | Returns | Description |
|---|---|---|---|
| `Bridge.Framework.GetObject` | — | `table\|nil` | Get framework object |
| `Bridge.Framework.GetPlayerGroup` | `source` | `string` | Get player group/role |
| `Bridge.Framework.GetPlayerIdentifier` | `source` | `string` | Get player license |
| `Bridge.Framework.OnPlayerLoaded` | `callback` | — | Register player load handler |

## Standalone Mode

When using standalone mode, admin permissions are checked via FiveM ace permissions:
```cfg
add_ace group.admin command.zweed_admin allow
```
