# Kits

DNA kit of customer.

<br />

## Create Kit
### POST `/api/v1/kits/ `

| Attribute Name | Data Type | Description
|:---|:---|:---
| id | Integer | ID of the kit.
| shipment | | The Shipment where the kit is from.
| barcode | String | Identifier of the Panel.
| sku | String | The SKU of the kit.
| status | String | The current status of the kit.

#### Example

###### Request

```
POST /api/v1/kits/
Host: staging.partners.toolboxgenomics.com
Content-Type: application/json

Payload:
  {
    "barcode": "MK1000088111"
  }

```

###### Response

```
Response:
  {
    "barcode": "MK1000088111"
  }

```

## Get Kits
### GET `/api/v1/kits/ `

| Attribute Name | Data Type | Description
|:---|:---|:---
| id | Integer | ID of the kit.
| shipment | | The Shipment where the kit is from.
| barcode | String | Identifier of the Panel.
| sku | String | The SKU of the kit.
| status | String | The current status of the kit.

#### Example

###### Response

```
GET /api/v1/kits/
Host: staging.partners.toolboxgenomics.com
Content-Type: application/json

Response:
[
  {
    "id": 65,
    "shipment": 66
    "barcode": "MK1000088111",
    "sku": "MyKit-1",
  },
  {
    "id": 66,
    "shipment": 67
    "barcode": "MK1000088112",
    "sku": "MyKit-1",
  }
]

```
## Get a kit
### GET `/api/v1/kits/<id>/ `

| Attribute Name | Data Type | Description
|:---|:---|:---
| id | Integer | ID of the kit.
| shipment | | The Shipment where the kit is from.
| barcode | String | Identifier of the Panel.
| sku | String | The SKU of the kit.
| status | String | The current status of the kit.

#### Example

###### Response

```
GET /api/v1/kits/66/
Host: staging.partners.toolboxgenomics.com
Content-Type: application/json

Response:
{
  "id": 66,
  "shipment": 67
  "barcode": "MK1000088112",
  "sku": "MyKit-1",
}

```

## Kit Statuses
| Event | Status | Description
|:---|:---|:---
| Kit out for delivery | KIT_SHIPPED | Sent immediately when a kit is added to a shipment.
| Kit received by lab | KIT_RECEIVED | Sent when the lab receives the kit.
| Kit in process | SAMPLE_IN_PROCESS | Sent when the lab starts the processing of the sample.
| Kit failed | KIT_UNUSABLE | Sent when a replacement kit is needed.
| Kit lost | KIT_LOST | Sent when a kit got lost and replacement kit is needed.
| Kit data ready | DATA_AVAILABLE | Sent when kit's genetic data is ready.
