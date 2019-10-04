# Customer
Customers are persons who will be receiving personalized reports based on their DNA.
 
### Create a Customer
Submit customer details. This should be done prior to creating a Customer Shipment.
<table>
  <tr>
    <td><strong>URL</strong></td>
    <td> /api/v1/customers/ </td>
  </tr>
  <tr>
    <td><strong>HTTP Method</strong></td>
    <td> POST </td>
  </tr>
  <tr>
    <td valign="top"><strong>Request<br />Attributes</strong></td>
    <td>
      <ul>
        <li><code>reference_id</code> [String]</li>
        <li><code>first_name</code> [String]</li>
        <li><code>last_name</code> [String]</li>
        <li><code>email</code> [String]</li>
        <li><code>date_of_birth</code> [String] 'YYYY-MM-DD' </li>
        <li><code>consent_date</code> [String] 'YYYY-MM-DD' </li>
        <li><code>gender</code> [String] OPTIONAL</li>
        <li><code>ethnicity</code> [List] [String] OPTIONAL</li>
        <li><code>caffeine_consumption</code> [String] OPTIONAL</li>
        <li><code>diet</code> [List] [String] OPTIONAL</li>
      </ul>
    </td>
  </tr>
</table>


#### Example Request
```
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

```
HTTP/1.0 201 OK

Content-Type: application/json

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

### Get a Customer

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

#### List All Customers

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
