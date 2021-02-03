---
title: Headers
position: 6
right_code: |
  ~~~ http
  HTTP/1.1 200 Ok
  Link: <https://api.pokemontcg.io/v1/cards?page=94>; rel="last", <https://api.pokemontcg.io/v1/cards?page=2>; rel="next"
  Page-Size: 100
  Count: 100
  Total-Count: 9320
  Ratelimit-Limit: 5000
  Ratelimit-Remaining: 4999
  ~~~
---

This section pertains to V1 only.
{: .info }

There are quite a few custom response headers available when making a request. Some of these will only show up when the results are paginated.

1. `Link`: Link headers with prev, last, next, first links (when appropriate)
2. `Page-Size`: The page size for the request
3. `Count`: The number of elements returned
4. `Total-Count`: The total number of elements (across all pages)
5. `Ratelimit-Limit`: The ratelimit for a given user
6. `Ratelimit-Remaining`: The number of requests left before the ratelimit is exceeded.