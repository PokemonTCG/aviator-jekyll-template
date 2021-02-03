---
title: /rarities
position: 6.0
type: get
description: Get All Rarities
right_code: |
  ~~~ json
  {
    "data": [
        "Amazing Rare",
        "Common",
        "LEGEND",
        "Promo",
        "Rare",
        "Rare ACE",
        "Rare BREAK",
        "Rare Holo",
        "Rare Holo EX",
        "Rare Holo GX",
        "Rare Holo LV.X",
        "Rare Holo Star",
        "Rare Holo V",
        "Rare Holo VMAX",
        "Rare Prime",
        "Rare Prism Star",
        "Rare Rainbow",
        "Rare Secret",
        "Rare Shining",
        "Rare Shiny",
        "Rare Shiny GX",
        "Rare Ultra",
        "Uncommon"
    ]
  }
  ~~~
  {: title="Response" }
---

~~~ bash
curl "https://api.pokemontcg.io/v2/rarities"
~~~
{: title="bash"}