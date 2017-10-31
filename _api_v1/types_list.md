---
title: /types
position: 3.0
type: get
description: Get All Types
right_code: |
  ~~~ json
  {
    "types": [
      "Colorless",
      "Darkness",
      "Dragon",
      "Fairy",
      "Fighting",
      "Fire",
      "Grass",
      "Lightning",
      "Metal",
      "Psychic",
      "Water"
    ]
  }
  ~~~
  {: title="Response" }
---

~~~ ruby
require 'pokemon_tcg_sdk'

types = Pokemon::Type.all
~~~
{: title="ruby" }

~~~ python
from pokemontcgsdk import Type

types = Type.all()
~~~
{: title="python" }

~~~ elixir
types = Pokemon.Type.all
~~~
{: title="elixir" }

~~~ javascript
// todo
~~~
{: title="javascript"}

~~~ php
<?php

$types = Pokemon::Type()->all();
~~~
{: title="php"}

~~~ bash
curl "https://api.pokemontcg.io/v1/types"
~~~
{: title="bash"}