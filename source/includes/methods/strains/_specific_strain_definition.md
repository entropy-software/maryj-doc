## Specific Strain Definition

> Example Request

```shell
curl -X "GET" "http://api.maryj.dev/strain/sour-diesel/flavors" \
  -H "Accept: application/vnd.maryj.v1"
```

> The above command returns JSON structured like this:

```json
{
  "meta": {
    "code": 200
  },
  "data": {
    "flavors": [
      {
        "name": "diesel"
      },
      {
        "name": "pungent"
      },
      {
        "name": "earthy"
      },
      {
        "name": "skunk"
      },
      {
        "name": "sweet"
      }
    ]
  }
}
```

This endpoint retrieves a specific strain definition.

### HTTP Request

`GET http://api.maryj.io/strain/:strain-slug/:definition`

### URL Parameters

Parameter | Description
--------- | -----------
strain-slug | Strain slug `sour-diesel`
definition | Strain specific `conditions`, `effects`, `symptoms`, `flavors`
