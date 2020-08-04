Directory: "./../Skills"  
Module: Skills

Itemization refers to a skill being acquired as a physical item. The skill system of RPGCore is designed for players to put their skills on their equipment, though if you go for something more permanent you can also use the passive tree as a source for skills (this however will not work for traps and totems, as they require the skill to be socketed on the item.)

# Handling Itemization

The itemization of a skill is handled by the `backing-item` section of it, the backing item section is treated as a complete item - however only the most basic data is stored once the item is generated. The only things that you might want to do is adding coloring and display bindings.

Example Itemization:

```yml
  backing-item:
    material: DIAMOND_HOE
    custom-model: 47
    custom-tags:
      display-binding: SKILL
      skill-color: RED
```

This would create an itemized skill, requiring a red socket (See: [[Items: Coloring]]), having the "SKILL" display binding (See: [[Pointer]]) and using a diamond hoe with the model number 47.