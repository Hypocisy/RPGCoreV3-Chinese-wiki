Directory: "./../itemmodule/sockets"  
Module: ItemModule

Socketable jewels are designed to be embedded on an item for additional attributes. Beware that your socketable and your slot both need to match in color. Additional details about coloring can be found here [[ItemModule: Coloring]]

You can access the socketing system either by dropping a socketable on an item or running the "/rc sockets" command while holding the item you want to socket something on. Socketed jewels can be swapped out at no cost.

# Configuration (./../itemmodule/config.yml)

The general configuration of the socketing system.

| Option | Type | Description |
|-|-|-|
| title | string | the title of the details to be printed on the item |
| slots-by-rarity | section | rarity mapped to the extra affix slots on the item |
| extra-socket-breakpoints | section | upgrade level mapped to extra slots gained after upgrading level |
| socketing-message | string | extra line shown above itemized socketables |
| show-named | boolean | instead of showing the effects when socket, shows the name of the socketable |
| empty-socket | string | placeholder contents for when a slot is empty |

# Configuration (./../itemmodule/items)

An item needs to be specified with a number of things so that it can be socketed upon.

If you define a negative number of sockets on the item, you can prevent item rarity from pushing the number up.

| Option | Type | Description |
|-|-|-|
| custom-tags.default-sockets | integer | base amount of slots for sockets |

# Configuration (./../itemmodule/sockets) 

Creating socketables requires the following specifications

| Option | Type | Description |
|-|-|-|
| id | string | the id used by the socketable |
| displayname | string | the displayname of this socketable | 
| effects | attribute list | a list of attributes gained, use fixed attributes only |
| maximum | integer | if greater 0, you do not gain the effect of additional copies |
| auto-generate-item-copy | section | a complete section to specify an RPGCore item |

Beneath is an example for a dexterity socketable jewel. When equipped, it will grant the player 25 dexterity. You have no limit on how many of these jewels you can have socketed, and it will use an emerald as the icon.

```yml
# Can be socketed on green slots of an item.
DEXTERITY_SOCKETABLE:
  # Id of the socketable item, make sure no item id conflicts here
  id: DEXTERITY_SOCKETABLE
  # The name to show for this socketable
  displayname: Dexterity Jewel
  # Add 25 dexterity to the owner when equipped
  effects:
  - ADD 25 TO DEXTERITY
  # No (global) maximum of equipped socketables
  maximum: -1
  auto-generate-item-copy: 
    # Utilize an emerald as it is a green socketable
    material: EMERALD
    # The item is always considered rare
    rarity: RARE
    # Description for the item
    lore:
    - "Use 'rc sockets' to check all sockets."
    - "Drop on an item to view the sockets of it."
    # When dropped will be documented as a socketable
    display-binding: SOCKETABLE
    # Must be socketed on a green slot
    socket-color: GREEN
    # Can be dropped by mobs
    dropable:
      weighting: 1
      drop-level: 10
      tagging: [JEWEL, DEXTERITY]
```
