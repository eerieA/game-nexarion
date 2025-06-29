# Rules

## Base values

| Port safety | | Base values | |
| :--- | :--- | :--- | :--- |
| Very low | 0 | cheap: | 4 |
| Low | 1 | Mid: | 30 |
| Mid | 2 | Expensive: | 75 |
| High | 3 | Very expensive: | 150 |

| Rarity mul (for legal) | | Rarity value (for smuggle) | |
| :--- | :--- | :--- | :--- |
| Common | x1 | Common | 0 |
| Uncommon | x2 | Uncommon | 1 |
| Rare | x4 | Rare | 2 |
| Very rare | x8 | Very rare | 3 |

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
    *   If port safety ≤ Low
        *   add `1d6*5` to price
    *   Else
        *   add `1d6*8` to price
*   Else
    *   If port safety ≤ very low
        *   no modifier
    *   Else
        *   Not sellable

### Smuggle difficulty score
`= port safety + rarity val`

### Smuggle check
*   Roll 6d6
*   If (num of die with ≥3) ≥ smuggle diff score
    *   success
*   Else
    *   failure

### Consequences of smuggle failures
*   Random illegal good reduced by `1-(# of die ≥ 3)/6`
*   If port safety > Low
    *   Being fined by `200 + 1d6 * port safety * 10`
*   Else
    *   no additional punishment

### Moving
*   Cost 30 credits to buy supplies