---
title: /cards/:id
position: 1.1
type: get
description: Get Card
right_code: |
  ~~~ json
  {
    "card": {
      "id": "xy7-54",
      "name": "Gardevoir",
      "imageUrl": "https://images.pokemontcg.io/xy7/54.png",
      "subtype": "Stage 2",
      "supertype": "Pokémon",
      ...
    }
  }
  ~~~
  {: title="Response" }
---

Returns a specific card by id

~~~ ruby
require 'pokemon_tcg_sdk'

card = Pokemon::Card.find('xy7-54')
~~~
{: title="ruby" }

~~~ python

from pokemontcgsdk import Card

card = Card.find('xy7-54')
~~~
{: title="python" }

~~~ elixir
card = Pokemon.Card.find("xy7-54")
~~~
{: title="elixir" }

~~~ javascript
const pokemon = require('pokemontcgsdk')

pokemon.card.find('xy7-54')
.then(result => {
    console.log(result.card.name)
})
~~~
{: title="javascript"}

~~~ php
<?php

$card = Pokemon::Card()->find('xy7-54');
~~~
{: title="php"}

~~~ bash
curl "https://api.pokemontcg.io/v1/cards/xy7-54"
~~~
{: title="bash"}