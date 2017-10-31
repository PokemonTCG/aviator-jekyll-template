---
title: /sets
position: 2.0
type: get
description: Get All Sets
right_code: |
  ~~~ json
    {  
    "sets":[  
        {
          "code": "base1",
          "ptcgoCode": "BS",
          "name": "Base",
          "series": "Base",
          "totalCards": 102,
          "standardLegal": false,
          "expandedLegal": false,
          "releaseDate": "01/09/1999",
          "symbolUrl": "https://images.pokemontcg.io/base1/symbol.png",
          "logoUrl": "https://images.pokemontcg.io/base1/logo.png"
        },
        {
          "code": "base2",
          "ptcgoCode": "JU",
          "name": "Jungle",
          "series": "Base",
          "totalCards": 64,
          "standardLegal": false,
          "expandedLegal": false,
          "releaseDate": "06/16/1999",
          "symbolUrl": "https://images.pokemontcg.io/base2/symbol.png",
          "logoUrl": "https://images.pokemontcg.io/base2/logo.png"
        },
        {...},
        {...}
    ]
    }
  ~~~
  {: title="Response" }
---

Each field below can be used as a query parameter:

name
: The name of the set

ptcgoCode
: The Pokémon Trading Card Game Online Code

series
: The series the set belongs to

totalCards
: The number of cards in the set (excluding secret rares)

standardLegal
: Whether or not the set is tournament legal for standard format

expandedLegal
: Whether or not the set is tournament legal for expanded format

page
: The page of data to return

pageSize
: The number of cards to return (max 100)

#### Other Fields In Reponse

The fields below are also part of the response (if not null), but cannot currently be used as query parameters.

code
: The code name of the set

releaseDate
: The data the set was released

symbolUrl
: The symbol of the set

logoUrl
: The logo of the set

~~~ ruby
require 'pokemon_tcg_sdk'

# Get all Sets
sets = Pokemon::Set.all

# Filter Sets
sets = Pokemon::Set.where(standardLegal: true).all

# Get sets on a specific page / pageSize
sets = Pokemon::Set.where(page: 2).where(pageSize: 10).all
~~~
{: title="ruby" }

~~~ python
from pokemontcgsdk import Set

# Get all Sets
sets = Set.all()

# Filter Sets
sets = Set.where(standardLegal=true).all()

# Get sets on a specific page / pageSize
sets = Set.where(page=2).where(pageSize=10).all()
~~~
{: title="python" }

~~~ elixir
# Get all Sets
sets = Pokemon.Set.all

# Filter sets
sets = Pokemon.Set.where(standardLegal: true)

# Get sets on a specific page / pageSize
sets = Pokemon.Set.where(page: 2, pageSize: 10)
~~~
{: title="elixir" }

~~~ javascript
// todo
~~~
{: title="javascript"}

~~~ php
<?php

# Get all Sets
$sets = Pokemon::Set()->all();

# Filter Sets
$set = Pokemon::Set()->where(['standardLegal' => 'true'])->all();

# Get sets on a specific page / pageSize
$sets = Pokemon::Set()->where([
    'page'     => 2,
    'pageSize' => 10
])->all();
~~~
{: title="php"}

~~~ bash
# Get all sets
curl "https://api.pokemontcg.io/v1/sets"

# Filter cards
curl "https://api.pokemontcg.io/v1/sets?standardLegal=true"

# Get specific page of data
curl "https://api.pokemontcg.io/v1/sets?page=2&pageSize=10"
~~~
{: title="bash"}