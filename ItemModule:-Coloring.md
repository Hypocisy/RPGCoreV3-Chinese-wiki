Directory: "./../itemmodule/items"  
Module: ItemModule, SkillModule

The following colors are possible to be utilized: BLUE, YELLOW, GREEN, RED, WHITE, BROWN, PURPLE, LIGHT_BLUE, ORANGE, GRAY and BLACK (Owing minecraft limitations, these are the only colors which are possible. There are no plans on adding support for other coloring.)

Check [[ItemModule: Materials]] for means of modifying the colors of existing items.

Warning: The default configuration excludes the coloring system.

# Use of coloring 

Coloring is a system mostly in context with socketing. When you want to socket a skill on an item, the skill needs to match in color. 

If you want to socket a blue jewel, you need a blue slot. If you want to socket a red skill, you need a red slot. White colors are a special case here, it will be treated as a wildcard.

# Making an item able to be colored

Should you want to add colored sockets to an equipment piece beneath is a sample which will create a helmet that can roll red, green, yellow and blue sockets but not white sockets. It is more likely to roll a blue socket on this item, but the other three colors are equally distributed

```yml
TWILIGHT_HELMET:
  id: TWILIGHT_HELMET
  name: "Twilight Helmet"
  material: LEATHER_HELMET
  seed: true
  implicits:
  - ADD RANGE(1,100) TO INTELLIGENCE
  - ADD 0.03 TO CRIT_DAMAGE_SPELL
  - ADD 0.02 TO RESISTANCE_FIRE
  - ADD 0.02 TO RESISTANCE_LIGHTNING
  - ADD 0.02 TO RESISTANCE_COLD
  color-weighing:
    BLUE: 2
    BROWN: 1
    RED: 1
    GREEN: 1
    WHITE: 0
```

# Making a skill able to be colored

The backing-item section of skills permits to define the color of the skill like. Beneath an example where the skill would expect a green slot to be socket into.

```yml
  backing-item:
    material: DIAMOND_HOE
    custom-model: 46
    custom-tags:
      display-binding: SKILL
      skill-color: GREEN
```

# Making a jewel able to be colored

The auto-generated-item-copy section of socketable jewels permits you to define the color of the jewel. Beneath an example where the jewel would expect a blue slot to be socketed into.

```yml

  auto-generate-item-copy: 
    material: DIAMOND
    rarity: RARE
    lore:
    - "Socket on the suitably colored equipment."
    - "Can also be socketed on the passive tree"
    display-binding: SOCKETABLE
    socket-color: BLUE
    dropable:
      weighting: 1.0
      drop-level: 10
      tagging: [JEWEL, CRITICAL]
```