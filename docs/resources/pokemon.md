title: Resources - Pokédex API - Pokémon Developers
description: Checkout all the resources of the Pokédex API and start building your application or website.

# Pokémon Resource

## Get Pokémon <small>by Pokédex number</small>
<span class="resource"><span class="get">GET</span> /pokemon/<a href="#pokemon-object">{number}</a></span>

Returns an array of <a href="#pokemon-object">Pokémon</a> objects containing all
the forms of the Pokémon specified the Pokédex number.

### Example Request
```bash
curl -i -X GET \
  -H "User-Agent: BastionDiscordBot (https://bastionbot.org, v6.3)" \
  https://pokeapi.bastionbot.org/v1/pokemon/658
```

### Example Response
```json
[
  {
    "number": "658",
    "name": "Greninja",
    "species": "Ninja",
    "types": [
      "Water",
      "Dark"
    ],
    "abilities": {
      "normal": [
        "Torrent"
      ],
      "hidden": [
        "Protean"
      ]
    },
    "eggGroups": [
      "Water 1"
    ],
    "gender": [
      87.5,
      12.5
    ],
    "height": "4'11\"",
    "weight": "88.2 lbs.",
    "family": {
      "id": 331,
      "evolutionStage": 3,
      "evolution-line": [
        "Froakie",
        "Frogadier",
        "Greninja"
      ]
    },
    "starter": false,
    "legendary": false,
    "mythical": false,
    "ultraBeast": false,
    "mega": false,
    "gen": 6,
    "sprite": "https://pokeres.bastionbot.org/images/pokemon/658.png"
  },
  {
    "number": "658",
    "name": "Ash-Greninja",
    "species": "Ninja",
    "types": [
      "Water",
      "Dark"
    ],
    "abilities": {
      "normal": [
        "Torrent"
      ],
      "hidden": [
        "Battle Bond"
      ]
    },
    "eggGroups": [
      "Water 1"
    ],
    "gender": [
      87.5,
      12.5
    ],
    "height": "4'11\"",
    "weight": "88.2 lbs.",
    "family": {
      "id": 331,
      "evolutionStage": 3,
      "evolution-line": [
        "Froakie",
        "Frogadier",
        "Greninja"
      ]
    },
    "starter": false,
    "legendary": false,
    "mythical": false,
    "ultraBeast": false,
    "mega": false,
    "gen": 6,
    "sprite": "https://pokeres.bastionbot.org/images/pokemon/658-ash.png"
  }
]
```

## Get Pokémon Counts
<span class="resource"><span class="get">GET</span> /pokemon/counts</span>

Returns a <a href="#pokemon-counts-object">Pokémon Counts</a> object containing
the number of Pokémon in each generation and the total number of Pokémon in the
Pokémon World.

### Example Request
```bash
curl -i -X GET -H \
  "User-Agent: BastionDiscordBot (https://bastionbot.oorg, v6.3)" \
  https://pokeapi.bastionbot.org/v1/pokemon/counts
```

### Example Response
```json
{
  "gen1": 151,
  "gen2": 100,
  "gen3": 135,
  "gen4": 107,
  "gen5": 156,
  "gen6": 72,
  "gen7": 86,
  "total": 807
}
```

## Pokémon Models

### Pokémon Object
<table>
  <caption>Pokémon Structure</caption>
  <thead>
    <tr class="header">
      <th width="15%">Field</th>
      <th width="30%">Type</th>
      <th width="55%">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>number</td>
      <td>integer</td>
      <td>The Pokédex number of the Pokémon</td>
    </tr>
    <tr>
      <td>name</td>
      <td>string</td>
      <td>The name of the Pokémon</td>
    </tr>
    <tr>
      <td>species</td>
      <td>string</td>
      <td>The species the Pokémon belongs to</td>
    </tr>
    <tr>
      <td>types</td>
      <td>array of <a href="types.md">Pokémon types</a></td>
      <td>The type of the Pokémon</td>
    </tr>
    <tr>
      <td>abilities</td>
      <td>array of normal and hidden Pokémon abilities</td>
      <td>The abilities of the Pokémon</td>
    </tr>
    <tr>
      <td>eggGroups</td>
      <td>array of <a href="egg-groups.md">Pokémon egg groups</a></td>
      <td>The egg groups the Pokémon belong to</td>
    </tr>
    <tr>
      <td>height</td>
      <td>string</td>
      <td>The height of the Pokémon in feet</td>
    </tr>
    <tr>
      <td>weight</td>
      <td>string</td>
      <td>The weight of the Pokémon in pounds</td>
    </tr>
    <tr>
      <td>family</td>
      <td><a href="#pokemon-family-object">Pokémon family</a> object</td>
      <td>The family id, evolution stage and evolution line of the Pokémon</td>
    </tr>
    <tr>
      <td>starter</td>
      <td>bool</td>
      <td>Is it a starter Pokémon</td>
    </tr>
    <tr>
      <td>legendary</td>
      <td>bool</td>
      <td>Is it a legendary Pokémon</td>
    </tr>
    <tr>
      <td>mythical</td>
      <td>bool</td>
      <td>Is it a mythical Pokémon</td>
    </tr>
    <tr>
      <td>ultraBeast</td>
      <td>bool</td>
      <td>Is it a ultra beast</td>
    </tr>
    <tr>
      <td>mega</td>
      <td>bool</td>
      <td>Is it mega evolved form of the Pokémon</td>
    </tr>
    <tr>
      <td>gen</td>
      <td>integer</td>
      <td>The generation the Pokémon was first discovered</td>
    </tr>
    <tr>
      <td>sprite</td>
      <td>string</td>
      <td>The URL of an image of the Pokémon</td>
    </tr>
  </tbody>
</table>

### Pokémon Family Object
<table>
  <caption>Pokémon Family Structure</caption>
  <thead>
    <tr class="header">
      <th width="15%">Field</th>
      <th width="15%">Type</th>
      <th width="70%">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>id</td>
      <td>integer</td>
      <td>The id of Pokémon family.</td>
    </tr>
    <tr>
      <td>evolutionStage</td>
      <td>integer</td>
      <td>The evolved stage of the Pokémon in it's evolution line.</td>
    </tr>
    <tr>
      <td>evolutionLine</td>
      <td>array of Pokémon names</td>
      <td>The list of Pokémon in it's evolution line.</td>
    </tr>
  </tbody>
</table>

### Pokémon Counts Object
<table>
  <caption>Pokémon Counts Structure</caption>
  <thead>
    <tr class="header">
      <th width="15%">Field</th>
      <th width="15%">Type</th>
      <th width="70%">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>gen1</td>
      <td>integer</td>
      <td>The number of Pokémon discovered in this generation.</td>
    </tr>
    <tr>
      <td>gen2</td>
      <td>integer</td>
      <td>The number of Pokémon discovered in this generation.</td>
    </tr>
    <tr>
      <td>⋮</td>
      <td>integer</td>
      <td>The number of Pokémon discovered in this generation.</td>
    </tr>
    <tr>
      <td>total</td>
      <td>integer</td>
      <td>The total number of Pokémon discovered in the Pokémon World.</td>
    </tr>
  </tbody>
</table>
