---
title: /subtypes
position: 4.0
type: get
description: Get All Sub Types
right_code: |
  ~~~ json
  {
    "subtypes": [
      "EX",
      "Special",
      "Restored",
      "Level Up",
      "MEGA",
      "Technical Machine",
      "Item",
      "Stadium",
      "Supporter",
      "Stage 1",
      "GX",
      "Pokémon Tool",
      "Basic",
      "LEGEND",
      "Stage 2",
      "BREAK",
      "Rocket's Secret Machine"
    ]
  }
  ~~~
  {: title="Response" }
---

~~~ ruby
require 'pokemon_tcg_sdk'

types = Pokemon::Subtype.all
~~~
{: title="ruby" }

~~~ python
from pokemontcgsdk import Type

types = Subtype.all()
~~~
{: title="python" }

~~~ elixir
types = Pokemon.Subtype.all
~~~
{: title="elixir" }

~~~ javascript
// todo
~~~
{: title="javascript"}

~~~ php
<?php

$types = Pokemon::Subtype()->all();
~~~
{: title="php"}

~~~ bash
curl "https://api.pokemontcg.io/v1/subtypes"
~~~
{: title="bash"}