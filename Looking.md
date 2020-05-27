Picks the furthest away block according to where the target is looking, will pick the air block if no solid ones are present. If we pick entities, we take the one that is the closest to the position (if multiple ones are available.)

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | / | / | looking | / | / |
| distance | decimal | maximum travel distance | 10 | no | yes |
| entity-target-distance | decimal | if an entity is within the given range, target them instead | 3 | no | yes |
| target-entity | boolean | if an entity is near, pick the entity instead. | true | no | no |
| ignore-liquid | boolean | allow to phase through liquid blocks | true | no | no |