# Rules

## Values

**Port safety values**

| | |
| :--- | :--- |
| Very low | 0 |
| Low | 1 |
| Mid | 2 |
| High | 3 |

**Goods base values**

| | |
| :--- | :--- |
| cheap | 4 |
| Mid | 30 |
| Expensive | 75 |
| Very expensive | 150 |

**Rarity values**

| Rarity mul (for legal) | | Rarity value (for smuggle) | |
| :--- | :--- | :--- | :--- |
| Common | x1 | Common | 0 |
| Uncommon | x2 | Uncommon | 1 |
| Rare | x4 | Rare | 2 |
| Very rare | x8 | Very rare | 3 |


**Distance Matrix (in Distance Units, DU)**

|      | Novus Capitolium | Harmonious Spire | Echoing Gallery | The Mire's Gaze | The Gilded Hand | The Edge Heap | The Grand Nexus |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Novus Capitolium** | - | 12 | 14 | 20 | 22 | 25 | 8 |
| **Harmonious Spire** | 12 | - | 5 | 18 | 20 | 23 | 10 |
| **Echoing Gallery** | 14 | 5 | - | 21 | 23 | 26 | 12 |
| **The Mire's Gaze** | 20 | 18 | 21 | - | 15 | 18 | 24 |
| **The Gilded Hand** | 22 | 20 | 23 | 15 | - | 6 | 28 |
| **The Edge Heap** | 25 | 23 | 26 | 18 | 6 | - | 30 |
| **The Grand Nexus** | 8 | 10 | 12 | 24 | 28 | 30 | - |

## Equations

### Prices before legality
*   If port sells
    *   `price = Base val - (1d6 x Rarity mul)`
*   If port buys
    *   `price = Base val + (1d6 x Rarity mul)`
*   Else
    *   `price = Base val + (1d6 - 3)`

### Prices with legality
*   If good is legal
    *   no modifier
*   If good is restricted and is listed
    *   add `1d6*3` to price
*   If good is illegal and is listed
    *   If port safety $\le$ Low
        *   add `1d6*5` to price
    *   Else
        *   add `1d6*8` to price
*   Else
    *   If port safety $\le$ very low
        *   no modifier
    *   Else
        *   Not sellable

### Smuggle difficulty score
`= port safety + rarity val`

### Smuggle check
*   Roll 6d6
*   If (num of die with ≥3) $\ge$ smuggle diff score
    *   success
*   Else
    *   failure

### Consequences of smuggle failures
*   Random illegal good reduced by `1-(# of die ≥ 3)/6`
*   If port safety > Low
    *   Being fined by `200 + 1d6 * port safety * 10` credits
*   Else
    *   no additional punishment

### Sailing

A standard ship travels `4` DU per cycle. Better ships the player later can purchase may travel faster.

- sailing time = `Ceiling(Distance in DU / 4)` cycles
- sailing cost = `5 * sailing time` credits
