Only detects motion exceeding 0.01 units within a single tick, the "distance" is accumulating and channels are usually randomly generated so every move trigger counts the distance separately.

| Key | Type | Description | Defaults | Required | Variable |
|-|-|-|-|-|-|
| type | string | | move | yes | no |
| distance | decimal | distance we need to cover to trigger (resets) | 1 | no | yes |
| channel | string | shares the distance with other triggers | random | no | no |