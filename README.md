# Toolbox Genomics Partners API

This doc will show you how to use our REST API to authenticate, make requests, and retrieve data. All responses to and from the API will be in JSON.


### Authentication
The API uses JSON Web Tokens for authentication. [View documentation](https://github.com/ToolboxGenomics/tbg-docs/blob/master/tokens.md)


### Steps to Place an Order for Kits and Panels for a Client.

1. Add a client record. [View documentation](https://github.com/ToolboxGenomics/tbg-docs/blob/master/customers.md)
2. Request for a kit to be shipped to the client. [View documentation](https://github.com/ToolboxGenomics/tbg-docs/blob/master/shipments.md)
3. Place an order for panels. [View documentation](https://github.com/ToolboxGenomics/tbg-docs/blob/master/orders.md)


### Receiving Event Updates from Toolbox Genomics

The list of events can be found [here](https://github.com/ToolboxGenomics/tbg-docs/blob/master/events.md). To receive event notifications from the Toolbox Genomics API, there are 2 options:

1. Polling - To check for new events periodically, the Event List API endpoint can be used with a timestamp filter so that only specific events can be retrieved based on a specified date/time. View the documentation [here](https://github.com/ToolboxGenomics/tbg-docs/blob/master/events.md). For example, to retrieve the events for October 1, 2019 12am UTC onwards, the following API request can be performed:

`GET partners.toolboxgenomics.com/api/v1/events/?created_at__gte=2019-10-01+00:00:00`

2. Webhooks - Webhooks are messages sent by Toolbox Genomics via HTTPS POST to a URL you provide to us. Webhook messages are sent when certain Events occur in the life of a resource. They allow your application to receive pushed updates about a resource, rather than poll our API for status changes. [View documentation](https://github.com/ToolboxGenomics/tbg-docs/blob/master/webhooks.md)


### Receiving Report Results
check https://github.com/ToolboxGenomics/tbg-docs/blob/master/reports.md

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
    "field_name":[
      "Field-specific error message, e.g., field_name is not a valid email address."
    ]
  },
  "non-field-errors": [
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
