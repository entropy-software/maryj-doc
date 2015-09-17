---
title: Maryj API Reference

language_tabs:
  - shell
  - ruby
  - php: PHP

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>

search: true
---

# Introduction

The Maryj API is organized around REST. Our API is designed to have predictable, resource-oriented URLs and to use HTTP response codes to indicate API errors. We use built-in HTTP features, like HTTP authentication and HTTP verbs, which can be understood by off-the-shelf HTTP clients.

We support cross-origin resource sharing to allow you to interact securely with our API from a client-side web application (though you should remember that you should never expose your secret API key in any public website's client-side code). JSON will be returned in all responses from the API, including errors.

You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

## Making Requests

All requests should supply the Accept: application/vnd.maryj.v1 header `v1 - is the API version`. POST requests must have a JSON encoded body.

Requests must be made over HTTPS. Any non-secure requests are met with a redirect (HTTP 302) to the HTTPS equivalent URI.

## Errors

Maryj uses conventional HTTP response codes to indicate success or failure of an API request. In general, codes in the 2xx range indicate success, codes in the 4xx range indicate an error that resulted from the provided information (e.g. a required parameter was missing, a missing strain, etc.), and codes in the 5xx range indicate an error with Maryj's servers.


Error Code | Meaning
---------- | -------
200 | OK -- Everything worked as expected.
400 | Bad Request -- Often missing a required parameter.
401 | Unauthorized -- No valid API key provided.
402 | Request Failed -- Parameters were valid but request failed.
404 | Not Found -- The requested item doesn't exist.
500, 502, 503, 504 | Server Errors -- Something went wrong on Maryj's end.

# Authentication

To authenticate against Maryj API, you need an API access token.

You can retrieve a token from one of your applications.


# Strains

## Get All Strains

> Example Request

```ruby
require 'net/http'

def send_request
  # /strain/all (GET )

  begin
    uri = URI('http://api.maryj.dev/strain/all')

    # Create client
    http = Net::HTTP.new(uri.host, uri.port)


    # Create Request
    req =  Net::HTTP::Get.new(uri)
    # Add headers
    req.add_field "Accept", "application/vnd.maryj.v1"

    # Fetch Request
    res = http.request(req)
    puts "Response HTTP Status Code: #{res.code}"
    puts "Response HTTP Response Body: #{res.body}"
  rescue StandardError => e
    puts "HTTP Request failed (#{e.message})"
  end
end
```

```php
<?php

// Get cURL resource
$ch = curl_init();

// Set url
curl_setopt($ch, CURLOPT_URL, 'http://api.maryj.dev/strain/all');

// Set method
curl_setopt($ch, CURLOPT_CUSTOMREQUEST, 'GET');

// Set options
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);

// Set headers
curl_setopt($ch, CURLOPT_HTTPHEADER, [
  "Accept: application/vnd.maryj.v1",
 ]
);


// Send the request & save response to $resp
$resp = curl_exec($ch);

if(!$resp) {
  die('Error: "' . curl_error($ch) . '" - Code: ' . curl_errno($ch));
} else {
  echo "Response HTTP Status Code : " . curl_getinfo($ch, CURLINFO_HTTP_CODE);
  echo "\nResponse HTTP Body : " . $resp;
}

// Close request to clear up some resources
curl_close($ch);
```

```shell
curl -X "GET" "http://api.maryj.dev/strain/all" \
  -H "Accept: application/vnd.maryj.v1"
```

> The above command returns JSON structured like this:

```json
{
  "meta": {
    "code": 200
  },
  "data": {
    "strains": [
      {
        "id": 1,
        "name": "Aloha",
        "slug": "aloha",
        "category": "Sativa"
      },
      {
        "id": 2,
        "name": "Alohaberry",
        "slug": "alohaberry",
        "category": "Hybrid"
      }
    ]
  }
}
```

This endpoint retrieves all strains.

### HTTP Request

`GET http://api.maryj.io/strain/all`

## Get a Specific Strain

> Example Request

```shell
curl -X "GET" "http://api.maryj.dev/strain/sour-diesel" \
  -H "Accept: application/vnd.maryj.v1"
```

> The above command returns JSON structured like this:

```json
{
  "meta": {
    "code": 200
  },
  "data": {
    "strain": {
      "id": 1256,
      "name": "Sour Diesel",
      "slug": "sour-diesel",
      "category": "Sativa",
      "conditions": [
        {
          "name": "anxiety"
        }
      ],
      "effects": [
        {
          "name": "happy"
        }
      ],
      "flavor": [
        {
          "name": "diesel"
        }
      ],
      "symptoms": [
        {
          "name": "stress"
        }
      ]
    }
  }
}
```

This endpoint retrieves a specific strain.

<aside class="warning">
If the strain cant by found a status code of 404 will be returned.
</aside>

### HTTP Request

`GET http://api.maryj.io/strain/<SLUG>`

### URL Parameters

Parameter | Description
--------- | -----------
slug | Strain slug `sour-diesel`


## Search Strains

> Example Request

```shell
curl -X "POST" "http://api.maryj.dev/strain/search" \
	-H "Accept: application/vnd.maryj.v1" \
	-d $'{
          "category": [
            "sativa"
          ],
          "params": {
            "flavors": [
              "tropical"
            ],
            "conditions": [
              "anxiety"
            ],
            "effects": [
              "focused"
            ],
            "symptoms": [
              "stress"
            ]
          }
        }
```

> The above command returns JSON structured like this:

```json
{
  "meta": {
    "code": 200
  },
  "data": {
    "strain": {
      "id": 1256,
      "name": "Sour Diesel",
      "slug": "sour-diesel",
      "category": "Sativa",
      "conditions": [
        {
          "name": "anxiety"
        }
      ],
      "effects": [
        {
          "name": "happy"
        }
      ],
      "flavor": [
        {
          "name": "diesel"
        }
      ],
      "symptoms": [
        {
          "name": "stress"
        }
      ]
    }
  }
}
```

This endpoint searches all strains with the provided parameters.

### HTTP Request

`POST http://api.maryj.io/strain/search`

### Query Parameters

Parameter | Description
--------- | -----------
category | What category to search in `sativa`, `indica`, `hybrid`
params | Additional search parameters `conditions`, `effects`, `flavor`, `symptoms`
