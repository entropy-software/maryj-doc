## Pagination

> Pagination Example

```json
{
  "meta": {
    "code": 200,
    "pagination": {
      "per_page": 25,
      "total_pages": 60,
      "total_objects": 1498,
      "links": {
        "first": "http://api.maryj.dev/strain/all?page=1",
        "last": "http://api.maryj.dev/strain/all?page=60",
        "prev": "http://api.maryj.dev/strain/all?page=1",
        "next": "http://api.maryj.dev/strain/all?page=3"
      }
    }
  },
  "data": {
    "strains": [
      ...........
    ]
  }
}
```

Requests that return multiple results will be paginated to 25 items by default. You can use the page parameter to specify which page of data to retrieve. API responses return pre-built pagination links with rels first, prev, next and last and client applications are encouraged to follow these links for pagination.
