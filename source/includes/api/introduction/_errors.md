## Errors

Maryj uses conventional HTTP response codes to indicate success or failure of an API request. In general, codes in the 2xx range indicate success, codes in the 4xx range indicate an error that resulted from the provided information (e.g. a required parameter was missing, a missing strain, etc.), and codes in the 5xx range indicate an error with Maryj's servers.


Error Code | Meaning
---------- | -------
200 | OK -- Everything worked as expected.
400 | Bad Request -- Often missing a required parameter.
401 | Unauthorized -- No valid API key provided.
402 | Request Failed -- Parameters were valid but request failed.
404 | Not Found -- The requested item doesn't exist.
500, 502, 503, 504 | Server Errors -- Something went wrong on Maryj's end.
