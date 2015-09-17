## Flavors

> Example Request

```shell
curl -X "GET" "http://api.maryj.dev/definition/flavors" \
  -H "Accept: application/vnd.maryj.v1"
```

> The above command returns JSON structured like this:

```json
{
  "meta": {
    "code": 200
  },
  "data": {
    "symptoms": [
      {
        "id": 1,
        "name": "ammonia"
      },
      {
        "id": 2,
        "name": "apple"
      },
      {
        "id": 3,
        "name": "apricot"
      },
      {
        "id": 4,
        "name": "berry"
      }
    ]
  }
}
```

This endpoint retrieves all flavors.

### HTTP Request

`GET http://api.maryj.dev/definition/flavors`
