
# Customer
<br><br>
This document explains on how to create and retrieve customers in your account.
<br><br>


<table>
  <tr>
    <td><strong>URL</strong></td>
    <td> /api/v1/customer/ </td>
  </tr>
  <tr>
    <td><strong>HTTP Method</strong></td>
    <td> POST </td>
  </tr>
  <tr>
    <td valign="top"><strong>Parameters</strong></td>
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
        <li><code>caffeine_consumption</code> [List] [String] OPTIONAL</li>
        <li><code>diet</code> [List] [String] OPTIONAL</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td valign="top"><strong>Response</strong></td>
    <td>
      <ul>
        <li><code>id</code> [Number/Integer]</li>
        <li><code>created_at</code> [String]</li>
        <li><code>reference_id</code> [String]</li>
        <li><code>first_name</code> [String]</li>
        <li><code>last_name</code> [String]</li>
        <li><code>email</code> [String]</li>
        <li><code>date_of_birth</code> [String] </li>
        <li><code>consent_date</code> [String] </li>
        <li><code>gender</code> [String] </li>
        <li><code>ethnicity</code> [List] </li>
        <li><code>caffeine_consumption</code> [List]</li>
        <li><code>diet</code> [List]</li>
      </ul>
    </td>
  </tr>
</table>


#### Example

###### Request

```
POST /api/v1/customers/
Host: staging.partners.toolboxgenomics.com
Content-Type: application/json

Payload:
  {
    "reference_id": "cs7010",
    "first_name": "Jon",
    "last_name": "Snow",
    "email": Jon.snow@winterfell.com,
    "date_of_birth": "1996-01-28",
    "gender": "Male",
    "ethnicity": "on-demand",
    "ethnicity": ["asian", "african"],
    "caffeine_consumption": "Yes",
    "diet": ["no_meat", "no_gluten"]
  }

```

###### Success Response

```
HTTP/1.0 201 OK 
Content-Type: application/json

{
  "id": 319,
  "created_at": "2017-11-24 10:00:00",
  "reference_id": "cs7010",
  "first_name": "Jon",
  "last_name": "Snow",
  "email": Jon.snow@winterfell.com,
  "date_of_birth": "1996-01-28",
  "gender": "Male",
  "ethnicity": "on-demand",
  "ethnicity": ["asian", "african"],
  "caffeine_consumption": "Yes",
  "diet": ["no_meat", "no_gluten"]

}

```

## Retrieving Customers

This section describes how to retrieve all customers.

### API Access Points
#### Retrieve order details
You can get order details using this API Access Point.
<table>
  <tr>
    <td><strong>URL</strong></td>
    <td> /customers/{customer-id} </td>
  </tr>
  <tr>
    <td><strong>HTTP Method</strong></td>
    <td> GET </td>
  </tr>
  <tr>
    <td valign="top"><strong>Response</strong></td>
    <td>
      <ul>
        <li><code>id</code> [Number/Integer]</li>
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

#### Example


##### Request

```
GET /api/v1/customers/319/
Host: staging.partners.toolboxgenomics.com
Content-Type: application/json

```

##### Success Response

```
HTTP/1.0 200 OK 
Content-Type: application/json

{
  "id": 319,
  "created_at": "2017-11-24 10:00:00",
  "reference_id": "cs7010",
  "first_name": "Jon",
  "last_name": "Snow",
  "email": Jon.snow@winterfell.com,
  "date_of_birth": "1996-01-28",
  "gender": "Male",
  "ethnicity": "on-demand",
  "ethnicity": ["asian", "african"],
  "caffeine_consumption": "Yes",
  "diet": ["no_meat", "no_gluten"]

}
```

#### Retrieve ALL customers
You can get all your customers using this API endpoint.
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
    <td valign="top"><strong>Response</strong></td>
    <td>
    List of Customers with the following details:
      <ul>
        <li><code>id</code> [Number/Integer]</li>
        <li><code>created_at</code> [String]</li>
        <li><code>reference_id</code> [String]</li>
        <li><code>first_name</code> [String]</li>
        <li><code>last_name</code> [String]</li>
        <li><code>email</code> [String]</li>
        <li><code>date_of_birth</code> [String] </li>
        <li><code>consent_date</code> [String] </li>
        <li><code>gender</code> [String] </li>
        <li><code>ethnicity</code> [List] </li>
        <li><code>caffeine_consumption</code> [List]</li>
        <li><code>diet</code> [List]</li>
      </ul>
    </td>
  </tr>
</table>

#### Example


##### Request

```
GET api/v1/customers/
Host: staging.partners.toolboxgenomics.com
Content-Type: application/json

```

##### Success Response

```
HTTP/1.0 200 OK 
Content-Type: application/json

[
    {
        "id": 319,
        "created_at": "2017-11-24 10:00:00",
        "reference_id": "cs7010",
        "first_name": "Jon",
        "last_name": "Snow",
        "email": Jon.snow@winterfell.com,
        "date_of_birth": "1996-01-28",
        "gender": "Male",
        "ethnicity": "on-demand",
        "ethnicity": ["asian", "african"],
        "caffeine_consumption": "Yes",
        "diet": ["no_meat", "no_gluten"]

    },
    {
        "id": 319,
        "created_at": "2017-11-24 10:00:00",
        "reference_id": "cs7010",
        "first_name": "Jon",
        "last_name": "Snow",
        "email": Jon.snow@winterfell.com,
        "date_of_birth": "1996-01-28",
        "gender": "Male",
        "ethnicity": "on-demand",
        "ethnicity": ["asian", "african"],
        "caffeine_consumption": "Yes",
        "diet": ["no_meat", "no_gluten"]

    },
]
```