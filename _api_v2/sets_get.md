---
title: /sets/:id
position: 2.1
type: get
description: Get Set
right_code: |
  ~~~ json
  {
    "data": {
      "id": "sm1",
      "name": "Sun & Moon",
      "series": "Sun & Moon",
      "printedTotal": 149,
      "total": 149,
      "legalities": {
        "unlimited": "Legal",
        "expanded": "Legal"
      },
      "ptcgoCode": "SUM",
      "releaseDate": "2017/02/03",
      "updatedAt": "2019/04/10 19:59:00",
      "images": {
        "symbol": "https://images.pokemontcg.io/sm1/symbol.png",
        "logo": "https://images.pokemontcg.io/sm1/logo.png"
      }
    }
  }
  ~~~
  {: title="Response" }
---

Returns a specific set by the set code


~~~ bash
curl "https://api.pokemontcg.io/v2/sets/sm1"
~~~
{: title="bash"}