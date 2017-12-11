title: Resources - Pokédex API - Pokémon Developers
description: Checkout all the resources of the Pokédex API and start building your application or website.

# Pokémon Types Resource

## Get Pokémon Types
<span class="resource"><span class="get">GET</span> /types</span>

Returns an array of Pokémon Types discovered in the Pokémon World.

### Example Request
```bash
curl -i -X GET \
  -H "User-Agent: BastionDiscordBot (https://bastionbot.org, v6.3)" \
  https://pokeapi.bastionbot.org/v1/types
```

### Example Response
```json
[
  "Bug",
  "Dark",
  "Dragon",
  "Electric",
  "Fairy",
  "Fighting",
  "Fire",
  "Flying",
  "Ghost",
  "Grass",
  "Ground",
  "Ice",
  "Normal",
  "Poison",
  "Psychic",
  "Rock",
  "Steel",
  "Water"
]
```
