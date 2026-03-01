# Inventory Bridge

The inventory bridge provides a unified API for all inventory operations.

## API (Server-Side)

| Function | Parameters | Returns | Description |
|---|---|---|---|
| `Bridge.Inventory.Search` | `source, type, item` | `number\|table` | Search inventory by count or slots |
| `Bridge.Inventory.AddItem` | `source, item, count, metadata` | `boolean` | Add items to player |
| `Bridge.Inventory.RemoveItem` | `source, item, count, metadata, slot` | `boolean` | Remove items from player |
| `Bridge.Inventory.CanCarry` | `source, item, count` | `boolean` | Check if player can carry |
| `Bridge.Inventory.SetDurability` | `inv, slot, durability` | — | Set item durability |
| `Bridge.Inventory.GetSlots` | `source, item` | `table` | Get slot data for item |
| `Bridge.Inventory.RegisterDropOnItem` | `data` | — | Register drag-and-drop handler |

## API (Client-Side)

| Function | Parameters | Returns | Description |
|---|---|---|---|
| `Bridge.Inventory.SearchClient` | `type, item` | `number\|table` | Client-side search |
| `Bridge.Inventory.SearchClientFull` | `type, item, ...` | `number\|table` | Client-side search (full args) |
| `Bridge.Inventory.DisplayMetadata` | `key, label` | — | Register metadata display |
| `Bridge.Inventory.CloseInventory` | — | — | Close player inventory |
| `Bridge.Inventory.SetBusy` | `busy` | — | Set inventory busy state |

## Supported Implementations

- **ox_inventory**: Fully implemented
- **qb-inventory**: Stub (implement your API calls)
- **custom**: Template for any inventory system
