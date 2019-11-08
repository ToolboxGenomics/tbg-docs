# Kits

DNA kit of customer.

<br />

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
