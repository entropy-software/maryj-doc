## Effects

> Example Request

```shell
curl -X "GET" "http://api.maryj.dev/definition/effects" \
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
        "name": "anxious"
      },
      {
        "id": 2,
        "name": "aroused"
      },
      {
        "id": 3,
        "name": "creative"
      },
      {
        "id": 4,
        "name": "dizzy"
      }
    ]
  }
}
```

This endpoint retrieves all effects.

### HTTP Request

`GET http://api.maryj.dev/definition/effects`
