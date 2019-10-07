# Customer Panel Orders

Customer Panel Orders are orders for Panels for a specific Customer. This document explains on how to create, retrieve and cancel Customer Panel Orders.

<br />

## Create a Customer Panel Order
### POST `/api/v1/customer-panel-orders/ `

| Attribute Name | Data Type | Description
|:---|:---|:---
| customer_id | integer| The Customer for the order.  This `id` can be obtained from the Toolbox Genomics API after Customer creation.
| order_items | Object | Orders.

#### Example

###### Request

```
POST /api/v1/customer-panel-orders/
Host: staging.partners.toolboxgenomics.com
Content-Type: application/json

Payload:
  {
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

## Get a Customer Panel Order
### GET `/api/v1/customer-panel-orders/{customer-panel-order-id}/ `

You can get Customer panel orders using this API Access Point.

| Attribute Name | Data Type | Description
|:---|:---|:---
| id | integer| System generated `id` of Toolbox Genomics API after Order creation.
| created_at | date | The datetime Customer Panel Order is created.
| customer_id | integer| The Customer for the order.  This `id` can be obtained from the Toolbox Genomics API after Customer creation.
| order_items | Object | Orders.


#### Example


##### Request

```
GET /api/v1/customer-panel-orders/101/
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
## Get all Customer Panel Orders
### GET `/api/v1/customer-panel-orders/`

You can get Customer panel orders using this API Access Point.

| Attribute Name | Data Type | Description
|:---|:---|:---
| id | integer| System generated `id` of Toolbox Genomics API after Order creation.
| created_at | date | The datetime Customer Panel Order is created.
| customer_id | integer| The Customer for the order.  This `id` can be obtained from the Toolbox Genomics API after Customer creation.
| order_items | Object | Order items of the order.

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
