
# Shipments
<br><br>
This document explains on how to create, retrieve and cancel shipments in your account.
<br><br>

<table>
  <tr>
    <td><strong>URL</strong></td>
    <td> /api/v1/customer-shipment/ </td>
  </tr>
  <tr>
    <td><strong>HTTP Method</strong></td>
    <td> POST </td>
  </tr>
  <tr>
    <td valign="top"><strong>Parameters</strong></td>
    <td>
      <ul>
        <li><code>recipient_address</code> [String]</li>
        <li><code>recipient_phone</code> [String]</li>
        <li><code>recipient_name</code> [String]</li>
        <li><code>sku</code> [String] </li>
        <li><code>quantity</code> [Int] </li>
        <li><code>customer_id</code> [Int] id of the customer</li>
        <li><code>is_replacement</code> [Bool]</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td valign="top"><strong>Response</strong></td>
    <td>
      <ul>
        <li><code>id</code> [Number/Integer]</li>
        <li><code>created_at</code> [String]</li
        <li><code>recipient_address</code> [String]</li>
        <li><code>recipient_phone</code> [String]</li>
        <li><code>recipient_name</code> [String]</li>
        <li><code>status</code> [String]</li>
        <li><code>tracking_number</code> [String]</li>
        <li><code>sku</code> [String] </li>
        <li><code>quantity</code> [Int] </li>
        <li><code>customer_id</code> [Int] id of the customer</li>
        <li><code>is_replacement</code> [Bool]</li>
      </ul>
    </td>
  </tr>
</table>


#### Example

###### Request

```
POST /api/v1/customer-shipments/
Host: staging.partners.toolboxgenomics.com
Content-Type: application/json

Payload:
  {
    "recipient_address": "Winterfell",
    "recipient_phone": "Jon",
    "recipient_name": "Snow",
    "sku": "PT-Kit-1",
    "quantity": 1,
    "customer_id": 319,
    "is_replacement": False
  }

```

###### Success Response

```
HTTP/1.0 201 OK 
Content-Type: application/json

{
  "id": 70,
  "created_at": "2017-11-24 10:00:00",
  "recipient_address": "winterfell",
  "recipient_phone": "jon",
  "recipient_name": "snow",
  "sku": "pt-kit-1",
  "status": "pending",
  "tracking_no": null
  "quantity": 1,
  "customer_id": 319,
  "is_replacement": false

}

```

## Retrieving customer shipments

This section describes how to retrieve all customer shipments.

### API Access Points
#### Retrieve Customer Shipment details
You can get Customer Shipment details using this API Access Point.
<table>
  <tr>
    <td><strong>URL</strong></td>
    <td> /api/v1/customer-shipment/{customer-shipment-id} </td>
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
        <li><code>recipient_address</code> [String]</li>
        <li><code>recipient_phone</code> [String]</li>
        <li><code>recipient_name</code> [String]</li>
        <li><code>status</code> [String]</li>
        <li><code>tracking_number</code> [String]</li>
        <li><code>sku</code> [String] </li>
        <li><code>quantity</code> [Int] </li>
        <li><code>customer_id</code> [Int] id of the customer</li>
        <li><code>is_replacement</code> [Bool]</li>
      </ul>
    </td>
  </tr>
</table>

#### Example


##### Request

```
GET /api/v1/customer-shipments/70/
Host: staging.partners.toolboxgenomics.com
Content-Type: application/json

```

##### Success Response

```
HTTP/1.0 200 OK 
Content-Type: application/json

{
  "id": 70,
  "created_at": "2017-11-24 10:00:00",
  "recipient_address": "Winterfell",
  "recipient_phone": "Jon",
  "recipient_name": "Snow",
  "sku": "PT-Kit-1",
  "status": "PENDING",
  "tracking_no": null
  "quantity": 1,
  "customer_id": 319,
  "is_replacement": False

}
```

#### Retrieve all Customer Shipments
You can get all your Customer Shipments using this API Access Point.
<table>
  <tr>
    <td><strong>URL</strong></td>
    <td> /api/v1/customer-shipments/ </td>
  </tr>
  <tr>
    <td><strong>HTTP Method</strong></td>
    <td> GET </td>
  </tr>
  <tr>
    <td valign="top"><strong>Response</strong></td>
    <td>
    List of Customer Shipments with the following details:
      <ul>
        <li><code>id</code> [Number/Integer]</li>
        <li><code>created_at</code> [String]</li
        <li><code>recipient_address</code> [String]</li>
        <li><code>recipient_phone</code> [String]</li>
        <li><code>recipient_name</code> [String]</li>
        <li><code>status</code> [String]</li>
        <li><code>tracking_number</code> [String]</li>
        <li><code>sku</code> [String] </li>
        <li><code>quantity</code> [Int] </li>
        <li><code>customer_id</code> [Int] id of the customer</li>
        <li><code>is_replacement</code> [Bool]</li>
      </ul>
    </td>
  </tr>
</table>

#### Example


##### Request

```
GET /api/v1/customer-shipments/
Host: staging.partners.toolboxgenomics.com
Content-Type: application/json

```

##### Success Response

```
HTTP/1.0 200 OK 
Content-Type: application/json

[
    {
      "id": 70,
      "created_at": "2017-11-24 10:00:00",
      "recipient_address": "winterfell",
      "recipient_phone": "jon",
      "recipient_name": "snow",
      "sku": "pt-kit-1",
      "status": "pending",
      "tracking_no": null
      "quantity": 1,
      "customer_id": 319,
      "is_replacement": false
    },
    {
      "id": 71,
      "created_at": "2017-11-24 10:01:00",
      "recipient_address": "Winterfell",
      "recipient_phone": "Nancy Jewel",
      "recipient_name": "McDonie",
      "sku": "pt-kit-1",
      "status": "pending",
      "tracking_no": null
      "quantity": 1,
      "customer_id": 320,
      "is_replacement": false

    },
]
```