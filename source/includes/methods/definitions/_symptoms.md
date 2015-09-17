## Symptoms

> Example Request

```shell
curl -X "GET" "http://api.maryj.dev/definition/symptoms" \
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
        "name": "cramps"
      },
      {
        "id": 2,
        "name": "depression"
      },
      {
        "id": 3,
        "name": "eyepressure"
      },
      {
        "id": 4,
        "name": "fatigue"
      }
    ]
  }
}
```

This endpoint retrieves all symptoms.

### HTTP Request

`GET http://api.maryj.dev/definition/symptoms`
