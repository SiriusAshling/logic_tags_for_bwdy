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

Valid tags: `Hammer`, `Boots`, `Compass`, `Spectacles`, `LavaCharm`, `WindRing`, `BlueSword`, `BlueShield`, `RedSword`, `RedShield`, `SilverKey`, `GoldKey`, `RedKey`, `GreenKey`, `BlueKey`, `TealKey`, `PurpleKey`, `SkeletonKey`, `Sword`, `PortalStone`, `Treasure`, `ShrineKey`, `UnderworldKey`, `OrangeCrystal`, `Carrot`, `Mirror`, `NewGame`, `NewGamePlus`

Using `UnderworldKey` implies `NewGamePlus`.

If the first character of a tag is numeric, it specifies the amount needed in the format `<amount> <tag>`. It is still valid for a tag to appear multiple times like `GoldKey, GoldKey`, in which case it should be treated as requiring multiple.

`notes` are optional

# Assumptions for simplicity

- The starting point is normal and all portals and transitions connect as usual
- Gold Sword, Shields and Stopwatches are not shuffled (so they may be used from their normal locations)
- Hearts are not shuffled (can add this without much overhead, just saving work for now)

# Progress

- [x] DustShelf
- [ ] ThroneRoom
- [ ] ExplodingThroneRoom
- [ ] CastleRuins
- [x] NorthMundeman
- [x] SouthMundeman
- [ ] VerdantCoast
- [ ] OtherworldArena
- [x] CastleGrounds
- [ ] Sanctuary
- [x] TheTunnels
- [ ] Luddershore
- [x] TheTundra
- [ ] FrozenShore
- [x] HallowGround
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
- [x] HauntedManse
- [ ] SmugglersRoad
- [ ] SmugglersRuin

# Notes

It has been assumed that the player has no global progress.

Coin Shop items aren't really normal items and don't fit that well into the id concept, also feel like shuffling them might not be desirable.
Since there's a P-Coin in the Coin Shop (`8.114.120`) and by the save format items are guaranteed to not move, could just hack to use that P-Coins logic in combination with the player's current Coin count to determine whether the player can buy shop coin items. But really, the coin shop items don't do much anyway and probably are never logically relevant.

# TODO
Turn empty tag arrays two dimensional
Check Hallow Ground again with the newfound options while pathing Frozen Shore
