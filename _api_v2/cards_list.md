---
title: /cards
position: 1.0
type: get
description: Get All Cards
right_code: |
  ~~~ json
  {  
    "data":[  
    {
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
      "attacks": [
        {
          "name": "Poison Powder",
          "cost": [
            "Grass",
            "Colorless",
            "Colorless"
          ],
          "convertedEnergyCost": 3,
          "damage": "60",
          "text": "Your opponent's Active Pokémon is now Poisoned."
        },
        {
          "name": "Jungle Hammer",
          "cost": [
            "Grass",
            "Grass",
            "Colorless",
            "Colorless"
          ],
          "convertedEnergyCost": 4,
          "damage": "90",
          "text": "Heal 30 damage from this Pokémon."
        }
      ],
      "weaknesses": [
        {
          "type": "Fire",
          "value": "×2"
        }
      ],
      "retreatCost": [
        "Colorless",
        "Colorless",
        "Colorless",
        "Colorless"
      ],
      "convertedRetreatCost": 4,
      "set": {
        "id": "xy1",
        "name": "XY",
        "series": "XY",
        "printedTotal": 146,
        "total": 146,
        "legalities": {
          "unlimited": "Legal",
          "expanded": "Legal"
        },
        "ptcgoCode": "XY",
        "releaseDate": "02/05/2014",
        "updatedAt": "03/04/2018 10:35:00",
        "images": {
          "symbol": "https://images.pokemontcg.io/xy1/symbol.png",
          "logo": "https://images.pokemontcg.io/xy1/logo.png"
        },
        "_self": "https://beta.pokemontcg.io/sets/xy1"
      },
      "number": "1",
      "artist": "Eske Yoshinob",
      "rarity": "Rare Holo EX",
      "nationalPokedexNumbers": [
        3
      ],
      "legalities": {
        "unlimited": "Legal",
        "expanded": "Legal"
      },
      "images": {
        "small": "https://images.pokemontcg.io/xy1/1.png",
        "large": "https://images.pokemontcg.io/xy1/1_hires.png"
      },
      "tcgplayer": {
        "url": "http://prices.pokemontcg.io/tcgplayer/xy1-1",
        "prices": [
          {
            "holofoil": {
              "low": 0.78,
              "mid": 2.51,
              "high": 12.27,
              "market": 1.38,
              "directLow": 1.99
            }
          }
        ]
      }
    },
    { ... },
    { ... }
    ]
    }
  ~~~
  {: title="Response" }
---
This call will return a maximum of 250 cards. The default is 250.
{: .info }

These are the supported query string parameters:

q
: The search query. Examples can be found below.

page
: The page of data to access. Defaults to 1.

pageSize
: The maximum amount of cards to return. Defaults to 250 (max is also 250).

orderBy
: The field(s) to order the results by. Examples can be found below.


Simple usage:

~~~ bash
# Get all cards
curl "https://api.pokemontcg.io/v2/cards"

# Filter cards
curl "https://api.pokemontcg.io/v2/cards?q=supertype:pokemon types:dragon"

# Get specific page of data
curl "https://api.pokemontcg.io/v2/cards?page=5"
~~~
{: title="bash"}

To perform search queries, you use the `q` parameter. The search syntax is a very familiar Lucene like syntax.

## Keyword matching:

Search for all cards that have "charizard" in the name field.

```
name:charizard
```

Search for the phrase "venusaur v" in the name field.

```
name:"venusaur v"
```

Search for "charizard" in the name field AND the type "mega" in the subtypes field.

```
name:charizard subtypes:mega
```

Search for "charizard" in the name field AND either the subtypes of "mega" or "vmax."

```
name:charizard (subtypes:mega OR subtypes:vmax)
```

Search for all "mega" subtypes, but NOT water types.

```
subtypes:mega -types:water
```

## Wildcard Matching

Search for any card that starts with "char" in the name field.

```
name:char*
```

Search for any card that starts with "char" in the name and ends with "der."

```
name:char*der
```

## Exact Matching

Search for any card named "charizard." That is, no other word except for "charizard" appears in the name field.

```
!name:charizard
```

## Range Searches

Some fields support searching on a range. This includes fields with numerical data like `hp` and `nationalPokedexNumbers`.

Search for only cards that feature the original 151 pokemon.

```
nationalPokedexNumbers:[1 TO 151]
```

Using square brackets `[` and `]` means to do an inclusive range search, while using curly braces `{` and `}` means exclusive.

Search for cards with a max HP up to 100.

```
hp:[* TO 100]
```

Search for cards with any HP greater than or equal to 150.

```
hp:[150 TO *]
```

## Search on nested fields

To search nested fields, use a period `.` as a separator. For example, to filter by the set id:

```
set.id:sm1
```

Or to filter on cards where they have an attack named "Spelunk":

```
attacks.name:Spelunk
```

Find cards that are banned in Standard.

```
legalities.standard:banned
```

Every field in the response is searchable.

## Ordering Data

You can also order data using the `orderBy` query parameter.

Order all cards from Sun & Moon by their number.

```
?orderBy=number
```

Order all cards from Sun & Moon by their name (ascending) and then their number (descending)

```
?orderBy=name,-number
```