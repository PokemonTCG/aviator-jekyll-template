---
title: Getting Started
position: 1
---

Version 2 is now available!
{: .info }

Version 1 of this API is officially deprecated and will be unavailable as of August 1, 2021. It is highly recommended you upgrade to Version 2 as soon as possible. More details can be found within these docs.
{: .error }


Welcome to the Pokémon TCG API! You can use the API to access Pokémon TCG API endpoints, which can get information on cards and sets. All API access is performed over HTTPS and accessed from the `https://api.pokemontcg.io` domain.

### Get an API Key

For V2 of the API, it is highly recommended to make an account over at [https://dev.pokemontcg.io](https://dev.pokemontcg.io) and get an API key. This API key has higher rate limits, and if necessary, those limits can be adjusted for you if they don't meet your needs.

To use your API key, put it in the `X-Api-Key` header of your request.

To use the API endpoints, the format is as follows:

`https://api.pokemontcg.io/<version>/<resource>`

For example:

`https://api.pokemontcg.io/v2/cards`

There are multiple SDKs available to make it even easier to consume the API.
To chat with other developers and discuss the API and SDKs, check out the [Discord Server](https://discord.gg/dpsTCvg)!

[![pokemontcg-developers on discord](https://img.shields.io/badge/discord-pokemontcg--developers-738bd7.svg)](https://discord.gg/dpsTCvg)
