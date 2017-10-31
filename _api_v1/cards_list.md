---
title: /cards
position: 1.0
type: get
description: Get All Cards
right_code: |
  ~~~ json
  {  
    "cards":[  
    {
      "id": "base5-20",
      "name": "Dark Blastoise",
      "nationalPokedexNumber": 9,
      "imageUrl": "https://images.pokemontcg.io/base5/20.png",
      "imageUrlHiRes": "https://images.pokemontcg.io/base5/20_hires.png",
      "types": [
          "Water"
      ],
      "supertype": "Pokémon",
      "subtype": "Stage 2",
      "evolvesFrom": "Wartortle",
      "hp": "70",
      "retreatCost": [
        "Colorless",
        "Colorless"
      ],
      "number": "20",
      "artist": "Mitsuhiro Arita",
      "rarity": "Rare",
      "series": "Base",
      "set": "Team Rocket",
      "setCode": "base5",
      "attacks": [
        {
          "cost": [
            "Water",
            "Water"
          ],
          "name": "Hydrocannon",
          "text": "Does 30 damage plus 20 more damage for each Energy attached to Dark Blastoise but not used to pay for this attack. You can't add more than 40 damage in this way.",
          "damage": "30+",
          "convertedEnergyCost": 2
        },
        {
          "cost": [
            "Colorless",
            "Colorless",
            "Water"
          ],
          "name": "Rocket Tackle",
          "text": "Dark Blastoise does 10 damage to itself. Flip a coin. If heads, prevent all damage done to Dark Blastoise during your opponent's next turn. (Any other effects of attacks still happen.)",
          "damage": "40",
          "convertedEnergyCost": 3
        }
      ],
      "weaknesses": [
        {
          "type": "Lightning",
          "value": "×2"
        }
      ]
    },
    { ... },
    { ... }
    ]
    }
  ~~~
  {: title="Response" }
---
This call will return a maximum of 1000 cards. The default is 100.
{: .info }

Paginate the response using the `page` parameter.

Each field below can be used as a query parameter. By default, fields that have a singular value such as rarity, set, and name will always use a logical “or” operator when querying with a list of values. Fields that can have multiple values such as types can use a logical "and" or a logical "or" operator.

The accepted delimiters when querying fields are the pipe character or a comma character. The pipe represents a logical “or”, and a comma represents a logical “and”. The comma can only be used with fields that accept multiple values (like types).

Example:`name=blastoise|charizard`

More examples: `types=fire,metal` versus `colors=fire|metal`

name
: The card name. Put the name in double quotes for an exact match, otherwise partial matching will be applied.

id
: A unique id for this card. It is made up by taking the set code and concatenating the card number to it. (ex. xy1-1)

nationalPokedexNumber
: The national pokedex number for a card that features a Pokémon supertype.

types
: The types of the card. These typically appear in the top right of card, and are denoted by energy symbol (ex. Fire, Fighting, Psychic, etc.)

subtype
: The subtype of the card. Examples include MEGA, Stage 1, BREAK, Supporter, etc.

supertype
: The supertype of the card. Either Pokémon, Trainer, or Energy.

hp
: The hit points of the card. This typically appears in the top right corner of the card.

number
: The number of the card for the set it was released in. Found on the bottom right side of the card.

artist
: The artist of the card.

rarity
: The rarity of the card (ex. Rare, Rare Holo, Common, etc.)

series
: The series the card appears in (ex. Base, XY, EX, etc.)

set
: The set the card appears in (ex. BREAKthrough, Phantom Forces, Jungle, etc.)

setCode
: The unique code of the set (ex. base1, xy5, ex3)

retreatCost
: The amount of energy it takes to retreat. Found on the bottom of the card.

text
: Any additional text on a card. This includes special rules (like MEGA rules or EX), and text that appears on Trainer cards.

attackDamage
: The attack damage of any given attack for a card

attackCost
: The energy cost of a given attack for a card

attackName
: The name of an attack

attackText
: The text description of an attack

weaknesses
: The weaknesses of the card (ex. Fire, Water, Grass)

resistances
: The resistances of the card (ex. Fire, Water, Grass)

ancientTrait
: The Ancient Trait of the card (if exists)

abilityName
: The name of the ability

abilityText
: The text of the ability

abilityType
: The type of the ability (such as Poké-Power, Poké-Body, Pokémon Power or Ability)

contains
: Filter on cards that contain a specific field in the JSON response (ex. ?contains=ancientTrait)

#### Other Fields in Response

The fields below are also part of the response (if not null), but cannot currently be used as query parameters

imageUrl
: The image url for a card.

imageUrlHiRes
: The high resolution image url for a card.

ability
: A passive effect during battle. Also known as Poké-Powers and Poké-Bodies from older set. With the release of Black & White, all Pokémon Powers are known as Abilities.

attacks
: The attacks for a given card.

~~~ ruby
require 'pokemon_tcg_sdk'

# Get all Cards
cards = Pokemon::Card.all

# Filter Cards
# You can chain 'where' clauses together. The key of the hash
# should be the URL parameter you are trying to filter on
cards = Pokemon::Card.where(supertype: 'pokemon')
                     .where(types: 'dragon|fire|flying')
                     .where(hp: 'gt100')
                     .all

# Get cards on a specific page / pageSize
cards = Pokemon::Card.where(page: 50).where(pageSize: 500).all
~~~
{: title="ruby" }

~~~ python
from pokemontcgsdk import Card

# Get all Cards
cards = Card.all()

# Filter Cards
# You can chain 'where' clauses together. The key of the hash
# should be the URL parameter you are trying to filter on
cards = Card.where(supertype='pokemon') \
            .where(types='dragon|fire|flying') \
            .where(hp='gt100') \
            .all()

# Get cards on a specific page / pageSize
cards = Card.where(page=50).where(pageSize=500).all()
~~~
{: title="python" }

~~~ elixir
# Get all Cards
cards = Pokemon.Card.all

# Filter Cards
cards = Pokemon.Card.where(supertype: "pokemon", types: "dragon|fire|flying", hp: "gt100")

# Get cards on a specific page / pageSize
cards = Pokemon.Card.where(page: 5, pageSize: 100)
~~~
{: title="elixir" }

~~~ javascript
const pokemon = require('pokemontcgsdk')

// Get all cards
pokemon.card.all()
.on('data', function (card) {
  console.log(card.name)
});

// Filter Cards
pokemon.card.all({ supertype: 'pokemon', types: 'dragon|fire|flying', hp: 'gt100' })
.on('data', function (card) {
    console.log(card.name)
});

// Get cards on a specific page / pageSize
pokemon.card.where({ page: 50, pageSize: 500})
.then(cards => {
    console.log(cards[0].name)
})
~~~
{: title="javascript"}

~~~ php
<?php

# Get all Cards
$cards = Pokemon::Card()->all();

# Filter Cards
$cards = Pokemon::Card()->where([
  'supertype' => 'pokemon', 
  'types' => 'dragon|fire|flying',
  'hp' => 'gt100'
])->all();

# Get cards on a specific page / pageSize
$cards = Pokemon::Card()->where([
    'page'     => 50,
    'pageSize' => 100
])->all();
~~~
{: title="php"}

~~~ bash
# Get all cards
curl "https://api.pokemontcg.io/v1/cards"

# Filter cards
curl "https://api.pokemontcg.io/v1/cards?supertype=pokemon&types=dragon|fire|flying&hp=gt100"

# Get specific page of data
curl "https://api.pokemontcg.io/v1/cards?page=50&pageSize=500"
~~~
{: title="bash"}