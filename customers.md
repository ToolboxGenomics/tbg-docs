# Customer
Customers are persons who will be receiving personalized reports based on their DNA.
 

## Create a Customer
Submit customer details.

#### POST `/api/v1/customers`

| Attribute Name | Data Type | Description                     |
|----------------|-----------|---------------------------------|
| first_name | string | The first name that will be displayed on the customer's report |
| last_name | string | The last name that will be displayed on the customer's report |
| reference_id | string | _(optional)_ The id that will be displayed on the customer's report |
| email | string | _(optional)_ |
| date_of_birth | string | _(optional)_ The date of birth of the customer in standard ISO 8601 format 'YYYY-MM-DD' |
| consent_date | string | _(optional)_ The date when the the customer provided his/her legal consent in standard ISO 8601 format 'YYYY-MM-DD' |
| gender | string | _(optional)_ The sex of the customer assigned at birth. The choices are: `male`, `female` |
| ethnicity | list of strings | _(optional)_ The ethnicty of the customer. The choices are: `asian`, `caucasian`, `latino`, `black` |
| caffeine_consumption | string | _(optional)_ Whether or not the customer consumes caffeine. The choices are: `yes`, `no` |
| diet | list of strings| _(optional)_ Any special diet of the customer. The choices are: `no_meat`, `no_gluten`, `no_dairy`, `only_fish` |


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
    "gender": "male",
    "ethnicity": ["asian", "african"],
    "caffeine_consumption": "yes",
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
  "gender": "male",
  "ethnicity": ["asian", "african"],
  "caffeine_consumption": "yes",
  "diet": ["no_meat", "no_gluten"]
}

```

## Get a Customer

Retrieve details about an individual customer by customer id.
<table>
  <tr>
    <td><strong>URL</strong></td>
    <td>/api/v1/customers/{customer-id}/</td>
  </tr>
  <tr>
    <td><strong>HTTP Method</strong></td>
    <td> GET </td>
  </tr>
  <tr>
    <td valign="top"><strong>Response<br />Attributes</strong></td>
    <td>
      <ul>
        <li><code>id</code> [Integer]</li>
        <li><code>created_at</code> [String]</li>
        <li><code>reference_id</code> [String]</li>
        <li><code>first_name</code> [String]</li>
        <li><code>last_name</code> [String]</li>
        <li><code>email</code> [String]</li>
        <li><code>date_of_birth</code> [String] </li>
        <li><code>consent_date</code> [String] </li>
        <li><code>gender</code> [String] </li>
        <li><code>ethnicity</code> [List] [String] </li>
        <li><code>caffeine_consumption</code> [String] OPTIONAL</li>
        <li><code>diet</code> [String] OPTIONAL</li>
      </ul>
    </td>
  </tr>
</table>

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
  "gender": "Male",
  "ethnicity": ["asian", "african"],
  "caffeine_consumption": "Yes",
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

## List All Customers

Retrieve details of all customers.
<table>
  <tr>
    <td><strong>URL</strong></td>
    <td> /api/v1/customers/ </td>
  </tr>
  <tr>
    <td><strong>HTTP Method</strong></td>
    <td> GET </td>
  </tr>
  <tr>
    <td valign="top"><strong>Response<br />Attributes</strong></td>
    <td>
    List of Customers with the following details:
      <ul>
        <li><code>id</code> [Integer]</li>
        <li><code>created_at</code> [String]</li>
        <li><code>reference_id</code> [String]</li>
        <li><code>first_name</code> [String]</li>
        <li><code>last_name</code> [String]</li>
        <li><code>email</code> [String]</li>
        <li><code>date_of_birth</code> [String] </li>
        <li><code>consent_date</code> [String] </li>
        <li><code>gender</code> [String] </li>
        <li><code>ethnicity</code> [List] </li>
        <li><code>caffeine_consumption</code> [String]</li>
        <li><code>diet</code> [List]</li>
      </ul>
    </td>
  </tr>
</table>


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
