## All Strains

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
