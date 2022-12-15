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

`tags` are a two dimensional array. The outer array connects its elements with OR, the inner array connects its elements with AND. The example above reads as "(Hammer) OR (Silver Key AND Compass) OR (10 Swords)".

Valid tags:
- Found collectibles: `Hammer`, `Boots`, `Compass`, `Spectacles`, `LavaCharm`, `WindRing`, `BlueSword`, `BlueShield`, `RedSword`, `RedShield`, `SilverKey`, `GoldKey`, `RedKey`, `GreenKey`, `BlueKey`, `TealKey`, `PurpleKey`, `SkeletonKey`, `Sword`, `PortalStone`, `Treasure`, `ShrineKey`, `UnderworldKey`, `OrangeCrystal`, `Mirror`, `FishingRod`, `Fish`
- Game mode: `NewGame`, `NewGamePlus`, `NewGamePlusPlus`
- Global data: `GlitchKey`, `BlueCat`, `SmugglersRoadRestored`

If the first character of a tag is numeric, it specifies the amount needed in the format `<amount> <tag>`. It is still valid for a tag to appear multiple times like `GoldKey, GoldKey`, in which case it should be treated as requiring multiple.

# Assumptions for simplicity

- The starting point is normal and all portals and transitions connect as usual
- Gold Sword, Shields and Stopwatches are not shuffled (so they may be used from their normal locations)
- Cats are not shuffled (so they may be used from their normal locations)
- Hearts are not shuffled (can add this without much overhead, just saving work for now)
- Silver and Gold Doors aren't mapped (technically they should be, but it's a lot of extra work to avoid a type of softlock that probably will never happen anyway)

# Progress
- [x] DustShelf
- [x] ThroneRoom
- [x] ExplodingThroneRoom
- [x] CastleRuins
- [x] NorthMundeman
- [x] SouthMundeman
- [x] VerdantCoast
- [x] OtherworldArena
- [x] CastleGrounds
- [x] Sanctuary
- [x] TheTunnels
- [x] Luddershore
- [x] TheTundra
- [x] FrozenShore
- [x] HallowGround
- [x] SouthernSwamp
- [x] DragonsLair
- [x] CorruptedCastle
- [x] CastleMonillud
- [x] TheUnderworld
- [x] Otherworld
- [x] MoltenCavern
- [x] TheDungeons
- [x] ItemShop
- [x] Convergence
- [x] TrialOfReality
- [x] HauntedManse
- [x] SmugglersRoad
- [x] SmugglersRuin

# Notes

Using `UnderworldKey` implies at least `NewGamePlus` (but it may still be needed to specify `NewGamePlus` to express needing the weaker enemies compared to NG++). None of the game mode tags imply any other game mode.

All the global data requirements can be derived from having access to a certain item:
- `8.89.35` on ANY file (although only NG+ can reach it) -> `BlueCat` (other cats don't have logical implications)
- `41.19.20` on ANY file -> `SmugglersRoadRestored` (assuming it is still the location that restores Smuggler's Road in the randomizer)
- `19.15.2` on ALL files -> `GlitchKey`

Note that this will require some recursion on the reach check since getting access to an item which unlocks a new global data may unlock further items in the same step.

So far only permanent collectibles as well as Underworld doors and Portals have been mapped.

It has been assumed that the player starts with no global progress.

Coin Shop items aren't in one definitive map position, not sure what to do with those.
Since there's a P-Coin in the Coin Shop (`8.114.120`) and by the save format items are guaranteed to not move, could just hack to use that P-Coins logic in combination with the player's current Coin count to determine whether the player can buy shop coin items (either requiring 250 for any to avoid softlocks or enforcing a purchase order).

Since gem shop costs are based on the item on offer, gem requirements have not been noted for those.
