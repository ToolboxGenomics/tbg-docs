# Panels

Panel you can order for a specific Customer. This document explains on how to retrieve Panel.

<br />

## Get Trait Panels
### GET `/api/v1/trait-panels/ `

| Attribute Name | Data Type | Description
|:---|:---|:---
| id | Integer | ID of the panel.
| name | | Name of the Panel.
| sku | String | Identifier of the Panel.
| is_license_required | Boolean | If a licensed practitioner is required for the specific Panel.
| phenotype_groups | List | List of phenotype groups under the Panel

#### Example

###### Response

```
GET /api/v1/trait-panels/
Host: staging.partners.toolboxgenomics.com
Content-Type: application/json

Payload:
[
  {
    "id": 1,
    "sku": "cardiometabolic-1"
    "is_license_required": false,
    "phenotype_groups": [
      "Oxidative Stress"
    ]
  },
  {
    "id": 2,
    "sku": "detox-1"
    "is_license_required": true,
    "phenotype_groups": [
      "Inflammation", . . .
    ]
  }
]

```
## Get Raw Panels
### GET `/api/v1/raw-panels/ `

| Attribute Name | Data Type | Description
|:---|:---|:---
| id | Integer | ID of the Panel.
| name | | Name of the Panel.
| sku | String | Identifier of the Panel.
| is_license_required | Boolean | If a licensed practitioner is required for the specific Panel.
| snps | List | List of snps under the Panel

#### Example

###### Response

```
GET /api/v1/raw-panels/
Host: staging.partners.toolboxgenomics.com
Content-Type: application/json

Payload:
[
  {
    "id": 1,
    "sku": "raw-panel-1"
    "is_license_required": false,
    "snps": ["rs2312", "rs39230",. . . . ]
  },
  {
    "id": 2,
    "sku": "apoe-1"
    "is_license_required": True
    "snps": ["rs2312", "rs39230",. . . . ]
  }
]

```

## Get Multi Trait Panels
### GET `/api/v1/multi-trait-panels/ `

| Attribute Name | Data Type | Description
|:---|:---|:---
| id | Integer | ID of the panel.
| trait_panels | | Name of the Panel.
| sku | String | Identifier of the Panel.
| is_license_required | Boolean | If a licensed practitioner is required for the specific Panel.

#### Example

###### Response

```
GET /api/v1/multi-trait-panels/
Host: staging.partners.toolboxgenomics.com
Content-Type: application/json

Payload:
[
  {
    "id": 6,
    "sku": "health-report-1"
    "is_license_required": false,
    "trait_panels": [
      {
        7: "performance-1",
        8: "metabolism-1",
        9: "nutrition-1"
      }
    ]
  },
  {
    "id": 7,
    "sku": "health-report-2"
    "is_license_required": false,
    "trait_panels": [
      {
        10: "empower-1",
        11: "cardiometabolic-1",
        12: "immune-1"
      }
    ]
  },
]

```
