# Events Reference

## Server Events (receive on server)

| Event | Parameters | Description |
|---|---|---|
| `zweed:createNewPlant` | `model, coords, rotation` | Place a new pot |
| `plant:waterPlant` | `plantId, amount` | Water a plant |
| `plant:addSoil` | `plantId, amount` | Add soil to a plant |
| `plant:addSeed` | `plantId, seedItem` | Plant a seed |
| `plant:addFertilizer` | `plantId, fertType` | Apply fertilizer |
| `zWeed:despawnPlant` | `plantId` | Remove a plant |
| `zWeed:AddPackingStation` | `model, coords, rotation` | Place a packing bench |
| `zWeed:PickupPackingStation` | `stationId` | Pick up a packing bench |
| `zWeed:GivePackedWeed` | — | Pack weed buds + bags |
| `zWeed:increaseDurability` | `data, slot, quantity` | Refill watering can |

## Client Events (receive on client)

| Event | Parameters | Description |
|---|---|---|
| `zWeed:PlantUpdate` | `id, plantData` | Single plant update |
| `zWeed:PlantsFullSync` | `syncId, chunkIndex, totalChunks, plantChunk` | Batch sync chunk |
| `zWeed:SyncStart` | `syncId, totalChunks` | Begin sync session |
| `zWeed:SyncEnd` | `syncId` | End sync session |
| `zWeed:despawnPlant` | `plantId` | Remove plant from scene |
| `zWeed:CreatePackingStation` | `stationData` | Create bench on client |
| `zWeed:DeletePackingStation` | `stationId` | Remove bench from client |
| `zWeed:PlayJoingCreationAnim` | `animType` | Play grinding/rolling anim |

## Callbacks (lib.callback)

| Callback | Parameters | Returns | Description |
|---|---|---|---|
| `zWeed:harvestBud` | `plantID, budIndex, netID` | `boolean` | Harvest a bud (server-side logic) |
| `plant:getSpawnData` | `plantID` | `table` | Get plant data for spawning |
| `zWeed:requestPlants` | — | — | Request full plant sync |
