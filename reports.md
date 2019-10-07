# Reports

This section describes how to get order reports.

## List all Reports
### GET `/api/v1/reports/`

List all Reports.

| Attribute Name | Data Type | Description
|:---|:---|:---
| id | integer| System generated `id` of Toolbox Genomics API after Order creation.
| created_at | date | The datetime Shipment is created.
| customer_id | integer| The intended recipient of the shipment.  This `id` can be obtained from the Toolbox Genomics API after Customer creation.
| panel | Object | The Panel of the Report.
| report_files | Object | The Report Files of the Report.


#### Example Request

```
GET /api/v1/reports/
Host: staging.partners.toolboxgenomics.com
Content-Type: application/json

```

#### Example Response

```
HTTP/1.0 200 OK 
Content-Type: application/json
[
  {
    "id": 70,
    "client_id": 319,
    "created_at": "2017-11-24 10:00:00",
    "status": "report-ready",
    "panel": {
      "name": "Cardiometabolic Panel",
      "sku": "cardiometabolic-1",
      "description": "Description",
    }
  },
  {
    "id": 69,
    "client_id": 320,
    "created_at": "2017-11-24 10:00:00",
    "status": "pending",
    "panel": {
      "name": "Hormone Panel",
      "sku": "hormone-1",
      "description": "Description",
    },
  }
]
```

<br />

## Retrieve a  Report
### GET `/api/v1/reports/{report-id}`

Retrieve a Report.

| Attribute Name | Data Type | Description
|:---|:---|:---
| id | integer| System generated `id` of Toolbox Genomics API after Order creation.
| created_at | date | The datetime Shipment is created.
| customer_id | integer| The intended recipient of the shipment.  This `id` can be obtained from the Toolbox Genomics API after Customer creation.
| panel | Object | The Panel of the Report.
| report_files | Object | The Report Files of the Report.


#### Example Request

```
GET /api/v1/reports/70/
Host: staging.partners.toolboxgenomics.com
Content-Type: application/json

```

#### Example Response

```
HTTP/1.0 200 OK 
Content-Type: application/json
{
  "id": 70,
  "client_id": 319,
  "created_at": "2017-11-24 10:00:00",
  "status": "report-ready",
  "panel": {
    "name": "Cardiometabolic Panel",
    "sku": "cardiometabolic-1",
    "description": "Description",
  }
}
```
## List all Reports of a Customer
### GET `/api/v1/reports/?customer_id={customer-id}`

Retrieve the list of all Reports.

| Attribute Name | Data Type | Description
|:---|:---|:---
| id | integer| System generated `id` of Toolbox Genomics API after Shipment creation.
| created_at | date | The datetime Shipment is created.
| customer_id | integer| The intended recipient of the shipment.  This `id` can be obtained from the Toolbox Genomics API after Customer creation.
| panel | Object | The Panel of the Report.
| report_files | Object | The Report Files of the Report.


#### Example Request

```
GET /api/v1/reports/?client_id=319
Host: staging.partners.toolboxgenomics.com
Content-Type: application/json

```

#### Example Response

```
HTTP/1.0 200 OK 
Content-Type: application/json

[
  {
    "id": 70,
    "client_id": 319,
    "created_at": "2017-11-24 10:00:00",
    "status": "report-ready",
    "panel": {
      "name": "Cardiometabolic Panel",
      "sku": "cardiometabolic-1",
      "description": "Description",
    }
  },
  {
    "id": 71,
    "client_id": 319,
    "created_at": "2017-11-24 10:00:00",
    "status": "report-ready",
    "panel": {
      "name": "Hormone Panel",
      "sku": "hormone-1",
      "description": "Description",
    }
  }
]
```

## List a Report's Report Files
### GET `/api/v1/report-files/?report_id={report-id}`

List a Report's Report Files. Only Reports with `report-ready` status will have Report Files

| Attribute Name | Data Type | Description
|:---|:---|:---
| id | integer| System generated `id` of Toolbox Genomics API after Order creation.
| report_id | integer| System generated `id` of the Report.
| created_at | date | The datetime Shipment is created.
| category | string| The category of the Report File, can be 'health-action-plan`, 'practitioner-summary', 'supplements', 'client-summary'.
| download_link | URL | The link where the file can be downloaded.


#### Example Request

```
GET /api/v1/report-files/?report_id=70
Host: staging.partners.toolboxgenomics.com
Content-Type: application/json

```

#### Example Response

```
HTTP/1.0 200 OK 
Content-Type: application/json
[
  {
    "id": 1,
    "report_id": 70,
    "created_at": "2017-11-30 10:00:00",
    "category": "health-action-plan",
    "download_link: "https://staging.partners.toolboxgenomics.com/report-files/3/download/"
  },
  {
    "id": 2,
    "report_id": 70,
    "created_at": "2017-11-30 10:00:00",
    "category": "practitioner-summary",
    "download_link: "https://staging.partners.toolboxgenomics.com/report-files/4/download/"
  },
]
```

<br />