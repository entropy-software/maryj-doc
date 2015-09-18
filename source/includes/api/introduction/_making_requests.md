## Making Requests

> API Endpoint

```json
https://api.maryj.dev/
```

All requests should supply the Accept: application/vnd.maryj.v1 header `v1 - is the API version`. POST requests must have a JSON encoded body.

Requests must be made over HTTPS. Any non-secure requests are met with a redirect (HTTP 302) to the HTTPS equivalent URI.
