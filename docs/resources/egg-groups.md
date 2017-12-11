title: Resources - Pokédex API - Pokémon Developers
description: Checkout all the resources of the Pokédex API and start building your application or website.

# Pokémon Egg Groups Resource

## Get Pokémon Egg Groups
<span class="resource"><span class="get">GET</span> /egg-groups</span>

Returns an array of Pokémon Egg Groups discovered in the Pokémon World.

### Example Request
```bash
curl -i -X GET -H \
  "User-Agent: BastionDiscordBot (https://bastionbot.oorg, v6.3)" \
  https://pokeapi.bastionbot.org/v1/egg-groups
```

### Example Response
```json
[
  "Bug",
  "Ditto",
  "Dragon",
  "Fairy",
  "Field",
  "Flying",
  "Grass",
  "Gender unknown",
  "Human-Like",
  "Mineral",
  "Monster",
  "Amorphous",
  "Undiscovered",
  "Water 1",
  "Water 2",
  "Water 3"
]
```
