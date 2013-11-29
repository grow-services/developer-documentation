# The service

## API keys

End-users can apply for an `API key` + `API secret` through the website [www.grow-services.net](http://www.grow-services.net). 

The key and secret serve 2 purposes:

1. To ensure the webservice is only used by licensed, accredited organisations and individuals
2. API rate-limiting to enforce intended use

Each request to any of the APIs contains:

1. The `api key`
2. The token: A sha1 hash of the `api key` + `api secret`

### Example:

Given the following key and secret:

* Key: `warg47aLgX`
* Secret: `BGiYJZx8b0`

The result of sha1("warg47aLgX" + "BGiYJZx8b0"):

* Token: `812982adbbfdcbf4c52bb1b07044510ed867d1b1`

The token guarantees to the API that the requester has a valid license key and secret.

### Developer 

## Languages

The output images of the webservice are available in  the following languages:

* `en_UK`: English
* `nl_NL`: Dutch

... more languages will be added in the near-future.

The documentation and technical interface is available in English only.

## Protocols

The API supports a pre-defined set of request methods, which are available through the following protocols. The MIS is free to choose any of the supported protocols.

### REST API

This is simple API where parameters are submitted as HTTP GET and/or POST variables (both supported).

Endpoint:

    https://www.grow-services.net/api/grow/rest/

The url is post-fixed with the methodname in all lowercase and a final slash.

Parameters are passed as either GET or POST (recommended) variables.

### XML POST API 

This is simple API where parameters are submitted in structured XML fragments.

Endpoint:

    https://www.grow-services.net/api/grow/xml/

The url is post-fixed with the methodname in all lowercase and a final slash.

Parameters are passed in structured XML fragments. Please refer to the "examples" section for XML examples.

### SOAP API (near future)

This API allows you to interact with the service through a SOAP interface. A WSDL will be published once it's ready.

    Endpoint:
        WSDL  https://www.grow-services.net/api/grow/soap/?wsdl
        Server https://www.grow-services.net/api/grow/soap/
