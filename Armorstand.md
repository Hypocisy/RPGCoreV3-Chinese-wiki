Create a temporary armorstand fixed at the given position, note that the armorstand is packet based and not meant to be persistent. Since the armorstand exists on packet level it wont be targetted by any other resource.

The armorstand cannot be targetted.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | / | fakestand | yes | no |
| duration | integer | how many ticks to persist | 100 | no | yes |
| representing-item | material | material to use as a hat | / | no | no |
| random | decimal | random offset applied | 0.0 | no | yes |