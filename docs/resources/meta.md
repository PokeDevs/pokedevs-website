title: Resources - Pokédex API - Poké Devs
description: Checkout all the resources of the Pokédex API and start building your application or website.

# Pokédex Meta Resource

## Get Pokédex API Information
<span class="resource"><span class="get">GET</span> /info</span>

Returns basic information about the Pokédex API containing the base URL,
resources URL, available versions, etc.

!!! note
    This endpoint doesn't work with versioning. You should access this endpoint
    directly from the base URL.

### Example Request
```bash
curl -i -X GET \
  -H "User-Agent: BastionDiscordBot (https://bastionbot.org, v6.3)" \
  https://pokeapi.bastionbot.org/info
```

### Example Response
```json
{
  "title": "Pokédex API",
  "baseURL": "https://pokeapi.bastionbot.org",
  "resourcesURL": "https://pokeres.bastionbot.org",
  "versions": [
    "/v1"
  ],
  "author": "Sankarsan Kampa"
}
```

<table>
  <caption>Pokédex API Info Structure</caption>
  <thead>
    <tr class="header">
      <th width="15%">Field</th>
      <th width="30%">Type</th>
      <th width="55%">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>title</td>
      <td>string</td>
      <td>The name the API</td>
    </tr>
    <tr>
      <td>baseURL</td>
      <td>string</td>
      <td>The base URL of the Pokédex API for requesting resources</td>
    </tr>
    <tr>
      <td>resourcesURL</td>
      <td>string</td>
      <td>The base URL of the image (and other) resources required by the Pokédex API</td>
    </tr>
    <tr>
      <td>versions</td>
      <td>array of strings</td>
      <td>Available versions of the Pokédex API</td>
    </tr>
    <tr>
      <td>author</td>
      <td>string</td>
      <td>The author/developer of the Pokédex API</td>
    </tr>
  </tbody>
</table>

## Get Pokédex API Statistics
<span class="resource"><span class="get">GET</span> /stats</span>

Returns basic statistics of the Pokédex API containing the total number of
API calls, number of API calls since last restart and uptime of the API server.

!!! note
    This endpoint doesn't work with versioning. You should access this endpoint
    directly from the base URL.

### Example Request
```bash
curl -i -X GET \
  -H "User-Agent: BastionDiscordBot (https://bastionbot.org, v6.3)" \
  https://pokeapi.bastionbot.org/stats
```

### Example Response
```json
{
  "total_hits": "1337",
  "session_hits": "201",
  "uptime": 658
}
```

<table>
  <caption>Pokédex API Stats Structure</caption>
  <thead>
    <tr class="header">
      <th width="15%">Field</th>
      <th width="30%">Type</th>
      <th width="55%">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>total_hits</td>
      <td>string</td>
      <td>Total number of API calls made to Pokédex API. *Note that this is not accurate because currently the API is hosted in Heroku, which restarts frequently. I'll host the API in a dedicated server if I get enough resources to do so. So, if you like this project, please consider donating via [PayPal](https://paypal.me/snkrsnkampa).*</td>
    </tr>
    <tr>
      <td>session_hits</td>
      <td>string</td>
      <td>Number of API calls made to Pokédex API since last restart</td>
    </tr>
    <tr>
      <td>uptime</td>
      <td>number</td>
      <td>Number of seconds elapsed since Pokédex API server was booted</td>
    </tr>
  </tbody>
</table>
