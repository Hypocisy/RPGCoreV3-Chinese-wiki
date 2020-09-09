Picks points near **every** target which was input. If we roll to pick an entity, but no entities are available, no target will be picked.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | / | / | nearby | / | / |
| face-origin | boolean | when picking a point, the picked point will face the origin (entities must be set to be copied.) | false | no | no |
| entity-as-copy | boolean | when picking an entity, we will instead copy the location | false | no | no |
| total-target-points | decimal | points to pick per target supplied | 1 | no | yes |
| minimum-distance | decimal | minimum distance from the original | 0 | no | yes |
| maximum-distance | decimal | maximum distance from the original | 1 | no | yes |
| entity-target-chance | percentage | chance to pick an entity within range rather then a point | 50% | no | yes |
| exclude-self | boolean | among the entities picked, exclude the input | true | no | no |