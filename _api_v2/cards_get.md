---
title: /cards/:id
position: 1.1
type: get
description: Get Card
right_code: |
  ~~~ json
  {
  "data": {
    "id": "xy1-1",
    "name": "Venusaur-EX",
    "supertype": "Pokémon",
    "subtypes": [
      "Basic",
      "EX"
    ],
    "hp": 180,
    "types": [
      "Grass"
    ],
    "evolvesTo": [
      "M Venusaur-EX"
    ],
    ...
  }
  ~~~
  {: title="Response" }
---

Returns a specific card by id

~~~ bash
curl "https://api.pokemontcg.io/v2/cards/xy7-54"
~~~
{: title="bash"}