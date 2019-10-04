# Toolbox Genomics Partner API

This doc will show you how to use our REST API to authenticate, make requests, and retrieve data. All responses to and from the API will be in JSON.


### Response Codes

We use conventional HTTP response codes to indicate success or failure of an API request. In general, codes in the 2xx range indicate success, codes in the 4xx range indicate an error that resulted from the provided information (e.g. a required parameter was missing, invalid syntax, etc.), and codes in the 5xx range indicate a server error.

| Code | Description
|:---|:---
| `200` | Success. Request completed.
| `201` | Success. New resource created.
| `204` | Success. No content to return. Only the status code returns.
| `400` | Bad Request - The request could not be parsed.
| `401` | Unauthorized - user is not logged in, could not be authenticated.
| `403` | Forbidden - Cannot access resource.
| `404` | Not Found - resource doesn't exist.
| `409` | Conflict - with state of the resource on server. Can occur with (too rapid) PUT requests.
| `5xx` | Server error.


### Error Messages

There are two types of errors returned by the API server in the bodies of 4xx and 5xx responses: Field-specific errors and  General error messages
```
{
  "errors": {
    "fieldName":[
      "Field-specific error message, e.g., fieldName is not a valid email address."
    ]
  },
  "messages": [
    "General error message."
  ]
}
```

### Dates

Our API uses the ISO8601 date format for complete date plus hours, minutes, seconds and timezone offset.         
```
         yyyy-MM-dd'T'HH:mm:ssZ`
For UTC: 2015-11-03T13:21:58+00:00
```
