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
    "search": [
      {
        "id": 1,
        "name": "Aloha",
        "slug": "aloha",
        "category": "Sativa"
      },
      {
        "id": 298,
        "name": "Buffalo Bill",
        "slug": "buffalo-bill",
        "category": "Sativa"
      },
      {
        "id": 650,
        "name": "Green Lantern",
        "slug": "green-lantern",
        "category": "Sativa"
      },
      {
        "id": 678,
        "name": "Hawaiian Haze",
        "slug": "hawaiian-haze",
        "category": "Sativa"
      }
    ]
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
