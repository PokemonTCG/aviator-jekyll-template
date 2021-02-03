---
title: /sets
position: 2.0
type: get
description: Get All Sets
right_code: |
  ~~~ json
    {
      "data": [
        {
          "id": "base1",
          "name": "Base",
          "series": "Base",
          "printedTotal": 102,
          "total": 102,
          "legalities": {
            "unlimited": "Legal"
          },
          "ptcgoCode": "BS",
          "releaseDate": "1999/01/09",
          "updatedAt": "2020/08/14 09:35:00",
          "images": {
            "symbol": "https://images.pokemontcg.io/base1/symbol.png",
            "logo": "https://images.pokemontcg.io/base1/logo.png"
          }
        },
        {
          "id": "base2",
          "name": "Jungle",
          "series": "Base",
          "printedTotal": 64,
          "total": 64,
          "legalities": {
            "unlimited": "Legal"
          },
          "ptcgoCode": "JU",
          "releaseDate": "1999/06/16",
          "updatedAt": "2020/08/14 09:35:00",
          "images": {
            "symbol": "https://images.pokemontcg.io/base2/symbol.png",
            "logo": "https://images.pokemontcg.io/base2/logo.png"
          }
        },
        {...},
        {...}
    ]
    }
  ~~~
  {: title="Response" }
---

These are the supported query string parameters:

q
: The search query. Examples can be found below.

page
: The page of data to access. Defaults to 1.

pageSize
: The maximum amount of cards to return. Defaults to 250 (max is also 250).

orderBy
: The field(s) to order the results by. Examples can be found below.

~~~ bash
# Get all sets
curl "https://api.pokemontcg.io/v2/sets"

# Filter cards
curl "https://api.pokemontcg.io/v2/sets?q=legalities.standard:legal"

# Get specific page of data
curl "https://api.pokemontcg.io/v2/sets?page=2&pageSize=10"
~~~
{: title="bash"}

Look at the /cards endpoint for more details on the advanced query syntax.