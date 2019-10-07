# Events
Events are created when certain events occur in the life of a resource. This document explains how to retrieve events.

<br>

### Event Types

| Event | Type | Description
|:---|:---|:---
| Kit out for delivery | kit.created | Sent immediately when a kit is added to a shipment.
| Kit received by lab | kit.updated | Sent when the lab receives the kit.
| Kit in process | kit.updated | Sent when the lab starts the processing of the sample.
| Kit failed | kit.updated | Sent when a replacement kit is needed.
| Report ready | report.updated | Sent when a report is ready.
| Report blocked - no consent | report.updated | Sent when a report is blocked because the Customer's consent_date was not provided.
| Report blocked - no kit registration | report.updated | Sent when a report is blocked because the Kit Registration's verification_date was not provided.


### Example Data for each Event Type

###### Kit out for delivery
```
{
  "id": 3514,
  "type": "kit.updated",
  "data": {
    "kit": {
      "barcode": "UL42345",
      "status": "KIT_SHIPPED",
      "shipment_id": 2344
    }
  }
}
```

###### Kit received by lab
```
{
  "id": 3514,
  "type": "kit.updated",
  "data": {
    "kit": {
      "barcode": "UL42345",
      "status": "KIT_RECEIVED",
    }
  }
}
```

###### Kit in process
```
{
  "id": 3514,
  "type": "kit.updated",
  "data": {
    "kit": {
      "barcode": "UL42345",
      "status": "KIT_PROCESSING",
    }
  }
}
```

###### Kit failed
```
{
  "id": 3514,
  "type": "kit.updated",
  "data": {
    "kit": {
      "barcode": "UL42345",
      "status": "KIT_FAILED",
      "reason": "Not enough DNA was extracted."
    }
  }
}
```

###### Report ready
```
{
  "id": 3514,
  "type": "report.updated",
  "data": {
    "report": {
      "id": 345345,
      "status": "AVAILABLE",
    }
  }
}
```

###### Report blocked - no consent
```
{
  "id": 3514,
  "type": "report.updated",
  "data": {
    "report": {
      "id": 345345,
      "status": "BLOCKED",
      "reason": "Customer consent date is not found."
    }
  }
}
```

###### Report ready - no kit registration
```
{
  "id": 3514,
  "type": "report.updated",
  "data": {
    "report": {
      "id": 345345,
      "status": "BLOCKED",
      "reason": "Kit registration verification date is not found."
    }
  }
}
```

<br />

## List Events
Retrieve details of all events.

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
        <li><code>type</code> [String]</li>
        <li><code>data</code> [Object]</li>
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
        "type": "kit.created",
        "data": {
            "kit": {
              "barcode": "PT101010111",
              "status": "KIT_SHIPPED",
              "shipment_id": 2344
            }
        }
    },
    {
        "id": 71,
        "created_at": "2017-11-24 10:01:00",
        "type": "report.updated",
        "data": {
            "report": {
              "id": 1012,
              "status": "AVAILABLE"
            }
        }
    }
]
```
