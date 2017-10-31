---
title: Find by hp
position: 1.1
type: get
description: Get Cards by Hp
right_code: |
  ~~~ json
  {  
    "cards":[  
      {
        "id": "xy4-24",
        "name": "M Manectric-EX",
        "nationalPokedexNumber": 310,
        "hp": "210",
        "imageUrl": "https://images.pokemontcg.io/xy4/24.png",
        ...
      },
    ]
  }
  ~~~
  {: title="Response" }
---

The following fields allow the modifiers gt (greater than), gte (greater than or equal to), lt (less than), and lte (less than or equal to) to used in the url parameter:

- attackDamage
- attackCost
- retreatCost
- hp

~~~ ruby
require 'pokemon_tcg_sdk'

cards = Pokemon::Card.where(hp: 'gt200').all
~~~
{: title="ruby" }

~~~ python
from pokemontcgsdk import Card

cards = Card.where(hp='gt200').all()
~~~
{: title="python" }

~~~ elixir
cards = Pokemon.Card.where(hp: "gt200")
~~~
{: title="elixir" }

~~~ javascript
const pokemon = require('pokemontcgsdk')

pokemon.card.all({ hp: 'gt200'})
.on('data', card => {
    console.log(card.name)
})

~~~
{: title="javascript"}

~~~ php
<?php

$cards = Pokemon::Card()->where([
  'hp' => 'gt200'
])->all();
~~~
{: title="php"}

~~~ bash
curl "https://api.pokemontcg.io/v1/cards?hp=gt200"
~~~
{: title="bash"}