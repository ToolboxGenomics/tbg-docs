# Events
Events are created when certain events occur in the life of a resource. This document explains how to retrieve events.

<br>

### Event Types

| Event | Action | Description
|:---|:---|:---
| Kit out for delivery | kit_out_for_delivery | Sent immediately when a kit is added to a shipment.
| Kit received by lab | kit_received_by_lab | Sent when the lab receives the kit.
| Kit in process | kit_in_process | Sent when the lab starts the processing of the sample.
| Kit failed | kit_failed | Sent when a replacement kit is needed.
| Kit data ready | kit_data_ready | Sent when kit's genetic data is ready.
| Report ready | report_ready | Sent when a report is ready.
| Report blocked - no consent | report_blocked_no_consent | Sent when a report is blocked because the Customer's consent_date was not provided.
| Report blocked - no kit registration | report_blocked_kit_not_registered | Sent when a report is blocked because the Kit Registration's verification_date was not provided.


### Example Data for each Event Type

###### Kit out for delivery
```
{
  "id": 3514,
  "type": "kit_out_for_delivery",
  "data": {
      "kit":
        {
          "id": 1,
          "sku": "ulta-1",
          "barcode": "TT02010201212",
          "shipment": 1,
          "created_at": "2019-11-06T05:55:15.428452Z",
          "modified_at": "2019-11-06T05:55:15.428494Z"
        }
  }
}
```

###### Kit received by lab
```
{
  "id": 3515,
  "type": "kit_received_by_lab",
  "data": {
      "kit":
        {
          "id": 1,
          "sku": "ulta-1",
          "barcode": "TT02010201212",
          "shipment": 1,
          "created_at": "2019-11-06T05:55:15.428452Z",
          "modified_at": "2019-11-06T05:55:15.428494Z"
        }
  }
}
```

###### Kit in process
```
{
  "id": 3516,
  "type": "kit_in_process",
  "data": {
      "kit":
        {
          "id": 1,
          "sku": "ulta-1",
          "barcode": "TT02010201212",
          "shipment": 1,
          "created_at": "2019-11-06T05:55:15.428452Z",
          "modified_at": "2019-11-06T05:55:15.428494Z"
        }
  }
}
```

###### Kit failed
```
{
  "id": 3517,
  "type": "kit_failed",
  "data": {
      "kit":
        {
          "id": 1,
          "sku": "ulta-1",
          "barcode": "TT02010201212",
          "shipment": 1,
          "created_at": "2019-11-06T05:55:15.428452Z",
          "modified_at": "2019-11-06T05:55:15.428494Z"
        }
  }
}
```

###### Kit data ready
```
{
  "id": 3518,
  "type": "kit_data_ready",
  "data": {
      "kit":
        {
          "id": 1,
          "sku": "ulta-1",
          "barcode": "TT02010201212",
          "shipment": 1,
          "created_at": "2019-11-06T05:55:15.428452Z",
          "modified_at": "2019-11-06T05:55:15.428494Z"
        }
  }
}
```

###### Report ready
```
{
  "id": 3519,
  "type": "report_ready",
  "data": {
      "kit":
        {
          "id": 1,
          "sku": "ulta-1",
          "barcode": "TT02010201212",
          "shipment": 1,
          "created_at": "2019-11-06T05:55:15.428452Z",
          "modified_at": "2019-11-06T05:55:15.428494Z"
        }
  }
}
```

###### Report blocked - no consent
```
{
  "id": 3520,
  "type": "report_blocked_no_consent",
  "data": {
      "kit":
        {
          "id": 1,
          "sku": "ulta-1",
          "barcode": "TT02010201212",
          "shipment": 1,
          "created_at": "2019-11-06T05:55:15.428452Z",
          "modified_at": "2019-11-06T05:55:15.428494Z"
        }
  }
}
```

###### Report ready - no kit registration
```
{
  "id": 3522,
  "type": "report_blocked_kit_not_registered",
  "data": {
      "report":
        {
          "id": 1,
          "customer": 3,
          "order": 2,
          "order_item": 15,
          "created_at": "2019-11-06T05:55:15.428452Z",
          "modified_at": "2019-11-06T05:55:15.428494Z"
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
        <li><code>action</code> [String]</li>
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
      "id": 3522,
      "type": "report_blocked_kit_not_registered",
      "data": {
      "report": {
          "id": 1,
          "customer": 3,
          "order": 2,
          "order_item": 15,
          "created_at": "2019-11-06T05:55:15.428452Z",
          "modified_at": "2019-11-06T05:55:15.428494Z"
        }
      }
    },
    {
      "id": 3518,
      "type": "kit_data_ready",
     "data": {
         "kit": {
             "id": 1,
             "sku": "ulta-1",
             "barcode": "TT02010201212",
             "shipment": 1,
             "created_at": "2019-11-06T05:55:15.428452Z",
             "modified_at": "2019-11-06T05:55:15.428494Z"
        }
    }
}
]
```
