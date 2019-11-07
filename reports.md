# Reports

This section describes how to get order reports.

## List all Reports
### GET `/api/v1/reports/`

List all Reports.

| Attribute Name | Data Type | Description
|:---|:---|:---
| id | integer| System generated `id` of Toolbox Genomics API after Order creation.
| created_at | date | The datetime Shipment is created.
| customer | integer| The intended recipient of the shipment.  This `id` can be obtained from the Toolbox Genomics API after Customer creation.
| order | integer | The Order of the Report.
| order_item | integer | The Order Item of the Report.


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
    "status": "pending",
    "customer": 2,
    "order": 211,
    "order_list": 3105
  },
  {
    "id": 69,
    "client_id": 320,
    "created_at": "2017-11-24 10:00:00",
    "status": "pending",
    "customer": 2,
    "order": 211,
    "order_list": 3106
  },
    {
    "id": 68,
    "client_id": 315,
    "created_at": "2017-11-24 10:00:00",
    "status": "report-ready",
    "customer": 2,
    "order": 211,
    "order_list": 3106
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
| customer | integer| The intended recipient of the shipment.  This `id` can be obtained from the Toolbox Genomics API after Customer creation.
| order | integer | The Order of the Report.
| order_item | integer | The Order Item of the Report.
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
  "status": "pending",
  "customer": 2,
  "order": 211,
  "order_list": 3105
}
```
## List all Reports of a Customer
### GET `/api/v1/reports/?customer_id={customer-id}`

Retrieve the list of all Reports.

| Attribute Name | Data Type | Description
|:---|:---|:---
| id | integer| System generated `id` of Toolbox Genomics API after Shipment creation.
| created_at | date | The datetime Shipment is created.
| customer | integer| The intended recipient of the shipment.  This `id` can be obtained from the Toolbox Genomics API after Customer creation.
| order | integer | The Order of the Report.
| order_item | integer | The Order Item of the Report.


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


## list Report Files
### GET `/api/v1/report-files/`


| Attribute Name | Data Type | Description
|:---|:---|:---
| id | integer| system generated `id` of toolbox genomics api after order creation.
| report | integer| system generated `id` of the report.
| created_at | date | the datetime shipment is created.
| category | string| the category of the report file, can be 'health-action-plan`, 'practitioner-summary', 'supplements', 'client-summary'.
| download_link | url | the link where the file can be downloaded.


#### example request

```
GET /api/v1/report-files/
host: staging.partners.toolboxgenomics.com
content-type: application/json

```

#### example response

```
http/1.0 200 ok 
content-type: application/json
[
  {
    "id": 1,
    "report": 70,
    "created_at": "2017-11-30 10:00:00",
    "category": "health-action-plan",
    "download_link: "https://staging.partners.toolboxgenomics.com/report-files/1/download/"
  },
  {
    "id": 2,
    "report": 70,
    "created_at": "2017-11-30 10:00:00",
    "category": "practitioner-summary",
    "download_link: "https://staging.partners.toolboxgenomics.com/report-files/2/download/"
  },
  {
    "id": 3,
    "report": 71,
    "created_at": "2017-11-30 10:00:00",
    "category": "health-action-plan",
    "download_link: "https://staging.partners.toolboxgenomics.com/report-files/3/download/"
  },
  {
    "id": 4,
    "report": 71,
    "created_at": "2017-11-30 10:00:00",
    "category": "practitioner-summary",
    "download_link: "https://staging.partners.toolboxgenomics.com/report-files/4/download/"
  },
]
```

<br />

## list a report's report files
### get `/api/v1/report-files/?report_id={report-id}`

list a report's report files. only reports with `report-ready` status will have report files

| Attribute Name | Data Type | Description
|:---|:---|:---
| id | integer| system generated `id` of toolbox genomics api after order creation.
| report | integer| system generated `id` of the report.
| created_at | date | the datetime shipment is created.
| category | string| the category of the report file, can be 'health-action-plan`, 'practitioner-summary', 'supplements', 'client-summary'.
| download_link | url | the link where the file can be downloaded.


#### example request

```
get /api/v1/report-files/?report_id=70
host: staging.partners.toolboxgenomics.com
content-type: application/json

```

#### example response

```
http/1.0 200 ok 
content-type: application/json
[
  {
    "id": 1,
    "report": 70,
    "created_at": "2017-11-30 10:00:00",
    "category": "health-action-plan",
    "download_link: "https://staging.partners.toolboxgenomics.com/report-files/3/download/"
  },
  {
    "id": 2,
    "report": 70,
    "created_at": "2017-11-30 10:00:00",
    "category": "practitioner-summary",
    "download_link: "https://staging.partners.toolboxgenomics.com/report-files/4/download/"
  },
]
```

<br />


## Retrieve a Report File
### get `/api/v1/report-files/{report-files-id}`

Retrieve a Report File.

| Attribute Name | Data Type | Description
|:---|:---|:---
| id | integer| system generated `id` of toolbox genomics api after order creation.
| report_id | integer| system generated `id` of the report.
| created_at | date | the datetime shipment is created.
| category | string| the category of the report file, can be 'health-action-plan`, 'practitioner-summary', 'supplements', 'client-summary'.
| download_link | url | the link where the file can be downloaded.


#### example request

```
GET /api/v1/report-files/1/
host: staging.partners.toolboxgenomics.com
content-type: application/json

```

#### example response

```
http/1.0 200 ok 
content-type: application/json
{
  "id": 1,
  "report_id": 70,
  "created_at": "2017-11-30 10:00:00",
  "category": "health-action-plan",
  "download_link: "https://staging.partners.toolboxgenomics.com/report-files/3/download/"
}
```

<br />
