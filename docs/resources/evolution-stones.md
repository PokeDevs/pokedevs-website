title: Resources - Pokédex API - Pokémon Developers
description: Checkout all the resources of the Pokédex API and start building your application or website.

# Evolution Stones Resource

## Get Evolution Stone Names
<span class="resource"><span class="get">GET</span> /evolution-stone</span>

Returns an array of Pokémon Evolution Stone names discovered in the Pokémon
world.

### Example Response
```json
[
  "Fire Stone",
  "Water Stone",
  "Thunder Stone",
  "Leaf Stone",
  "Moon Stone",
  "Sun Stone",
  "Shiny Stone",
  "Dusk Stone",
  "Dawn Stone",
  "Ice Stone"
]
```

## Get Evolution Stone
<span class="resource"><span class="get">GET</span> /evolution-stone/<a href="#evolution-stone-object">{slug}</a></span>

Returns a Evolution Stone object containing the details about the evolution
stone.

### Example Response
```json
{
  "name": "Dusk Stone",
  "aka": "Darkness Stone",
  "slug": "dusk",
  "effects": [
    "Causes Murkrow to evolve into Honchkrow.",
    "Causes Misdreavus to evolve into Mismagius.",
    "Causes Lampent to evolve into Chandelure.",
    "Causes Doublade to evolve into Aegislash."
  ],
  "sprite": "https://pokeres.bastionbot.org/images/evolution-stones/dusk-stone.png"
}
```

## Evolution Stone Models

### Evolution Stone Object
<table>
  <caption>Evolution Stone Structure</caption>
  <thead>
    <tr class="header">
      <th width="15%">Field</th>
      <th width="15%">Type</th>
      <th width="70%">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>name</td>
      <td>string</td>
      <td>The name of evolution stone</td>
    </tr>
    <tr>
      <td>aka</td>
      <td>string</td>
      <td>The alternate name of the evolution stone</td>
    </tr>
    <tr>
      <td>slug</td>
      <td>string</td>
      <td>The string used to identify this evolution stone.</td>
    </tr>
    <tr>
      <td>effects</td>
      <td>array of strings</td>
      <td>A list of the effects of using the evolution stone on a Pokémon</td>
    </tr>
    <tr>
      <td>sprite</td>
      <td>integer</td>
      <td>The URL of an image of the evolution stone</td>
    </tr>
  </tbody>
</table>
