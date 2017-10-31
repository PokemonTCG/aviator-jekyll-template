---
title: /supertypes
position: 5.0
type: get
description: Get All Super Types
right_code: |
  ~~~ json
  {
    "supertypes": [
      "Energy",
      "Pokémon",
      "Trainer"
    ]
  }
  ~~~
  {: title="Response" }
---

~~~ ruby
require 'pokemon_tcg_sdk'

types = Pokemon::Supertype.all
~~~
{: title="ruby" }

~~~ python
from pokemontcgsdk import Type

types = Supertype.all()
~~~
{: title="python" }

~~~ elixir
types = Pokemon.Supertype.all
~~~
{: title="elixir" }

~~~ javascript
// todo
~~~
{: title="javascript"}

~~~ php
<?php

$types = Pokemon::Supertype()->all();
~~~
{: title="php"}

~~~ bash
curl "https://api.pokemontcg.io/v1/supertypes"
~~~
{: title="bash"}