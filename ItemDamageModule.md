Directory: "./../ItemDamageModule.yml"  
Module: ItemDamageModule

This module allows you to create items with certain durability, this durability is tracked **separately** from minecraft durability. You can setup repairing stations to repair the items in question, the [[BreakdownModule]] is an excelelnt way of acquiring repairing materials but they also could be dropped from mobs. Check [[ItemModule: Materials]] for repair materials.

# Configuring the module

Beneath is the configuration of the module, note that while we say anvil it can be any sort of block in its place.

| Option | Type | Description |
|-|-|-|
| messages | section | messages shown for certain situations |
| damage-on-hurt | slot list | equipment slots that can take damage when hurt |
| damage-on-death | percent | durability lost from all items on death |
| damage-used-weapon | boolean | proper loss of durability for every tool |
| use-anvils-to-repair | location list | locations where repair anvils are |

# How to make an item with custom durability

This is a part of the configuration of an item itself.

| Option | Type | Description |
|-|-|-|
| custom.tags.maximum-durability | integer | the maximum custom durability of the item |
| custom-tags.need-repair-tags | tag list | tags of the repairing material to fix up the item |

