This repository documents the requirements to reach each item location in Hero's Spirit.

# Format

```json
{
    "id": "12.24.31",
    "tags": [["Hammer"], ["SilverKey", "Compass"], ["10 Sword"]],
    "notes": "hi im a stupid note"
}
```

`id` is structured as `<map id>.<x>.<y>`

`tags` are a two dimensional array. The outer array connects its elements with OR, the inner array connects its elements with AND. The example above reads as "Hammer OR (Silver Key AND Compass)".

Valid tags: `Hammer`, `Boots`, `Compass`, `Spectacles`, `LavaCharm`, `WindRing`, `BlueSword`, `BlueShield`, `RedSword`, `RedShield`, `SilverKey`, `GoldKey`, `RedKey`, `GreenKey`, `BlueKey`, `TealKey`, `PurpleKey`, `SkeletonKey`, `Sword`, `PortalStone`, `Gem`, `Treasure`, `ShrineKey`

If the first character of a tag is numeric, it specifies the amount needed in the format `<amount> <tag>`.

`notes` are optional

# Assumptions for simplicity

- The starting point is normal and all portals and transitions connect as usual
- Gold Sword, Shields and Stopwatches are not shuffled (so they may be used from their normal locations)

# Progress

- [ ] DustShelf
- [ ] ThroneRoom
- [ ] ExplodingThroneRoom
- [ ] CastleRuins
- [x] NorthMundeman
- [x] SouthMundeman
- [ ] VerdantCoast
- [ ] OtherworldArena
- [x] CastleGrounds
- [ ] Sanctuary
- [ ] TheTunnels
- [ ] Luddershore
- [ ] TheTundra
- [ ] FrozenShore
- [ ] HallowGround
- [x] SouthernSwamp
- [ ] DragonsLair
- [ ] CorruptedCastle
- [ ] CastleMonillud
- [ ] TheUnderworld
- [ ] Otherworld
- [ ] MoltenCavern
- [ ] TheDungeons
- [ ] ItemShop
- [ ] Convergence
- [ ] TrialOfReality
- [ ] HauntedManse
- [ ] SmugglersRoad
- [ ] SmugglersRuin

# TODO

Logic for Orange Crystal, Mirror, NG+ exclusive connections
