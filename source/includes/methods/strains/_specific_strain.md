## Specific Strain

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

`GET http://api.maryj.io/strain/:strain-slug`

### URL Parameters

Parameter | Description
--------- | -----------
strain-slug | Strain slug `sour-diesel`
