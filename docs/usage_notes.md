title: Usage Notes - Pokédex API - Poké Devs
description: Read the usage notes for implementing and using the Pokédex API.

**Pokédex API** is free to be consumed by everyone. Having said that, we ask
every developers using our API to read the usage notes and abide by it.

*   **Locally cache resources when ever you request them through the API.**  
    Caching the resources you already requested for at least *6 hours* prevents
    multiple API calls to request the same resource. Which makes your
    application or website faster, doesn't consume your rate limits and also
    gives less load to our servers.
*   **Do not spam the entire service to scrape all the data.**  
    Only request the resource that's actually necessary for your application or
    website.
*   **Use the correct `User-Agent` header.**  
    Using the correct `User-Agent` header in your API requests (as explained in
    the [Reference](reference.md#user-agent) page) let's us know what library,
    application and/or website is requesting the resource.  
    *If your library, application or website gets popular enough, we may showcase
    it in our website.*
*   **Give us a backlink.**  
    We don't charge you anything, and we never will. **Pokédex API** will be
    free forever. So, the least we want form you is to mention that the data
    that you show in your application or website is fetched from us (our API).

!!! danger
    Users not complying with this will have their IP address permanently banned,
    if their application or website is abusing the API.
