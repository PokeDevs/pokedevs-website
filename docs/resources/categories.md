title: Resources - Pokédex API - Poké Devs
description: Checkout all the resources of the Pokédex API and start building your application or website.

# Pokémon Categories Resource

## Get Pokémon Categories
<span class="resource"><span class="get">GET</span> /categories</span>

Returns an array of Pokémon Categories discovered in the Pokémon World.

### Example Request
```bash
curl -i -X GET \
  -H "User-Agent: BastionDiscordBot (https://bastionbot.org, v6.3)" \
  https://pokeapi.bastionbot.org/v1/categories
```

### Example Response
```json
[
  "starter",
  "legendary",
  "mythical",
  "ultraBeast",
  "mega"
]
```
