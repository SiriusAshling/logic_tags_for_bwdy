This repository documents the requirements to reach each item location in Hero's Spirit.

# Format

```json
{
    "id": "12.24.31",
    "tags": [["Hammer"], ["SilverKey", "Compass"]],
    "notes": "hi im a stupid note"
}
```

`id` is structured as `<map id>.<x>.<y>`

`tags` are a two dimensional array. The outer array connects its elements with OR, the inner array connects its elements with AND. The example above reads as "Hammer OR (Silver Key AND Compass)".

Valid tags: `Hammer`, `Boots`, `Compass`, `Spectacles`, `LavaCharm`, `WindRing`, `BlueSword`, `BlueShield`, `RedSword`, `RedShield`, `SilverKey`, `GoldKey`, `RedKey`, `GreenKey`, `BlueKey`, `TealKey`, `PurpleKey`, `SkeletonKey`, `Sword`, `PortalStone`, `Gem`, `Treasure`, `ShrineKey`

`notes` are optional
