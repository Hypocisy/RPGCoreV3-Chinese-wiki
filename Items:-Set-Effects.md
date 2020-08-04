Directory: "./../Items/set-effects.yml", "./../Items/items"  
Module: Items

Set effects are acquired by equipping a number of items which share the same set tag. You can have multiple of the same item, accessory slots also are affected. Entities can be affected by multiple set effects, add the `set-effect` NBT tag to the item to attach it to a certain set effect. Beware that mobs also are affected by set effects, hence giving them real items may make their balancing really messy.

### Setting up a set effect (./../Items/set-effects.yml)

Note that you gain the sum of all set effect tiers, so make sure that effects are **not** duplicates (iE: granting a lv13 skill, then a lv15 skill, then a lv20 skill!)

| Option | Type | Description |
|-|-|-|
| title | string | every set effect on items will generate one listing |
| effects-by-piece.#.unlocked-detail | string list | details when unlocked, no auto details are generated |
| effects-by-piece.#.locked-detail | string list | details when locked, no auto details are generated |
| effects-by-piece.#.skill-acquire | skill:level list | list of main skills acquired with x pieces |
| effects-by-piece.#.attribute-acquire | attribute list | list of attributes acquired with x pieces |
