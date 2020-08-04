Directory: "./../Attributes.yml"  
Module: Attributes

This allows you add additional attributes to your server. Note that the SkillModule and DamageModule both generate a number of additional attributes which are related to their individual configurations. There is a very limited section of attributes which actually requires you to manually define.

# How to create new attributes

This covers general item configuration, equipment still may need to specify the options defined here.

| Option | Type | Description |
|-|-|-|
| minimum | decimal | fixed threshold we cannot evaluate below |
| maximum | decimal | fixed threshold we cannot evaluate above |
| minimum-id | string | attribute we cannot evaluate below |
| maximum-id | string | attribute we cannot evaluate above |
| defaults | decimal | always added to base value of attribute |
| advanced-migrations | section | how to affect other attributes |

Beneath is an example for the "intelligence" attribute, capping out at 999 and defaulting to 1 point. Per 5 points in intelligence you would gain 1 energy shield and 1 point of mana.

```
    INTELLIGENCE: 
      default: 1
      minimum: 999
      advanced-migrations:
        SHIELD_AMOUNT:
          BASE: 0.2
          INCREASED: 0
          MULTIPLIED: 0
        MANA_AMOUNT:
          BASE: 0.2
          INCREASED: 0
          MULTIPLIED: 0
```
