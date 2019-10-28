# Customer
Customers are persons who will be receiving personalized reports based on their DNA.
 
<br />

## Create a Customer
Submit customer details.


#### POST `/api/v1/customers/`

| Attribute Name | Data Type | Description
|:---|:---|:---
| first_name | string | The first name that will be displayed on the customer's report
| last_name | string | The last name that will be displayed on the customer's report
| reference_id | string | _(optional)_ The id that will be displayed on the customer's report
| email | string | _(optional)_
| date_of_birth | string | _(optional)_ The date of birth of the customer in standard ISO 8601 format 'YYYY-MM-DD'
| consent_date | string | _(optional)_ The date when the the customer provided his/her legal consent in standard ISO 8601 format 'YYYY-MM-DD'
| sex | string | _(optional)_ The sex of the customer assigned at birth. The choices are: `male`, `female`
| ethnicity | list of strings | _(optional)_ The ethnicty of the customer. The choices are: `asian`, `caucasian`, `latino`, `african`
| caffeine_consumption | Boolean | _(optional)_ Whether or not the customer consumes caffeine. The choices are: `yes`, `no`
| diet | list of strings| _(optional)_ Any special diet of the customer. The choices are: `no_meat`, `no_gluten`, `no_dairy`, `only_fish`


#### Example Request
```json
Method: POST partners.toolboxgenomics.com/api/v1/customers/
Content-Type: application/json
Body:
  {
    "reference_id": "cs7010",
    "first_name": "Jon",
    "last_name": "Snow",
    "email": "jon.snow@winterfell.com",
    "date_of_birth": "1996-01-28",
    "consent_date": "2019-10-01",
    "sex": "male",
    "ethnicity": ["asian", "african"],
    "caffeine_consumption": true,
    "diet": ["no_meat", "no_gluten"]
  }

```

#### Example Success Response

```json
HTTP/1.0 201 OK

Content-Type: application/json
Body:
{
  "id": 319,
  "created_at": "2017-11-24 10:00:00",
  "reference_id": "cs7010",
  "first_name": "Jon",
  "last_name": "Snow",
  "email": "jon.snow@winterfell.com",
  "date_of_birth": "1996-01-28",
  "consent_date": "2019-10-01",
  "sex": "male",
  "ethnicity": ["asian", "african"],
  "caffeine_consumption": true,
  "diet": ["no_meat", "no_gluten"]
}

```

<br />

## Get a Customer

Retrieve details about an individual customer by customer id.
### GET `/api/v1/customers/{customer-id}/`
| Attribute Name | Data Type | Description
|:---|:---|:---
| id | int | Identifier of the customer.
| created_at | string | The date customer is created in standard ISO 8601 format 'YYYY-MM-DD'
| first_name | string | The first name that will be displayed on the customer's report
| last_name | string | The last name that will be displayed on the customer's report
| reference_id | string |  The id that will be displayed on the customer's report
| email | string | Email of the customer
| date_of_birth | string | The date of birth of the customer in standard ISO 8601 format 'YYYY-MM-DD'
| consent_date | string | The date when the the customer provided his/her legal consent in standard ISO 8601 format 'YYYY-MM-DD'
| sex | string | The sex of the customer assigned at birth. The choices are: `male`, `female`
| ethnicity | list of strings | The ethnicty of the customer. The choices are: `asian`, `caucasian`, `latino`, `black`
| caffeine_consumption | string | Whether or not the customer consumes caffeine. The choices are: `yes`, `no`
| diet | list of strings| Any special diet of the customer. The choices are: `no_meat`, `no_gluten`, `no_dairy`, `only_fish`

#### Example Request

```
GET partners.toolboxgenomics.com/api/v1/customers/319/
Content-Type: application/json
Body:
{
  "id": 319,
  "created_at": "2017-11-24T10:00:00+00:00",
  "reference_id": "cs7010",
  "first_name": "Jon",
  "last_name": "Snow",
  "email": "jon.snow@winterfell.com",
  "date_of_birth": "1996-01-28",
  "consent_date": "2019-10-01",
  "sex": "Male",
  "ethnicity": ["asian", "african"],
  "caffeine_consumption": true,
  "diet": ["no_meat", "no_gluten"]
}
```

#### Example Success Response

```
HTTP/1.0 200 OK

Content-Type: application/json
Body:
{
  "id": 319,
  "created_at": "2017-11-24T10:00:00+00:00",
  "reference_id": "cs7010",
  "first_name": "Jon",
  "last_name": "Snow",
  "email": "jon.snow@winterfell.com",
  "date_of_birth": "1996-01-28",
  "consent_date": "2019-10-01",
  "gender": "Male",
  "ethnicity": ["asian", "african"],
  "caffeine_consumption": "Yes",
  "diet": ["no_meat", "no_gluten"]
}
```

<br />

## List All Customers

Retrieve details of all customers.
### GET `/api/v1/customers/`
| Attribute Name | Data Type | Description
|:---|:---|:---
| id | int | Identifier of the customer.
| created_at | string | The date customer is created in standard ISO 8601 format 'YYYY-MM-DD'
| first_name | string | The first name that will be displayed on the customer's report
| last_name | string | The last name that will be displayed on the customer's report
| reference_id | string |  The id that will be displayed on the customer's report
| email | string | Email of the customer
| date_of_birth | string | The date of birth of the customer in standard ISO 8601 format 'YYYY-MM-DD'
| consent_date | string | The date when the the customer provided his/her legal consent in standard ISO 8601 format 'YYYY-MM-DD'
| gender | string | The sex of the customer assigned at birth. The choices are: `male`, `female`
| ethnicity | list of strings | The ethnicty of the customer. The choices are: `asian`, `caucasian`, `latino`, `black`
| caffeine_consumption | Boolean | Whether or not the customer consumes caffeine. The choices are: `yes`, `no`
| diet | list of strings| Any special diet of the customer. The choices are: `no_meat`, `no_gluten`, `no_dairy`, `only_fish`


#### Example Request

```
GET partners.toolboxgenomics.com/api/v1/customers/
Content-Type: application/json
```

#### Example Success Response

```
HTTP/1.0 200 OK

Content-Type: application/json
Body:
[
    {
        "id": 319,
        "created_at": "2017-11-24 10:00:00",
        "reference_id": "cs7010",
        "first_name": "Jon",
        "last_name": "Snow",
        "email": "jon.snow@winterfell.com",
        "date_of_birth": "1996-01-28",
        "consent_date": "2019-10-01",
        "gender": "Male",
        "ethnicity": ["asian", "african"],
        "caffeine_consumption": "Yes",
        "diet": ["no_meat", "no_gluten"]

    },
    {
        "id": 320,
        "created_at": "2017-11-24 10:00:00",
        "reference_id": "cs7010",
        "first_name": "Sansa",
        "last_name": "Stark",
        "email": "sansa.stark@winterfell.com",
        "date_of_birth": "1996-01-28",
        "consent_date": "2019-10-01",
        "gender": "Male",
        "ethnicity": ["asian", "african"],
        "caffeine_consumption": "Yes",
        "diet": ["no_meat", "no_gluten"]

    },
    {...},
    {...}
]
```
