## Conditions

> Example Request

```shell
curl -X "GET" "http://api.maryj.dev/definition/conditions" \
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
        "name": "addadhd"
      },
      {
        "id": 2,
        "name": "alzheimers"
      },
      {
        "id": 3,
        "name": "anorexia"
      },
      {
        "id": 4,
        "name": "anxiety"
      }
    ]
  }
}
```

This endpoint retrieves all conditions.

### HTTP Request

`GET http://api.maryj.dev/definition/conditions`
