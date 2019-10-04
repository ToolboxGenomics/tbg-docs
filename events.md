

# Events
<br><br>
This document explains on how to get Events.
<br><br>
#### Retrieve all Events
You can get all Events using this API Access Point.
<table>
  <tr>
    <td><strong>URL</strong></td>
    <td> /api/v1/events/ </td>
  </tr>
  <tr>
    <td><strong>HTTP Method</strong></td>
    <td> GET </td>
  </tr>
  <tr>
    <td valign="top"><strong>Response</strong></td>
    <td>
    List of Customer Events with the following details:
      <ul>
        <li><code>id</code> [int]</li>
        <li><code>created_at</code> [String]</li>
        <li><code>category</code> [String]</li>
        <li><code>message</code> [Object]</li>
      </ul>
    </td>
  </tr>
</table>

#### Example


##### Request

```
GET /api/v1/events/
Host: staging.partners.toolboxgenomics.com
Content-Type: application/json

```

##### Success Response

```
HTTP/1.0 200 OK 
Content-Type: application/json

[
    {
        "id": 70,
        "created_at": "2017-11-24 10:00:00",
        "category": "kit-status-update",
        "message": {
            "kit_barcode": "PT101010111",
            "status": "kit-in-process"
        }

    },
    {
        "id": 71,
        "created_at": "2017-11-24 10:01:00",
        "category": "report-status-update",
        "message": {
            "report_id": "1012",
            "status": "report-ready"
        }

    },
]
```