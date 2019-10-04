# Customer Panel Orders

Customer Panel Orders are orders for Panels for a specific Customer. This document explains on how to create, retrieve and cancel Customer Panel Orders.
<br />
To place a Customer Panel Order, the Customer must have an `existing Customer Shipment`.

<table>
  <tr>
    <td><strong>URL</strong></td>
    <td> /api/v1/customer-panel-orders/ </td>
  </tr>
  <tr>
    <td><strong>HTTP Method</strong></td>
    <td> POST </td>
  </tr>
  <tr>
    <td valign="top"><strong>Parameters</strong></td>
    <td>
      <ul>
        <li><code>customer_id</code> [String]</li>
        <li><code>order_items</code> [List]</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td valign="top"><strong>Response</strong></td>
    <td>
      <ul>
        <li><code>id</code> [Number/Integer]</li>
        <li><code>created_at</code> [String]</li>
        <li><code>customer_id</code> [String]</li>
        <li><code>order_items</code> [List]</li>
      </ul>
    </td>
  </tr>
</table>


#### Example

###### Request

```
POST /api/v1/customer-panel-orders/
Host: staging.partners.toolboxgenomics.com
Content-Type: application/json

Payload:
  {
    "customer_id": 319,
    "order_items": ["cardiometabolic-1", "nutri-opt-1"],
  }

```

###### Success Response

```
HTTP/1.0 201 OK 
Content-Type: application/json

{
  "id": 101,
  "created_at": "2017-11-24 10:00:00",
  "customer_id": 319,
  "order_items": [
      {
          "panel_sku": "cardiometabolic-1"
      },
      {
           "panel_sku": "nutri-opt-1"
      }
  ]
}

```

## Retrieving customer panel orders

This section describes how to retrieve all customer panel orders.

### API Access Points
#### Retrieve a Customer Panel Order
You can get Customer panel orders using this API Access Point.
<table>
  <tr>
    <td><strong>URL</strong></td>
    <td> /api/v1/customer-panel-orders/{customer-panel-order-id} </td>
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
        <li><code>customer_id</code> [String]</li>
        <li><code>order_items</code> [List]</li>
      </ul>
    </td>
  </tr>
</table>

#### Example


##### Request

```
GET /api/v1/customer-panel-orders/70/
Host: staging.partners.toolboxgenomics.com
Content-Type: application/json

```

##### Success Response

```
HTTP/1.0 200 OK 
Content-Type: application/json

{
  "id": 101,
  "created_at": "2017-11-24 10:00:00",
  "customer_id": 319,
  "order_items": [
      {
          "panel_sku": "cardiometabolic-1"
      },
      {
           "panel_sku": "nutri-opt-1"
      }
  ]
}
```

#### Retrieve all Customer Panel Orders
You can get all your Customer Panel Orders using this API Access Point.
<table>
  <tr>
    <td><strong>URL</strong></td>
    <td> /api/v1/customer-panel-orders/ </td>
  </tr>
  <tr>
    <td><strong>HTTP Method</strong></td>
    <td> GET </td>
  </tr>
  <tr>
    <td valign="top"><strong>Response</strong></td>
    <td>
    List of Customer Panel Orders with the following details:
      <ul>
        <li><code>id</code> [Number/Integer]</li>
        <li><code>created_at</code> [String]</li>
        <li><code>customer_id</code> [String]</li>
        <li><code>order_items</code> [List]</li>
      </ul>
    </td>
  </tr>
</table>

#### Example


##### Request

```
GET /api/v1/customer-panel-orders/
Host: staging.partners.toolboxgenomics.com
Content-Type: application/json

```

##### Success Response

```
HTTP/1.0 200 OK 
Content-Type: application/json

[
    {
        "id": 101,
        "created_at": "2017-11-24 10:00:00",
        "customer_id": 319,
        "order_items": [
            {
                "panel_sku": "cardiometabolic-1"
            },
            {
                "panel_sku": "nutri-opt-1"
            }
        ]
    },
    {
        "id": 102,
        "created_at": "2017-11-24 10:01:00",
        "customer_id": 320,
        "order_items": [
            {
                "panel_sku": "weight-management-1"
            },
            {
                "panel_sku": "hormone-1"
            }
        ]
    },
]
```
