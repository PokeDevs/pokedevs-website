title: Resources - Pokédex API - Pokémon Developers
description: Checkout all the resources of the Pokédex API and start building your application or website.

# Pokémon Leagues Resource

## Get Pokémon League Names
<span class="resource"><span class="get">GET</span> /league</span>

Returns an array of Pokémon League names known to us.

### Example Response
```json
[
  "Indigo League",
  "Johto League",
  "Hoenn League",
  "Sinnoh League",
  "Unova League",
  "Kalos League",
  "Orange League"
]
```

## Get Pokémon League
<span class="resource"><span class="get">GET</span> /league/<a href="#pokemon-league-object">{slug}</a></span>

Returns a Pokémon League object containing the details about the league.

### Example Response
```json
{
  "name": "Kalos League",
  "slug": "kalos",
  "region": "Kalos",
  "badgesRequired": 8,
  "badges": [
    "Bug Badge",
    "Cliff Badge",
    "Rumble Badge",
    "Plant Badge",
    "Voltage Badge",
    "Fairy Badge",
    "Psychic Badge",
    "Iceberg Badge"
  ]
}
```

## Pokémon League Models

### Pokémon League Object
<table>
  <caption>Pokémon League Structure</caption>
  <thead>
    <tr class="header">
      <th width="15%">Field</th>
      <th width="30%">Type</th>
      <th width="55%">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>name</td>
      <td>string</td>
      <td>The name of Pokémon league</td>
    </tr>
    <tr>
      <td>slug</td>
      <td>string</td>
      <td>The string used to identify this region.</td>
    </tr>
    <tr>
      <td>region</td>
      <td>string</td>
      <td>The region in the Pokémon World where the league happens</td>
    </tr>
    <tr>
      <td>badgesRequired</td>
      <td>integer</td>
      <td>The minimum number of Pokémon gym badges required to qualify for the Pokémon league</td>
    </tr>
    <tr>
      <td>badges</td>
      <td>array of Pokémon badge names</td>
      <td>The minimum number of Pokémon gym badges required to qualify for the Pokémon league</td>
    </tr>
  </tbody>
</table>
