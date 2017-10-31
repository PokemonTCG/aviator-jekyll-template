---
title: /sets/:id
position: 2.1
type: get
description: Get Set
right_code: |
  ~~~ json
  {  
    "set":{  
      "code":"xy1",
      "name":"XY",
      "series":"XY",
      "totalCards":140,
      "standardLegal":true,
      "releaseDate":"02/05/2014"
    }
  }
  ~~~
  {: title="Response" }
---

Returns a specific set by the set code

~~~ ruby
require 'pokemon_tcg_sdk'

set = Pokemon::Set.find('xy1')
~~~
{: title="ruby" }

~~~ python
from pokemontcgsdk import Set

set = Set.find('xy1')
~~~
{: title="python" }

~~~ elixir
set = Pokemon.Set.find("base1")
~~~
{: title="elixir" }

~~~ javascript
// todo
~~~
{: title="javascript"}

~~~ php
<?php

$set = Pokemon::Set()->find('base1');
~~~
{: title="php"}

~~~ bash
curl "https://api.pokemontcg.io/v1/sets/xy1"
~~~
{: title="bash"}