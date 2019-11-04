# Kit Registration

 
<br />

## Get Kit Regisration
Retrieve details about an individual customer by customer id.
### GET `/api/v1/kit-registrations/`
| Attribute Name | Data Type | Description
|:---|:---|:---
| id | int | Identifier of the customer.
| created_at | string | The date Kit Registration is created in standard ISO 8601 format 'YYYY-MM-DD'
| modified_at | string | The date Kit Registration is modified in standard ISO 8601 format 'YYYY-MM-DD'
| customer | Customer |  The customer of the kit registration object
| kit | Kit | The kit of the customer.
| verification_date | string | The date when the the customer registers the kit in standard ISO 8601 format 'YYYY-MM-DD'

GET partners.toolboxgenomics.com/api/v1/kit-registrations/?customer=70
Content-Type: application/json
Response:
[
 {
  "id": 68,
  "created_at": "2017-11-24T10:00:00+00:00",
  "modified_at": "2017-11-24T10:00:00+00:00",
  "customer": 70,
  "kit": "67",
  "verification_date": "2019-10-01"
 }
]

## Get a Kit Registration

### GET `/api/v1/kit-registrations/68/`
| Attribute Name | Data Type | Description
|:---|:---|:---
| id | int | Identifier of the customer.
| created_at | string | The date Kit Registration is created in standard ISO 8601 format 'YYYY-MM-DD'
| modified_at | string | The date Kit Registration is modified in standard ISO 8601 format 'YYYY-MM-DD'
| customer | Customer |  The customer of the kit registration object
| kit | Kit | The kit of the customer.
| verification_date | string | The date when the the customer registers the kit in standard ISO 8601 format 'YYYY-MM-DD'


#### Example Request

```
GET partners.toolboxgenomics.com/api/v1/kit-registrations/70/
Content-Type: application/json
```

#### Example Success Response

```
HTTP/1.0 200 OK

Content-Type: application/json
Body:
 {
  "id": 68,
  "created_at": "2017-11-24T10:00:00+00:00",
  "modified_at": "2017-11-24T10:00:00+00:00",
  "customer": 70,
  "kit": "67",
  "verification_date": "2019-10-01"
 }
```
