title: Reference - Pokédex API - Pokémon Developers
description: Welcome to the Pokédex API documentation page. Read and get started with developing amazing Pokémon apps.

## API Reference
Pokédex API is based on a single layer, a HTTPS/REST consumption-only API that
only allows the `GET` method to consume all the Pokémon information you'll ever
need.

## Base URL
The base URL for all API requests is:
```URL
https://api.pokedevs.bastionbot.org
```

## API Versioning
Pokédex API exposes different versions of the API. You can specify version by
including it in the request path:
```URL
https://api.pokedevs.bastionbot.org/v{version_number}
```

Omitting the version number from the route will route requests to the current
default version. We recommend specifying a version number in the request path
so that your app doesn't run into incompatibility when the default version is
changed.

<table>
  <caption>API Versions</caption>
  <thead>
    <tr class="header">
      <th>Version</th>
      <th>Status</th>
      <th>Default</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>Available</td>
      <td>✓</td>
    </tr>
  </tbody>
</table>

## Authentication
No authentication is required to access this API. All the resources are and
available to everyone. However, we will implement authentication methods in the
future that will give authenticated users higher [rate limits](#rate-limiting)
or no [rate limits](#rate-limiting) at all (more on [rate limits](#rate-limiting)
later).

## User Agent
Applications and websites using the API must provide a valid [User Agent](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43)
which specifies information about the app and website, in the following format:

```
User-Agent: AppName ($url, $version)
```

Applications and websites may append more information and metadata to the end of
this string as they wish.

### Example User Agent Header
```
User-Agent: BastionDiscordBot (https://bastionbot.org, 6.3.0)
```

## Rate Limiting
This API implements a process for limiting and preventing excessive requests in
accordance with [RFC 6585](https://tools.ietf.org/html/rfc6585#section-4).

This API rate limits requests in order to prevent abuse and overload of our
services. Rate limits are applied on a global basis, spanning across the entire
API.

Because we may change rate limits at any time and rate limits can be
different per application, rate limits should not be hard coded into your
application or website. In order to properly support our dynamic rate
limits, your application or website should parse for our rate limits in
response headers and locally prevent exceeding of the limits as they change.

!!! info
    Current rate limit is 500 API calls in 12 hours. And we will increase the
    rate limits every time we upgrade our server for better performance.

We recommend that your application or website should locally cache the
data that you receive to save the number of API calls consumed for the same
resource.

### Header Format
For every API request made, we return optional HTTP response headers containing
the rate limit encountered during your request.

```
X-RateLimit-Limit: 500
X-RateLimit-Remaining: 201
X-RateLimit-Reset: 905212800000
```

*   X-RateLimit-Limit - The number of requests that can be made
*   X-RateLimit-Remaining - The number of remaining requests that can be made
*   X-RateLimit-Reset - Epoch time (seconds since 00:00:00 UTC on January 1,
    1970) at which the rate limit resets. It is returned only if you've been
    rate limited.

### Exceeding A Rate Limit
In the case that a rate limit is exceeded, the API will return a HTTP 429
response code with a JSON body.

<table>
  <caption>Rate Limit Response Structure</caption>
  <thead>
    <tr class="header">
      <th width="15%">Field</th>
      <th width="15%">Type</th>
      <th width="70%">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>error</td>
      <td>integer</td>
      <td>The HTTP response code.</td>
    </tr>
    <tr>
      <td>message</td>
      <td>string</td>
      <td>A message saying you are being rate limited.</td>
    </tr>
    <tr>
      <td>retry_after</td>
      <td>integer</td>
      <td>The number of milliseconds to wait before submitting another request.</td>
    </tr>
  </tbody>
</table>

Note that the normal rate-limiting headers will be sent in this response.

!!! warning
    API users that regularly hit and ignore rate limits will be banned (by their
    IP address) from using the API again.

### Example Rate Limit Response
The rate-limiting response will look something like the following:

```
< HTTP/1.1 429 TOO MANY REQUESTS
< Content-Type: application/json
< Retry-After: 1000
< X-RateLimit-Limit: 500
< X-RateLimit-Remaining: 0
< X-RateLimit-Reset: 905212800000
{
  "error": 429,
  "message": "You are being rate limited.",
  "retry_after": 14400000
}
```
