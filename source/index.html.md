---
title: Rose Rocket Platform REST API v1.0.0
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2
---

# Rose Rocket Platform REST API v1.0.0

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

The Platform REST API lets you integrate with Rose Rocket applications using simple HTTP methods, in JSON formats, making this an ideal API for developing mobile applications or external clients.

Base URLs:

* <a href="https://platform.roserocket.com/v1">https://platform.roserocket.com/v1</a>


<a href="http://swagger.io/terms/">Terms of service</a>
Email: <a href="mailto:platform@roserocket.com">Support</a> 

# Authentication



- oAuth2 authentication. 

    - Flow: password

    - Token URL = [https://auth.roserocket.com/oauth/token](https://auth.roserocket.com/oauth/token)

|Scope|Scope Description|
|---|---|
|orders|manage orders|
|customers|manage customers|
|legs|manage legs|
|manifests|manage manifests|




* API Key
    - Parameter Name: **Authorization**, in: header. 



# order

Manage orders

## searchOrders

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/orders \
  -H 'Accept: application/json'

```

```http
GET https://platform.roserocket.com/v1/orders HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/orders',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/orders',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://platform.roserocket.com/v1/orders',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://platform.roserocket.com/v1/orders', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/orders");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /orders`

*Search orders*

<h3 id="searchOrders-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
created_start_at|query|string(date-time)|false|Date range (start)
created_end_at|query|string(date-time)|false|Date range (end)
search_term|query|string|false|Search term
external_id|query|string|false|External ID to filter by
in_external_ids|query|array[string]|false|External ID's to filter by
offset|query|integer|false|Pagination offset
limit|query|integer|false|Pagination limit


> Example responses

```json
{
  "orders": [
    {
      "id": "string",
      "sequence_id": 0,
      "external_id": "string",
      "public_id": "string",
      "customer": {
        "id": "string",
        "external_id": "string",
        "short_code": "string"
      },
      "origin": {
        "address_book_id": "string",
        "address_book_external_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0,
        "bus_hours_start_at": "2018-09-19T05:22:07Z",
        "bus_hours_end_at": "2018-09-19T05:22:07Z"
      },
      "destination": {
        "address_book_id": "string",
        "address_book_external_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0,
        "bus_hours_start_at": "2018-09-19T05:22:07Z",
        "bus_hours_end_at": "2018-09-19T05:22:07Z"
      },
      "billing": {
        "address_book_id": "string",
        "address_book_external_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0,
        "bus_hours_start_at": "2018-09-19T05:22:07Z",
        "bus_hours_end_at": "2018-09-19T05:22:07Z"
      },
      "status": "new",
      "billing_option": "prepaid",
      "notes": "string",
      "po_num": "string",
      "tender_num": "string",
      "ref_num": "string",
      "custom_broker": "string",
      "declared_value": 0,
      "declared_value_currency": "cad",
      "pickup_start_at": "2018-09-19T05:22:07Z",
      "pickup_end_at": "2018-09-19T05:22:07Z",
      "pickup_appt_start_at": "2018-09-19T05:22:07Z",
      "pickup_appt_end_at": "2018-09-19T05:22:07Z",
      "delivery_start_at": "2018-09-19T05:22:07Z",
      "delivery_end_at": "2018-09-19T05:22:07Z",
      "delivery_appt_start_at": "2018-09-19T05:22:07Z",
      "delivery_appt_end_at": "2018-09-19T05:22:07Z",
      "dim_type": "ltl",
      "commodities": [
        {
          "id": "string",
          "measurement_unit": "inch",
          "weight_unit": "lb",
          "freight_class": "string",
          "commodity_type": "skid",
          "commodity_type_other": "string",
          "description": "string",
          "feet": 0,
          "volume": 0,
          "length": 0,
          "width": 0,
          "height": 0,
          "weight": 0,
          "nmfc": "string",
          "is_stackable": true,
          "quantity": 0,
          "pieces": 0,
          "sku": "string"
        }
      ],
      "accessorials": [
        "string"
      ]
    }
  ],
  "offset": 0,
  "limit": 0,
  "total": 0
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="searchOrders-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="searchOrders-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
offset|integer|false|No description
limit|integer|false|No description
total|integer|false|No description
orders|[[Order](#schemaorder)]|false|No description
» id|string(uuid)|false|Auto generated system ID
» sequence_id|integer|false|Auto generated sequence ID per customer
» external_id|string|false|External ID for mapping the order to an external system. This field value can be _null_
» public_id|string|false|Auto generated human readable ID
» customer|[OrderCustomer](#schemaordercustomer)|false|Customer
»» id|string(uuid)|false|Auto generated customer id
»» external_id|string|false|Customer external id. This field value can be _null_
»» short_code|string|false|Customer's short code
» origin|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
» destination|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
» billing|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
» status|string|false|Order Status
» billing_option|string|false|Billing Option
» notes|string|false|Notes that will appear on BOL
» po_num|string|false|Purchase order numbers (if multiple use comma separated values)
» tender_num|string|false|Tender number
» ref_num|string|false|Reference number
» custom_broker|string|false|Custom broker information
» declared_value|number(float)|false|Declared value
» declared_value_currency|string|false|Declared value currency
» pickup_start_at|string(date-time)|false|Pickup time range (start)
» pickup_end_at|string(date-time)|false|Pickup time range (end)
» pickup_appt_start_at|string(date-time)|false|Pickup appointment time range (start). This field value can be _null_
» pickup_appt_end_at|string(date-time)|false|Pickup appointment time range (end). This field value can be _null_
» delivery_start_at|string(date-time)|false|Expected delivery time range (start). This field value can be _null_
» delivery_end_at|string(date-time)|false|Expected delivery time range (end). This field value can be _null_
» delivery_appt_start_at|string(date-time)|false|Delivery appointment time range (start). This field value can be _null_
» delivery_appt_end_at|string(date-time)|false|Delivery appointment time range (end). This field value can be _null_
» dim_type|string|false|Dimension type
» commodities|[[Commodity](#schemacommodity)]|false|Commodities items
»» id|string(uuid)|false|Auto generated commodity id
»» measurement_unit|string|false|Measurement unit
»» weight_unit|string|false|Weight unit
»» freight_class|string|false|Freight class
»» commodity_type|string|false|Commodity type
»» commodity_type_other|string|false|If commodity type is set to _other_, then this field must have value
»» description|string|false|Description of the commodity
»» feet|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»» volume|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»» length|number(float)|false|Length of the commodity
»» width|number(float)|false|Width of the commodity
»» height|number(float)|false|Height of the commodity
»» weight|number(float)|false|Weight of the commodity
»» nmfc|string|false|NMFC number
»» is_stackable|boolean|false|Is this commodity can be stacked?
»» quantity|integer|false|Quantity of the commodity
»» pieces|integer|false|Total number of pieces. This field value can be _null_
»» sku|string|false|SKU number
» accessorials|[string(uuid)]|false|No description



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: orders )
</aside>

## createOrder

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/customers/{customerID}/orders \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST https://platform.roserocket.com/v1/customers/{customerID}/orders HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerID}/orders',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "external_id": "string",
  "customer": {},
  "origin": {
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  },
  "destination": {
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  },
  "billing": {
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  },
  "billing_option": "prepaid",
  "notes": "string",
  "po_num": "string",
  "tender_num": "string",
  "ref_num": "string",
  "custom_broker": "string",
  "declared_value": 0,
  "declared_value_currency": "cad",
  "pickup_start_at": "2018-09-19T05:22:07Z",
  "pickup_end_at": "2018-09-19T05:22:07Z",
  "pickup_appt_start_at": "2018-09-19T05:22:07Z",
  "pickup_appt_end_at": "2018-09-19T05:22:07Z",
  "delivery_start_at": "2018-09-19T05:22:07Z",
  "delivery_end_at": "2018-09-19T05:22:07Z",
  "delivery_appt_start_at": "2018-09-19T05:22:07Z",
  "delivery_appt_end_at": "2018-09-19T05:22:07Z",
  "dim_type": "ltl",
  "commodities": [
    {
      "measurement_unit": "inch",
      "weight_unit": "lb",
      "freight_class": "string",
      "commodity_type": "skid",
      "commodity_type_other": "string",
      "description": "string",
      "feet": 0,
      "volume": 0,
      "length": 0,
      "width": 0,
      "height": 0,
      "weight": 0,
      "nmfc": "string",
      "is_stackable": true,
      "quantity": 0,
      "pieces": 0,
      "sku": "string"
    }
  ],
  "accessorials": [
    "string"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers/{customerID}/orders',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'https://platform.roserocket.com/v1/customers/{customerID}/orders',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('https://platform.roserocket.com/v1/customers/{customerID}/orders', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerID}/orders");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /customers/{customerID}/orders`

*Create new customer's order*

> Body parameter

```json
{
  "external_id": "string",
  "customer": {},
  "origin": {
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  },
  "destination": {
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  },
  "billing": {
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  },
  "billing_option": "prepaid",
  "notes": "string",
  "po_num": "string",
  "tender_num": "string",
  "ref_num": "string",
  "custom_broker": "string",
  "declared_value": 0,
  "declared_value_currency": "cad",
  "pickup_start_at": "2018-09-19T05:22:07Z",
  "pickup_end_at": "2018-09-19T05:22:07Z",
  "pickup_appt_start_at": "2018-09-19T05:22:07Z",
  "pickup_appt_end_at": "2018-09-19T05:22:07Z",
  "delivery_start_at": "2018-09-19T05:22:07Z",
  "delivery_end_at": "2018-09-19T05:22:07Z",
  "delivery_appt_start_at": "2018-09-19T05:22:07Z",
  "delivery_appt_end_at": "2018-09-19T05:22:07Z",
  "dim_type": "ltl",
  "commodities": [
    {
      "measurement_unit": "inch",
      "weight_unit": "lb",
      "freight_class": "string",
      "commodity_type": "skid",
      "commodity_type_other": "string",
      "description": "string",
      "feet": 0,
      "volume": 0,
      "length": 0,
      "width": 0,
      "height": 0,
      "weight": 0,
      "nmfc": "string",
      "is_stackable": true,
      "quantity": 0,
      "pieces": 0,
      "sku": "string"
    }
  ],
  "accessorials": [
    "string"
  ]
}
```
<h3 id="createOrder-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.
body|body|[Order](#schemaorder)|true|Order object
» id|body|string(uuid)|false|Auto generated system ID
» sequence_id|body|integer|false|Auto generated sequence ID per customer
» external_id|body|string|false|External ID for mapping the order to an external system. This field value can be _null_
» public_id|body|string|false|Auto generated human readable ID
» customer|body|[OrderCustomer](#schemaordercustomer)|false|Customer
»» id|body|string(uuid)|false|Auto generated customer id
»» external_id|body|string|false|Customer external id. This field value can be _null_
»» short_code|body|string|false|Customer's short code
» origin|body|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|body|string|false|Organization name
»» contact_name|body|string|false|Contact name
»» address_1|body|string|false|Address line 1
»» address_2|body|string|false|Address line 2
»» suite|body|string|false|Suite number
»» city|body|string|false|City
»» state|body|string|false|State / Province
»» country|body|string|false|Country (2 letter ISO)
»» postal|body|string|false|Postal / Zip code
»» phone|body|string|false|Phone number
»» phone_ext|body|string|false|Phone extension
»» email|body|string|false|Email
»» fax|body|string|false|Fax
»» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|body|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|body|string(date-time)|false|Business hours range (end). This field value can be _null_
» destination|body|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|body|string|false|Organization name
»» contact_name|body|string|false|Contact name
»» address_1|body|string|false|Address line 1
»» address_2|body|string|false|Address line 2
»» suite|body|string|false|Suite number
»» city|body|string|false|City
»» state|body|string|false|State / Province
»» country|body|string|false|Country (2 letter ISO)
»» postal|body|string|false|Postal / Zip code
»» phone|body|string|false|Phone number
»» phone_ext|body|string|false|Phone extension
»» email|body|string|false|Email
»» fax|body|string|false|Fax
»» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|body|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|body|string(date-time)|false|Business hours range (end). This field value can be _null_
» billing|body|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|body|string|false|Organization name
»» contact_name|body|string|false|Contact name
»» address_1|body|string|false|Address line 1
»» address_2|body|string|false|Address line 2
»» suite|body|string|false|Suite number
»» city|body|string|false|City
»» state|body|string|false|State / Province
»» country|body|string|false|Country (2 letter ISO)
»» postal|body|string|false|Postal / Zip code
»» phone|body|string|false|Phone number
»» phone_ext|body|string|false|Phone extension
»» email|body|string|false|Email
»» fax|body|string|false|Fax
»» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|body|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|body|string(date-time)|false|Business hours range (end). This field value can be _null_
» status|body|string|false|Order Status
» billing_option|body|string|false|Billing Option
» notes|body|string|false|Notes that will appear on BOL
» po_num|body|string|false|Purchase order numbers (if multiple use comma separated values)
» tender_num|body|string|false|Tender number
» ref_num|body|string|false|Reference number
» custom_broker|body|string|false|Custom broker information
» declared_value|body|number(float)|false|Declared value
» declared_value_currency|body|string|false|Declared value currency
» pickup_start_at|body|string(date-time)|false|Pickup time range (start)
» pickup_end_at|body|string(date-time)|false|Pickup time range (end)
» pickup_appt_start_at|body|string(date-time)|false|Pickup appointment time range (start). This field value can be _null_
» pickup_appt_end_at|body|string(date-time)|false|Pickup appointment time range (end). This field value can be _null_
» delivery_start_at|body|string(date-time)|false|Expected delivery time range (start). This field value can be _null_
» delivery_end_at|body|string(date-time)|false|Expected delivery time range (end). This field value can be _null_
» delivery_appt_start_at|body|string(date-time)|false|Delivery appointment time range (start). This field value can be _null_
» delivery_appt_end_at|body|string(date-time)|false|Delivery appointment time range (end). This field value can be _null_
» dim_type|body|string|false|Dimension type
» commodities|body|[[Commodity](#schemacommodity)]|false|Commodities items
»» id|body|string(uuid)|false|Auto generated commodity id
»» measurement_unit|body|string|false|Measurement unit
»» weight_unit|body|string|false|Weight unit
»» freight_class|body|string|false|Freight class
»» commodity_type|body|string|false|Commodity type
»» commodity_type_other|body|string|false|If commodity type is set to _other_, then this field must have value
»» description|body|string|false|Description of the commodity
»» feet|body|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»» volume|body|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»» length|body|number(float)|false|Length of the commodity
»» width|body|number(float)|false|Width of the commodity
»» height|body|number(float)|false|Height of the commodity
»» weight|body|number(float)|false|Weight of the commodity
»» nmfc|body|string|false|NMFC number
»» is_stackable|body|boolean|false|Is this commodity can be stacked?
»» quantity|body|integer|false|Quantity of the commodity
»» pieces|body|integer|false|Total number of pieces. This field value can be _null_
»» sku|body|string|false|SKU number
» accessorials|body|[string(uuid)]|false|No description


#### Enumerated Values

|Parameter|Value|
|---|---|
» status|new|
» status|saved|
» status|cancelled|
» status|quoting|
» status|quoted|
» status|no-quote|
» status|spot-quote-requested|
» status|pending-dispatch|
» status|dispatched|
» status|in-transit|
» status|delivered|
» status|archived|
» status|invoice-created|
» status|invoice-sent|
» status|invoice-paid|
» status|claim|
» status|draft-quick-quote|
» status|quick-quoting|
» status|quick-quoted|
» status|no-quick-quote|
» status|spot-qq-requested|
» status|pickup-request|
» status|rejected|
» billing_option|prepaid|
» billing_option|collect|
» billing_option|thirdparty|
» declared_value_currency|cad|
» declared_value_currency|usd|
» dim_type|ltl|
» dim_type|ftl|
» dim_type|volume|
»» measurement_unit|inch|
»» measurement_unit|cm|
»» weight_unit|lb|
»» weight_unit|kg|
»» commodity_type|skid|
»» commodity_type|other|

> Example responses

```json
{
  "customer": {
    "id": "string",
    "sequence_id": 0,
    "external_id": "string",
    "public_id": "string",
    "customer": {
      "id": "string",
      "external_id": "string",
      "short_code": "string"
    },
    "origin": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "destination": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "billing": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "status": "new",
    "billing_option": "prepaid",
    "notes": "string",
    "po_num": "string",
    "tender_num": "string",
    "ref_num": "string",
    "custom_broker": "string",
    "declared_value": 0,
    "declared_value_currency": "cad",
    "pickup_start_at": "2018-09-19T05:22:07Z",
    "pickup_end_at": "2018-09-19T05:22:07Z",
    "pickup_appt_start_at": "2018-09-19T05:22:07Z",
    "pickup_appt_end_at": "2018-09-19T05:22:07Z",
    "delivery_start_at": "2018-09-19T05:22:07Z",
    "delivery_end_at": "2018-09-19T05:22:07Z",
    "delivery_appt_start_at": "2018-09-19T05:22:07Z",
    "delivery_appt_end_at": "2018-09-19T05:22:07Z",
    "dim_type": "ltl",
    "commodities": [
      {
        "id": "string",
        "measurement_unit": "inch",
        "weight_unit": "lb",
        "freight_class": "string",
        "commodity_type": "skid",
        "commodity_type_other": "string",
        "description": "string",
        "feet": 0,
        "volume": 0,
        "length": 0,
        "width": 0,
        "height": 0,
        "weight": 0,
        "nmfc": "string",
        "is_stackable": true,
        "quantity": 0,
        "pieces": 0,
        "sku": "string"
      }
    ],
    "accessorials": [
      "string"
    ]
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="createOrder-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="createOrder-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
customer|[Order](#schemaorder)|false|Customer's order
» id|string(uuid)|false|Auto generated system ID
» sequence_id|integer|false|Auto generated sequence ID per customer
» external_id|string|false|External ID for mapping the order to an external system. This field value can be _null_
» public_id|string|false|Auto generated human readable ID
» customer|[OrderCustomer](#schemaordercustomer)|false|Customer
»» id|string(uuid)|false|Auto generated customer id
»» external_id|string|false|Customer external id. This field value can be _null_
»» short_code|string|false|Customer's short code
» origin|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
» destination|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
» billing|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
» status|string|false|Order Status
» billing_option|string|false|Billing Option
» notes|string|false|Notes that will appear on BOL
» po_num|string|false|Purchase order numbers (if multiple use comma separated values)
» tender_num|string|false|Tender number
» ref_num|string|false|Reference number
» custom_broker|string|false|Custom broker information
» declared_value|number(float)|false|Declared value
» declared_value_currency|string|false|Declared value currency
» pickup_start_at|string(date-time)|false|Pickup time range (start)
» pickup_end_at|string(date-time)|false|Pickup time range (end)
» pickup_appt_start_at|string(date-time)|false|Pickup appointment time range (start). This field value can be _null_
» pickup_appt_end_at|string(date-time)|false|Pickup appointment time range (end). This field value can be _null_
» delivery_start_at|string(date-time)|false|Expected delivery time range (start). This field value can be _null_
» delivery_end_at|string(date-time)|false|Expected delivery time range (end). This field value can be _null_
» delivery_appt_start_at|string(date-time)|false|Delivery appointment time range (start). This field value can be _null_
» delivery_appt_end_at|string(date-time)|false|Delivery appointment time range (end). This field value can be _null_
» dim_type|string|false|Dimension type
» commodities|[[Commodity](#schemacommodity)]|false|Commodities items
»» id|string(uuid)|false|Auto generated commodity id
»» measurement_unit|string|false|Measurement unit
»» weight_unit|string|false|Weight unit
»» freight_class|string|false|Freight class
»» commodity_type|string|false|Commodity type
»» commodity_type_other|string|false|If commodity type is set to _other_, then this field must have value
»» description|string|false|Description of the commodity
»» feet|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»» volume|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»» length|number(float)|false|Length of the commodity
»» width|number(float)|false|Width of the commodity
»» height|number(float)|false|Height of the commodity
»» weight|number(float)|false|Weight of the commodity
»» nmfc|string|false|NMFC number
»» is_stackable|boolean|false|Is this commodity can be stacked?
»» quantity|integer|false|Quantity of the commodity
»» pieces|integer|false|Total number of pieces. This field value can be _null_
»» sku|string|false|SKU number
» accessorials|[string(uuid)]|false|No description



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: orders )
</aside>

## bulkCreateOrder

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/customers/{customerID}/orders/bulk_create \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST https://platform.roserocket.com/v1/customers/{customerID}/orders/bulk_create HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerID}/orders/bulk_create',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "orders": [
    {
      "external_id": "string",
      "customer": {},
      "origin": {
        "address_book_external_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0,
        "bus_hours_start_at": "2018-09-19T05:22:07Z",
        "bus_hours_end_at": "2018-09-19T05:22:07Z"
      },
      "destination": {
        "address_book_external_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0,
        "bus_hours_start_at": "2018-09-19T05:22:07Z",
        "bus_hours_end_at": "2018-09-19T05:22:07Z"
      },
      "billing": {
        "address_book_external_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0,
        "bus_hours_start_at": "2018-09-19T05:22:07Z",
        "bus_hours_end_at": "2018-09-19T05:22:07Z"
      },
      "billing_option": "prepaid",
      "notes": "string",
      "po_num": "string",
      "tender_num": "string",
      "ref_num": "string",
      "custom_broker": "string",
      "declared_value": 0,
      "declared_value_currency": "cad",
      "pickup_start_at": "2018-09-19T05:22:07Z",
      "pickup_end_at": "2018-09-19T05:22:07Z",
      "pickup_appt_start_at": "2018-09-19T05:22:07Z",
      "pickup_appt_end_at": "2018-09-19T05:22:07Z",
      "delivery_start_at": "2018-09-19T05:22:07Z",
      "delivery_end_at": "2018-09-19T05:22:07Z",
      "delivery_appt_start_at": "2018-09-19T05:22:07Z",
      "delivery_appt_end_at": "2018-09-19T05:22:07Z",
      "dim_type": "ltl",
      "commodities": [
        {
          "measurement_unit": "inch",
          "weight_unit": "lb",
          "freight_class": "string",
          "commodity_type": "skid",
          "commodity_type_other": "string",
          "description": "string",
          "feet": 0,
          "volume": 0,
          "length": 0,
          "width": 0,
          "height": 0,
          "weight": 0,
          "nmfc": "string",
          "is_stackable": true,
          "quantity": 0,
          "pieces": 0,
          "sku": "string"
        }
      ],
      "accessorials": [
        "string"
      ]
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers/{customerID}/orders/bulk_create',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'https://platform.roserocket.com/v1/customers/{customerID}/orders/bulk_create',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('https://platform.roserocket.com/v1/customers/{customerID}/orders/bulk_create', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerID}/orders/bulk_create");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /customers/{customerID}/orders/bulk_create`

*Bulk create orders for a given customer.*

> Body parameter

```json
{
  "orders": [
    {
      "external_id": "string",
      "customer": {},
      "origin": {
        "address_book_external_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0,
        "bus_hours_start_at": "2018-09-19T05:22:07Z",
        "bus_hours_end_at": "2018-09-19T05:22:07Z"
      },
      "destination": {
        "address_book_external_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0,
        "bus_hours_start_at": "2018-09-19T05:22:07Z",
        "bus_hours_end_at": "2018-09-19T05:22:07Z"
      },
      "billing": {
        "address_book_external_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0,
        "bus_hours_start_at": "2018-09-19T05:22:07Z",
        "bus_hours_end_at": "2018-09-19T05:22:07Z"
      },
      "billing_option": "prepaid",
      "notes": "string",
      "po_num": "string",
      "tender_num": "string",
      "ref_num": "string",
      "custom_broker": "string",
      "declared_value": 0,
      "declared_value_currency": "cad",
      "pickup_start_at": "2018-09-19T05:22:07Z",
      "pickup_end_at": "2018-09-19T05:22:07Z",
      "pickup_appt_start_at": "2018-09-19T05:22:07Z",
      "pickup_appt_end_at": "2018-09-19T05:22:07Z",
      "delivery_start_at": "2018-09-19T05:22:07Z",
      "delivery_end_at": "2018-09-19T05:22:07Z",
      "delivery_appt_start_at": "2018-09-19T05:22:07Z",
      "delivery_appt_end_at": "2018-09-19T05:22:07Z",
      "dim_type": "ltl",
      "commodities": [
        {
          "measurement_unit": "inch",
          "weight_unit": "lb",
          "freight_class": "string",
          "commodity_type": "skid",
          "commodity_type_other": "string",
          "description": "string",
          "feet": 0,
          "volume": 0,
          "length": 0,
          "width": 0,
          "height": 0,
          "weight": 0,
          "nmfc": "string",
          "is_stackable": true,
          "quantity": 0,
          "pieces": 0,
          "sku": "string"
        }
      ],
      "accessorials": [
        "string"
      ]
    }
  ]
}
```
<h3 id="bulkCreateOrder-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.
body|body|[bulkCreateOrderBody](#schema+bulkcreateorderbody)|true|Bulk create request object
» orders|body|[[Order](#schemaorder)]|false|No description


> Example responses

```json
{
  "job_id": "string",
  "message": "string"
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="bulkCreateOrder-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[BulkOrderCreateResponse](#schemabulkordercreateresponse)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: orders )
</aside>

## bulkCreateOrderCustomerAgnostic

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/orders/bulk_create \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST https://platform.roserocket.com/v1/orders/bulk_create HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/orders/bulk_create',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "orders": [
    {
      "order": {
        "external_id": "string",
        "customer": {},
        "origin": {
          "address_book_external_id": "string",
          "org_name": "string",
          "contact_name": "string",
          "address_1": "string",
          "address_2": "string",
          "suite": "string",
          "city": "string",
          "state": "string",
          "country": "string",
          "postal": "string",
          "phone": "string",
          "phone_ext": "string",
          "email": "string",
          "fax": "string",
          "latitude": 0,
          "longitude": 0,
          "bus_hours_start_at": "2018-09-19T05:22:07Z",
          "bus_hours_end_at": "2018-09-19T05:22:07Z"
        },
        "destination": {
          "address_book_external_id": "string",
          "org_name": "string",
          "contact_name": "string",
          "address_1": "string",
          "address_2": "string",
          "suite": "string",
          "city": "string",
          "state": "string",
          "country": "string",
          "postal": "string",
          "phone": "string",
          "phone_ext": "string",
          "email": "string",
          "fax": "string",
          "latitude": 0,
          "longitude": 0,
          "bus_hours_start_at": "2018-09-19T05:22:07Z",
          "bus_hours_end_at": "2018-09-19T05:22:07Z"
        },
        "billing": {
          "address_book_external_id": "string",
          "org_name": "string",
          "contact_name": "string",
          "address_1": "string",
          "address_2": "string",
          "suite": "string",
          "city": "string",
          "state": "string",
          "country": "string",
          "postal": "string",
          "phone": "string",
          "phone_ext": "string",
          "email": "string",
          "fax": "string",
          "latitude": 0,
          "longitude": 0,
          "bus_hours_start_at": "2018-09-19T05:22:07Z",
          "bus_hours_end_at": "2018-09-19T05:22:07Z"
        },
        "billing_option": "prepaid",
        "notes": "string",
        "po_num": "string",
        "tender_num": "string",
        "ref_num": "string",
        "custom_broker": "string",
        "declared_value": 0,
        "declared_value_currency": "cad",
        "pickup_start_at": "2018-09-19T05:22:07Z",
        "pickup_end_at": "2018-09-19T05:22:07Z",
        "pickup_appt_start_at": "2018-09-19T05:22:07Z",
        "pickup_appt_end_at": "2018-09-19T05:22:07Z",
        "delivery_start_at": "2018-09-19T05:22:07Z",
        "delivery_end_at": "2018-09-19T05:22:07Z",
        "delivery_appt_start_at": "2018-09-19T05:22:07Z",
        "delivery_appt_end_at": "2018-09-19T05:22:07Z",
        "dim_type": "ltl",
        "commodities": [
          {
            "measurement_unit": "inch",
            "weight_unit": "lb",
            "freight_class": "string",
            "commodity_type": "skid",
            "commodity_type_other": "string",
            "description": "string",
            "feet": 0,
            "volume": 0,
            "length": 0,
            "width": 0,
            "height": 0,
            "weight": 0,
            "nmfc": "string",
            "is_stackable": true,
            "quantity": 0,
            "pieces": 0,
            "sku": "string"
          }
        ],
        "accessorials": [
          "string"
        ]
      }
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/orders/bulk_create',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'https://platform.roserocket.com/v1/orders/bulk_create',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('https://platform.roserocket.com/v1/orders/bulk_create', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/orders/bulk_create");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /orders/bulk_create`

*Bulk create orders for several customers.*

> Body parameter

```json
{
  "orders": [
    {
      "order": {
        "external_id": "string",
        "customer": {},
        "origin": {
          "address_book_external_id": "string",
          "org_name": "string",
          "contact_name": "string",
          "address_1": "string",
          "address_2": "string",
          "suite": "string",
          "city": "string",
          "state": "string",
          "country": "string",
          "postal": "string",
          "phone": "string",
          "phone_ext": "string",
          "email": "string",
          "fax": "string",
          "latitude": 0,
          "longitude": 0,
          "bus_hours_start_at": "2018-09-19T05:22:07Z",
          "bus_hours_end_at": "2018-09-19T05:22:07Z"
        },
        "destination": {
          "address_book_external_id": "string",
          "org_name": "string",
          "contact_name": "string",
          "address_1": "string",
          "address_2": "string",
          "suite": "string",
          "city": "string",
          "state": "string",
          "country": "string",
          "postal": "string",
          "phone": "string",
          "phone_ext": "string",
          "email": "string",
          "fax": "string",
          "latitude": 0,
          "longitude": 0,
          "bus_hours_start_at": "2018-09-19T05:22:07Z",
          "bus_hours_end_at": "2018-09-19T05:22:07Z"
        },
        "billing": {
          "address_book_external_id": "string",
          "org_name": "string",
          "contact_name": "string",
          "address_1": "string",
          "address_2": "string",
          "suite": "string",
          "city": "string",
          "state": "string",
          "country": "string",
          "postal": "string",
          "phone": "string",
          "phone_ext": "string",
          "email": "string",
          "fax": "string",
          "latitude": 0,
          "longitude": 0,
          "bus_hours_start_at": "2018-09-19T05:22:07Z",
          "bus_hours_end_at": "2018-09-19T05:22:07Z"
        },
        "billing_option": "prepaid",
        "notes": "string",
        "po_num": "string",
        "tender_num": "string",
        "ref_num": "string",
        "custom_broker": "string",
        "declared_value": 0,
        "declared_value_currency": "cad",
        "pickup_start_at": "2018-09-19T05:22:07Z",
        "pickup_end_at": "2018-09-19T05:22:07Z",
        "pickup_appt_start_at": "2018-09-19T05:22:07Z",
        "pickup_appt_end_at": "2018-09-19T05:22:07Z",
        "delivery_start_at": "2018-09-19T05:22:07Z",
        "delivery_end_at": "2018-09-19T05:22:07Z",
        "delivery_appt_start_at": "2018-09-19T05:22:07Z",
        "delivery_appt_end_at": "2018-09-19T05:22:07Z",
        "dim_type": "ltl",
        "commodities": [
          {
            "measurement_unit": "inch",
            "weight_unit": "lb",
            "freight_class": "string",
            "commodity_type": "skid",
            "commodity_type_other": "string",
            "description": "string",
            "feet": 0,
            "volume": 0,
            "length": 0,
            "width": 0,
            "height": 0,
            "weight": 0,
            "nmfc": "string",
            "is_stackable": true,
            "quantity": 0,
            "pieces": 0,
            "sku": "string"
          }
        ],
        "accessorials": [
          "string"
        ]
      }
    }
  ]
}
```
<h3 id="bulkCreateOrderCustomerAgnostic-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
body|body|[bulkCreateOrderCustomerAgnosticBody](#schema+bulkcreateordercustomeragnosticbody)|true|Bulk create request object
» orders|body|[object]|false|No description
»» order|body|[Order](#schemaorder)|false|No description


> Example responses

```json
{
  "job_id": "string",
  "message": "string"
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="bulkCreateOrderCustomerAgnostic-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[BulkOrderCreateResponse](#schemabulkordercreateresponse)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: orders )
</aside>

## bulkCreateBookedOrder

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/customers/{customerID}/bulk_create_booked_order \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST https://platform.roserocket.com/v1/customers/{customerID}/bulk_create_booked_order HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerID}/bulk_create_booked_order',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "orders": [
    {
      "external_id": "string",
      "customer": {},
      "origin": {
        "address_book_external_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0,
        "bus_hours_start_at": "2018-09-19T05:22:07Z",
        "bus_hours_end_at": "2018-09-19T05:22:07Z"
      },
      "destination": {
        "address_book_external_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0,
        "bus_hours_start_at": "2018-09-19T05:22:07Z",
        "bus_hours_end_at": "2018-09-19T05:22:07Z"
      },
      "billing": {
        "address_book_external_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0,
        "bus_hours_start_at": "2018-09-19T05:22:07Z",
        "bus_hours_end_at": "2018-09-19T05:22:07Z"
      },
      "billing_option": "prepaid",
      "notes": "string",
      "po_num": "string",
      "tender_num": "string",
      "ref_num": "string",
      "custom_broker": "string",
      "declared_value": 0,
      "declared_value_currency": "cad",
      "pickup_start_at": "2018-09-19T05:22:07Z",
      "pickup_end_at": "2018-09-19T05:22:07Z",
      "pickup_appt_start_at": "2018-09-19T05:22:07Z",
      "pickup_appt_end_at": "2018-09-19T05:22:07Z",
      "delivery_start_at": "2018-09-19T05:22:07Z",
      "delivery_end_at": "2018-09-19T05:22:07Z",
      "delivery_appt_start_at": "2018-09-19T05:22:07Z",
      "delivery_appt_end_at": "2018-09-19T05:22:07Z",
      "dim_type": "ltl",
      "commodities": [
        {
          "measurement_unit": "inch",
          "weight_unit": "lb",
          "freight_class": "string",
          "commodity_type": "skid",
          "commodity_type_other": "string",
          "description": "string",
          "feet": 0,
          "volume": 0,
          "length": 0,
          "width": 0,
          "height": 0,
          "weight": 0,
          "nmfc": "string",
          "is_stackable": true,
          "quantity": 0,
          "pieces": 0,
          "sku": "string"
        }
      ],
      "accessorials": [
        "string"
      ]
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers/{customerID}/bulk_create_booked_order',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'https://platform.roserocket.com/v1/customers/{customerID}/bulk_create_booked_order',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('https://platform.roserocket.com/v1/customers/{customerID}/bulk_create_booked_order', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerID}/bulk_create_booked_order");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /customers/{customerID}/bulk_create_booked_order`

*Bulk create booked orders for a given customer.*

> Body parameter

```json
{
  "orders": [
    {
      "external_id": "string",
      "customer": {},
      "origin": {
        "address_book_external_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0,
        "bus_hours_start_at": "2018-09-19T05:22:07Z",
        "bus_hours_end_at": "2018-09-19T05:22:07Z"
      },
      "destination": {
        "address_book_external_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0,
        "bus_hours_start_at": "2018-09-19T05:22:07Z",
        "bus_hours_end_at": "2018-09-19T05:22:07Z"
      },
      "billing": {
        "address_book_external_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0,
        "bus_hours_start_at": "2018-09-19T05:22:07Z",
        "bus_hours_end_at": "2018-09-19T05:22:07Z"
      },
      "billing_option": "prepaid",
      "notes": "string",
      "po_num": "string",
      "tender_num": "string",
      "ref_num": "string",
      "custom_broker": "string",
      "declared_value": 0,
      "declared_value_currency": "cad",
      "pickup_start_at": "2018-09-19T05:22:07Z",
      "pickup_end_at": "2018-09-19T05:22:07Z",
      "pickup_appt_start_at": "2018-09-19T05:22:07Z",
      "pickup_appt_end_at": "2018-09-19T05:22:07Z",
      "delivery_start_at": "2018-09-19T05:22:07Z",
      "delivery_end_at": "2018-09-19T05:22:07Z",
      "delivery_appt_start_at": "2018-09-19T05:22:07Z",
      "delivery_appt_end_at": "2018-09-19T05:22:07Z",
      "dim_type": "ltl",
      "commodities": [
        {
          "measurement_unit": "inch",
          "weight_unit": "lb",
          "freight_class": "string",
          "commodity_type": "skid",
          "commodity_type_other": "string",
          "description": "string",
          "feet": 0,
          "volume": 0,
          "length": 0,
          "width": 0,
          "height": 0,
          "weight": 0,
          "nmfc": "string",
          "is_stackable": true,
          "quantity": 0,
          "pieces": 0,
          "sku": "string"
        }
      ],
      "accessorials": [
        "string"
      ]
    }
  ]
}
```
<h3 id="bulkCreateBookedOrder-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.
body|body|[bulkCreateOrderBody](#schema+bulkcreateorderbody)|true|Bulk create request object
» orders|body|[[Order](#schemaorder)]|false|No description
»» id|body|string(uuid)|false|Auto generated system ID
»» sequence_id|body|integer|false|Auto generated sequence ID per customer
»» external_id|body|string|false|External ID for mapping the order to an external system. This field value can be _null_
»» public_id|body|string|false|Auto generated human readable ID
»» customer|body|[OrderCustomer](#schemaordercustomer)|false|Customer
»»» id|body|string(uuid)|false|Auto generated customer id
»»» external_id|body|string|false|Customer external id. This field value can be _null_
»»» short_code|body|string|false|Customer's short code
»» origin|body|[OrderAddress](#schemaorderaddress)|true|Order address
»»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»»» org_name|body|string|false|Organization name
»»» contact_name|body|string|false|Contact name
»»» address_1|body|string|false|Address line 1
»»» address_2|body|string|false|Address line 2
»»» suite|body|string|false|Suite number
»»» city|body|string|false|City
»»» state|body|string|false|State / Province
»»» country|body|string|false|Country (2 letter ISO)
»»» postal|body|string|false|Postal / Zip code
»»» phone|body|string|false|Phone number
»»» phone_ext|body|string|false|Phone extension
»»» email|body|string|false|Email
»»» fax|body|string|false|Fax
»»» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
»»» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_
»»» bus_hours_start_at|body|string(date-time)|false|Business hours range (start). This field value can be _null_
»»» bus_hours_end_at|body|string(date-time)|false|Business hours range (end). This field value can be _null_
»» destination|body|[OrderAddress](#schemaorderaddress)|true|Order address
»»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»»» org_name|body|string|false|Organization name
»»» contact_name|body|string|false|Contact name
»»» address_1|body|string|false|Address line 1
»»» address_2|body|string|false|Address line 2
»»» suite|body|string|false|Suite number
»»» city|body|string|false|City
»»» state|body|string|false|State / Province
»»» country|body|string|false|Country (2 letter ISO)
»»» postal|body|string|false|Postal / Zip code
»»» phone|body|string|false|Phone number
»»» phone_ext|body|string|false|Phone extension
»»» email|body|string|false|Email
»»» fax|body|string|false|Fax
»»» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
»»» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_
»»» bus_hours_start_at|body|string(date-time)|false|Business hours range (start). This field value can be _null_
»»» bus_hours_end_at|body|string(date-time)|false|Business hours range (end). This field value can be _null_
»» billing|body|[OrderAddress](#schemaorderaddress)|true|Order address
»»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»»» org_name|body|string|false|Organization name
»»» contact_name|body|string|false|Contact name
»»» address_1|body|string|false|Address line 1
»»» address_2|body|string|false|Address line 2
»»» suite|body|string|false|Suite number
»»» city|body|string|false|City
»»» state|body|string|false|State / Province
»»» country|body|string|false|Country (2 letter ISO)
»»» postal|body|string|false|Postal / Zip code
»»» phone|body|string|false|Phone number
»»» phone_ext|body|string|false|Phone extension
»»» email|body|string|false|Email
»»» fax|body|string|false|Fax
»»» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
»»» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_
»»» bus_hours_start_at|body|string(date-time)|false|Business hours range (start). This field value can be _null_
»»» bus_hours_end_at|body|string(date-time)|false|Business hours range (end). This field value can be _null_
»» status|body|string|false|Order Status
»» billing_option|body|string|false|Billing Option
»» notes|body|string|false|Notes that will appear on BOL
»» po_num|body|string|false|Purchase order numbers (if multiple use comma separated values)
»» tender_num|body|string|false|Tender number
»» ref_num|body|string|false|Reference number
»» custom_broker|body|string|false|Custom broker information
»» declared_value|body|number(float)|false|Declared value
»» declared_value_currency|body|string|false|Declared value currency
»» pickup_start_at|body|string(date-time)|false|Pickup time range (start)
»» pickup_end_at|body|string(date-time)|false|Pickup time range (end)
»» pickup_appt_start_at|body|string(date-time)|false|Pickup appointment time range (start). This field value can be _null_
»» pickup_appt_end_at|body|string(date-time)|false|Pickup appointment time range (end). This field value can be _null_
»» delivery_start_at|body|string(date-time)|false|Expected delivery time range (start). This field value can be _null_
»» delivery_end_at|body|string(date-time)|false|Expected delivery time range (end). This field value can be _null_
»» delivery_appt_start_at|body|string(date-time)|false|Delivery appointment time range (start). This field value can be _null_
»» delivery_appt_end_at|body|string(date-time)|false|Delivery appointment time range (end). This field value can be _null_
»» dim_type|body|string|false|Dimension type
»» commodities|body|[[Commodity](#schemacommodity)]|false|Commodities items
»»» id|body|string(uuid)|false|Auto generated commodity id
»»» measurement_unit|body|string|false|Measurement unit
»»» weight_unit|body|string|false|Weight unit
»»» freight_class|body|string|false|Freight class
»»» commodity_type|body|string|false|Commodity type
»»» commodity_type_other|body|string|false|If commodity type is set to _other_, then this field must have value
»»» description|body|string|false|Description of the commodity
»»» feet|body|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»»» volume|body|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»»» length|body|number(float)|false|Length of the commodity
»»» width|body|number(float)|false|Width of the commodity
»»» height|body|number(float)|false|Height of the commodity
»»» weight|body|number(float)|false|Weight of the commodity
»»» nmfc|body|string|false|NMFC number
»»» is_stackable|body|boolean|false|Is this commodity can be stacked?
»»» quantity|body|integer|false|Quantity of the commodity
»»» pieces|body|integer|false|Total number of pieces. This field value can be _null_
»»» sku|body|string|false|SKU number
»» accessorials|body|[string(uuid)]|false|No description


#### Enumerated Values

|Parameter|Value|
|---|---|
»» status|new|
»» status|saved|
»» status|cancelled|
»» status|quoting|
»» status|quoted|
»» status|no-quote|
»» status|spot-quote-requested|
»» status|pending-dispatch|
»» status|dispatched|
»» status|in-transit|
»» status|delivered|
»» status|archived|
»» status|invoice-created|
»» status|invoice-sent|
»» status|invoice-paid|
»» status|claim|
»» status|draft-quick-quote|
»» status|quick-quoting|
»» status|quick-quoted|
»» status|no-quick-quote|
»» status|spot-qq-requested|
»» status|pickup-request|
»» status|rejected|
»» billing_option|prepaid|
»» billing_option|collect|
»» billing_option|thirdparty|
»» declared_value_currency|cad|
»» declared_value_currency|usd|
»» dim_type|ltl|
»» dim_type|ftl|
»» dim_type|volume|
»»» measurement_unit|inch|
»»» measurement_unit|cm|
»»» weight_unit|lb|
»»» weight_unit|kg|
»»» commodity_type|skid|
»»» commodity_type|other|

> Example responses

```json
{
  "job_id": "string",
  "message": "string"
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="bulkCreateBookedOrder-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[BulkOrderCreateResponse](#schemabulkordercreateresponse)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: orders )
</aside>

## bulkCreateBookedOrderCustomerAgnostic

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/orders/bulk_create_booked_order \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST https://platform.roserocket.com/v1/orders/bulk_create_booked_order HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/orders/bulk_create_booked_order',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "orders": [
    {
      "order": {
        "external_id": "string",
        "customer": {},
        "origin": {
          "address_book_external_id": "string",
          "org_name": "string",
          "contact_name": "string",
          "address_1": "string",
          "address_2": "string",
          "suite": "string",
          "city": "string",
          "state": "string",
          "country": "string",
          "postal": "string",
          "phone": "string",
          "phone_ext": "string",
          "email": "string",
          "fax": "string",
          "latitude": 0,
          "longitude": 0,
          "bus_hours_start_at": "2018-09-19T05:22:07Z",
          "bus_hours_end_at": "2018-09-19T05:22:07Z"
        },
        "destination": {
          "address_book_external_id": "string",
          "org_name": "string",
          "contact_name": "string",
          "address_1": "string",
          "address_2": "string",
          "suite": "string",
          "city": "string",
          "state": "string",
          "country": "string",
          "postal": "string",
          "phone": "string",
          "phone_ext": "string",
          "email": "string",
          "fax": "string",
          "latitude": 0,
          "longitude": 0,
          "bus_hours_start_at": "2018-09-19T05:22:07Z",
          "bus_hours_end_at": "2018-09-19T05:22:07Z"
        },
        "billing": {
          "address_book_external_id": "string",
          "org_name": "string",
          "contact_name": "string",
          "address_1": "string",
          "address_2": "string",
          "suite": "string",
          "city": "string",
          "state": "string",
          "country": "string",
          "postal": "string",
          "phone": "string",
          "phone_ext": "string",
          "email": "string",
          "fax": "string",
          "latitude": 0,
          "longitude": 0,
          "bus_hours_start_at": "2018-09-19T05:22:07Z",
          "bus_hours_end_at": "2018-09-19T05:22:07Z"
        },
        "billing_option": "prepaid",
        "notes": "string",
        "po_num": "string",
        "tender_num": "string",
        "ref_num": "string",
        "custom_broker": "string",
        "declared_value": 0,
        "declared_value_currency": "cad",
        "pickup_start_at": "2018-09-19T05:22:07Z",
        "pickup_end_at": "2018-09-19T05:22:07Z",
        "pickup_appt_start_at": "2018-09-19T05:22:07Z",
        "pickup_appt_end_at": "2018-09-19T05:22:07Z",
        "delivery_start_at": "2018-09-19T05:22:07Z",
        "delivery_end_at": "2018-09-19T05:22:07Z",
        "delivery_appt_start_at": "2018-09-19T05:22:07Z",
        "delivery_appt_end_at": "2018-09-19T05:22:07Z",
        "dim_type": "ltl",
        "commodities": [
          {
            "measurement_unit": "inch",
            "weight_unit": "lb",
            "freight_class": "string",
            "commodity_type": "skid",
            "commodity_type_other": "string",
            "description": "string",
            "feet": 0,
            "volume": 0,
            "length": 0,
            "width": 0,
            "height": 0,
            "weight": 0,
            "nmfc": "string",
            "is_stackable": true,
            "quantity": 0,
            "pieces": 0,
            "sku": "string"
          }
        ],
        "accessorials": [
          "string"
        ]
      }
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/orders/bulk_create_booked_order',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'https://platform.roserocket.com/v1/orders/bulk_create_booked_order',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('https://platform.roserocket.com/v1/orders/bulk_create_booked_order', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/orders/bulk_create_booked_order");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /orders/bulk_create_booked_order`

*Bulk create booked orders for several customers.*

> Body parameter

```json
{
  "orders": [
    {
      "order": {
        "external_id": "string",
        "customer": {},
        "origin": {
          "address_book_external_id": "string",
          "org_name": "string",
          "contact_name": "string",
          "address_1": "string",
          "address_2": "string",
          "suite": "string",
          "city": "string",
          "state": "string",
          "country": "string",
          "postal": "string",
          "phone": "string",
          "phone_ext": "string",
          "email": "string",
          "fax": "string",
          "latitude": 0,
          "longitude": 0,
          "bus_hours_start_at": "2018-09-19T05:22:07Z",
          "bus_hours_end_at": "2018-09-19T05:22:07Z"
        },
        "destination": {
          "address_book_external_id": "string",
          "org_name": "string",
          "contact_name": "string",
          "address_1": "string",
          "address_2": "string",
          "suite": "string",
          "city": "string",
          "state": "string",
          "country": "string",
          "postal": "string",
          "phone": "string",
          "phone_ext": "string",
          "email": "string",
          "fax": "string",
          "latitude": 0,
          "longitude": 0,
          "bus_hours_start_at": "2018-09-19T05:22:07Z",
          "bus_hours_end_at": "2018-09-19T05:22:07Z"
        },
        "billing": {
          "address_book_external_id": "string",
          "org_name": "string",
          "contact_name": "string",
          "address_1": "string",
          "address_2": "string",
          "suite": "string",
          "city": "string",
          "state": "string",
          "country": "string",
          "postal": "string",
          "phone": "string",
          "phone_ext": "string",
          "email": "string",
          "fax": "string",
          "latitude": 0,
          "longitude": 0,
          "bus_hours_start_at": "2018-09-19T05:22:07Z",
          "bus_hours_end_at": "2018-09-19T05:22:07Z"
        },
        "billing_option": "prepaid",
        "notes": "string",
        "po_num": "string",
        "tender_num": "string",
        "ref_num": "string",
        "custom_broker": "string",
        "declared_value": 0,
        "declared_value_currency": "cad",
        "pickup_start_at": "2018-09-19T05:22:07Z",
        "pickup_end_at": "2018-09-19T05:22:07Z",
        "pickup_appt_start_at": "2018-09-19T05:22:07Z",
        "pickup_appt_end_at": "2018-09-19T05:22:07Z",
        "delivery_start_at": "2018-09-19T05:22:07Z",
        "delivery_end_at": "2018-09-19T05:22:07Z",
        "delivery_appt_start_at": "2018-09-19T05:22:07Z",
        "delivery_appt_end_at": "2018-09-19T05:22:07Z",
        "dim_type": "ltl",
        "commodities": [
          {
            "measurement_unit": "inch",
            "weight_unit": "lb",
            "freight_class": "string",
            "commodity_type": "skid",
            "commodity_type_other": "string",
            "description": "string",
            "feet": 0,
            "volume": 0,
            "length": 0,
            "width": 0,
            "height": 0,
            "weight": 0,
            "nmfc": "string",
            "is_stackable": true,
            "quantity": 0,
            "pieces": 0,
            "sku": "string"
          }
        ],
        "accessorials": [
          "string"
        ]
      }
    }
  ]
}
```
<h3 id="bulkCreateBookedOrderCustomerAgnostic-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
body|body|[bulkCreateOrderCustomerAgnosticBody](#schema+bulkcreateordercustomeragnosticbody)|true|Bulk create request object
» orders|body|[object]|false|No description
»» order|body|[Order](#schemaorder)|false|Customer's order
»»» id|body|string(uuid)|false|Auto generated system ID
»»» sequence_id|body|integer|false|Auto generated sequence ID per customer
»»» external_id|body|string|false|External ID for mapping the order to an external system. This field value can be _null_
»»» public_id|body|string|false|Auto generated human readable ID
»»» customer|body|[OrderCustomer](#schemaordercustomer)|false|Customer
»»»» id|body|string(uuid)|false|Auto generated customer id
»»»» external_id|body|string|false|Customer external id. This field value can be _null_
»»»» short_code|body|string|false|Customer's short code
»»» origin|body|[OrderAddress](#schemaorderaddress)|true|Order address
»»»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»»»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»»»» org_name|body|string|false|Organization name
»»»» contact_name|body|string|false|Contact name
»»»» address_1|body|string|false|Address line 1
»»»» address_2|body|string|false|Address line 2
»»»» suite|body|string|false|Suite number
»»»» city|body|string|false|City
»»»» state|body|string|false|State / Province
»»»» country|body|string|false|Country (2 letter ISO)
»»»» postal|body|string|false|Postal / Zip code
»»»» phone|body|string|false|Phone number
»»»» phone_ext|body|string|false|Phone extension
»»»» email|body|string|false|Email
»»»» fax|body|string|false|Fax
»»»» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
»»»» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_
»»»» bus_hours_start_at|body|string(date-time)|false|Business hours range (start). This field value can be _null_
»»»» bus_hours_end_at|body|string(date-time)|false|Business hours range (end). This field value can be _null_
»»» destination|body|[OrderAddress](#schemaorderaddress)|true|Order address
»»»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»»»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»»»» org_name|body|string|false|Organization name
»»»» contact_name|body|string|false|Contact name
»»»» address_1|body|string|false|Address line 1
»»»» address_2|body|string|false|Address line 2
»»»» suite|body|string|false|Suite number
»»»» city|body|string|false|City
»»»» state|body|string|false|State / Province
»»»» country|body|string|false|Country (2 letter ISO)
»»»» postal|body|string|false|Postal / Zip code
»»»» phone|body|string|false|Phone number
»»»» phone_ext|body|string|false|Phone extension
»»»» email|body|string|false|Email
»»»» fax|body|string|false|Fax
»»»» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
»»»» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_
»»»» bus_hours_start_at|body|string(date-time)|false|Business hours range (start). This field value can be _null_
»»»» bus_hours_end_at|body|string(date-time)|false|Business hours range (end). This field value can be _null_
»»» billing|body|[OrderAddress](#schemaorderaddress)|true|Order address
»»»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»»»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»»»» org_name|body|string|false|Organization name
»»»» contact_name|body|string|false|Contact name
»»»» address_1|body|string|false|Address line 1
»»»» address_2|body|string|false|Address line 2
»»»» suite|body|string|false|Suite number
»»»» city|body|string|false|City
»»»» state|body|string|false|State / Province
»»»» country|body|string|false|Country (2 letter ISO)
»»»» postal|body|string|false|Postal / Zip code
»»»» phone|body|string|false|Phone number
»»»» phone_ext|body|string|false|Phone extension
»»»» email|body|string|false|Email
»»»» fax|body|string|false|Fax
»»»» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
»»»» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_
»»»» bus_hours_start_at|body|string(date-time)|false|Business hours range (start). This field value can be _null_
»»»» bus_hours_end_at|body|string(date-time)|false|Business hours range (end). This field value can be _null_
»»» status|body|string|false|Order Status
»»» billing_option|body|string|false|Billing Option
»»» notes|body|string|false|Notes that will appear on BOL
»»» po_num|body|string|false|Purchase order numbers (if multiple use comma separated values)
»»» tender_num|body|string|false|Tender number
»»» ref_num|body|string|false|Reference number
»»» custom_broker|body|string|false|Custom broker information
»»» declared_value|body|number(float)|false|Declared value
»»» declared_value_currency|body|string|false|Declared value currency
»»» pickup_start_at|body|string(date-time)|false|Pickup time range (start)
»»» pickup_end_at|body|string(date-time)|false|Pickup time range (end)
»»» pickup_appt_start_at|body|string(date-time)|false|Pickup appointment time range (start). This field value can be _null_
»»» pickup_appt_end_at|body|string(date-time)|false|Pickup appointment time range (end). This field value can be _null_
»»» delivery_start_at|body|string(date-time)|false|Expected delivery time range (start). This field value can be _null_
»»» delivery_end_at|body|string(date-time)|false|Expected delivery time range (end). This field value can be _null_
»»» delivery_appt_start_at|body|string(date-time)|false|Delivery appointment time range (start). This field value can be _null_
»»» delivery_appt_end_at|body|string(date-time)|false|Delivery appointment time range (end). This field value can be _null_
»»» dim_type|body|string|false|Dimension type
»»» commodities|body|[[Commodity](#schemacommodity)]|false|Commodities items
»»»» id|body|string(uuid)|false|Auto generated commodity id
»»»» measurement_unit|body|string|false|Measurement unit
»»»» weight_unit|body|string|false|Weight unit
»»»» freight_class|body|string|false|Freight class
»»»» commodity_type|body|string|false|Commodity type
»»»» commodity_type_other|body|string|false|If commodity type is set to _other_, then this field must have value
»»»» description|body|string|false|Description of the commodity
»»»» feet|body|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»»»» volume|body|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»»»» length|body|number(float)|false|Length of the commodity
»»»» width|body|number(float)|false|Width of the commodity
»»»» height|body|number(float)|false|Height of the commodity
»»»» weight|body|number(float)|false|Weight of the commodity
»»»» nmfc|body|string|false|NMFC number
»»»» is_stackable|body|boolean|false|Is this commodity can be stacked?
»»»» quantity|body|integer|false|Quantity of the commodity
»»»» pieces|body|integer|false|Total number of pieces. This field value can be _null_
»»»» sku|body|string|false|SKU number
»»» accessorials|body|[string(uuid)]|false|No description


#### Enumerated Values

|Parameter|Value|
|---|---|
»»» status|new|
»»» status|saved|
»»» status|cancelled|
»»» status|quoting|
»»» status|quoted|
»»» status|no-quote|
»»» status|spot-quote-requested|
»»» status|pending-dispatch|
»»» status|dispatched|
»»» status|in-transit|
»»» status|delivered|
»»» status|archived|
»»» status|invoice-created|
»»» status|invoice-sent|
»»» status|invoice-paid|
»»» status|claim|
»»» status|draft-quick-quote|
»»» status|quick-quoting|
»»» status|quick-quoted|
»»» status|no-quick-quote|
»»» status|spot-qq-requested|
»»» status|pickup-request|
»»» status|rejected|
»»» billing_option|prepaid|
»»» billing_option|collect|
»»» billing_option|thirdparty|
»»» declared_value_currency|cad|
»»» declared_value_currency|usd|
»»» dim_type|ltl|
»»» dim_type|ftl|
»»» dim_type|volume|
»»»» measurement_unit|inch|
»»»» measurement_unit|cm|
»»»» weight_unit|lb|
»»»» weight_unit|kg|
»»»» commodity_type|skid|
»»»» commodity_type|other|

> Example responses

```json
{
  "job_id": "string",
  "message": "string"
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="bulkCreateBookedOrderCustomerAgnostic-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[BulkOrderCreateResponse](#schemabulkordercreateresponse)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: orders )
</aside>

## bulkUpsertBookedOrderCustomerAgnostic

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/orders/bulk_upsert_booked_order \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST https://platform.roserocket.com/v1/orders/bulk_upsert_booked_order HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/orders/bulk_upsert_booked_order',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "orders": [
    {
      "order": {
        "external_id": "string",
        "customer": {},
        "origin": {
          "address_book_external_id": "string",
          "org_name": "string",
          "contact_name": "string",
          "address_1": "string",
          "address_2": "string",
          "suite": "string",
          "city": "string",
          "state": "string",
          "country": "string",
          "postal": "string",
          "phone": "string",
          "phone_ext": "string",
          "email": "string",
          "fax": "string",
          "latitude": 0,
          "longitude": 0,
          "bus_hours_start_at": "2018-09-19T05:22:07Z",
          "bus_hours_end_at": "2018-09-19T05:22:07Z"
        },
        "destination": {
          "address_book_external_id": "string",
          "org_name": "string",
          "contact_name": "string",
          "address_1": "string",
          "address_2": "string",
          "suite": "string",
          "city": "string",
          "state": "string",
          "country": "string",
          "postal": "string",
          "phone": "string",
          "phone_ext": "string",
          "email": "string",
          "fax": "string",
          "latitude": 0,
          "longitude": 0,
          "bus_hours_start_at": "2018-09-19T05:22:07Z",
          "bus_hours_end_at": "2018-09-19T05:22:07Z"
        },
        "billing": {
          "address_book_external_id": "string",
          "org_name": "string",
          "contact_name": "string",
          "address_1": "string",
          "address_2": "string",
          "suite": "string",
          "city": "string",
          "state": "string",
          "country": "string",
          "postal": "string",
          "phone": "string",
          "phone_ext": "string",
          "email": "string",
          "fax": "string",
          "latitude": 0,
          "longitude": 0,
          "bus_hours_start_at": "2018-09-19T05:22:07Z",
          "bus_hours_end_at": "2018-09-19T05:22:07Z"
        },
        "billing_option": "prepaid",
        "notes": "string",
        "po_num": "string",
        "tender_num": "string",
        "ref_num": "string",
        "custom_broker": "string",
        "declared_value": 0,
        "declared_value_currency": "cad",
        "pickup_start_at": "2018-09-19T05:22:07Z",
        "pickup_end_at": "2018-09-19T05:22:07Z",
        "pickup_appt_start_at": "2018-09-19T05:22:07Z",
        "pickup_appt_end_at": "2018-09-19T05:22:07Z",
        "delivery_start_at": "2018-09-19T05:22:07Z",
        "delivery_end_at": "2018-09-19T05:22:07Z",
        "delivery_appt_start_at": "2018-09-19T05:22:07Z",
        "delivery_appt_end_at": "2018-09-19T05:22:07Z",
        "dim_type": "ltl",
        "commodities": [
          {
            "measurement_unit": "inch",
            "weight_unit": "lb",
            "freight_class": "string",
            "commodity_type": "skid",
            "commodity_type_other": "string",
            "description": "string",
            "feet": 0,
            "volume": 0,
            "length": 0,
            "width": 0,
            "height": 0,
            "weight": 0,
            "nmfc": "string",
            "is_stackable": true,
            "quantity": 0,
            "pieces": 0,
            "sku": "string"
          }
        ],
        "accessorials": [
          "string"
        ]
      }
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/orders/bulk_upsert_booked_order',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'https://platform.roserocket.com/v1/orders/bulk_upsert_booked_order',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('https://platform.roserocket.com/v1/orders/bulk_upsert_booked_order', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/orders/bulk_upsert_booked_order");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /orders/bulk_upsert_booked_order`

*Upsert orders for several customers.*

> Body parameter

```json
{
  "orders": [
    {
      "order": {
        "external_id": "string",
        "customer": {},
        "origin": {
          "address_book_external_id": "string",
          "org_name": "string",
          "contact_name": "string",
          "address_1": "string",
          "address_2": "string",
          "suite": "string",
          "city": "string",
          "state": "string",
          "country": "string",
          "postal": "string",
          "phone": "string",
          "phone_ext": "string",
          "email": "string",
          "fax": "string",
          "latitude": 0,
          "longitude": 0,
          "bus_hours_start_at": "2018-09-19T05:22:07Z",
          "bus_hours_end_at": "2018-09-19T05:22:07Z"
        },
        "destination": {
          "address_book_external_id": "string",
          "org_name": "string",
          "contact_name": "string",
          "address_1": "string",
          "address_2": "string",
          "suite": "string",
          "city": "string",
          "state": "string",
          "country": "string",
          "postal": "string",
          "phone": "string",
          "phone_ext": "string",
          "email": "string",
          "fax": "string",
          "latitude": 0,
          "longitude": 0,
          "bus_hours_start_at": "2018-09-19T05:22:07Z",
          "bus_hours_end_at": "2018-09-19T05:22:07Z"
        },
        "billing": {
          "address_book_external_id": "string",
          "org_name": "string",
          "contact_name": "string",
          "address_1": "string",
          "address_2": "string",
          "suite": "string",
          "city": "string",
          "state": "string",
          "country": "string",
          "postal": "string",
          "phone": "string",
          "phone_ext": "string",
          "email": "string",
          "fax": "string",
          "latitude": 0,
          "longitude": 0,
          "bus_hours_start_at": "2018-09-19T05:22:07Z",
          "bus_hours_end_at": "2018-09-19T05:22:07Z"
        },
        "billing_option": "prepaid",
        "notes": "string",
        "po_num": "string",
        "tender_num": "string",
        "ref_num": "string",
        "custom_broker": "string",
        "declared_value": 0,
        "declared_value_currency": "cad",
        "pickup_start_at": "2018-09-19T05:22:07Z",
        "pickup_end_at": "2018-09-19T05:22:07Z",
        "pickup_appt_start_at": "2018-09-19T05:22:07Z",
        "pickup_appt_end_at": "2018-09-19T05:22:07Z",
        "delivery_start_at": "2018-09-19T05:22:07Z",
        "delivery_end_at": "2018-09-19T05:22:07Z",
        "delivery_appt_start_at": "2018-09-19T05:22:07Z",
        "delivery_appt_end_at": "2018-09-19T05:22:07Z",
        "dim_type": "ltl",
        "commodities": [
          {
            "measurement_unit": "inch",
            "weight_unit": "lb",
            "freight_class": "string",
            "commodity_type": "skid",
            "commodity_type_other": "string",
            "description": "string",
            "feet": 0,
            "volume": 0,
            "length": 0,
            "width": 0,
            "height": 0,
            "weight": 0,
            "nmfc": "string",
            "is_stackable": true,
            "quantity": 0,
            "pieces": 0,
            "sku": "string"
          }
        ],
        "accessorials": [
          "string"
        ]
      }
    }
  ]
}
```
<h3 id="bulkUpsertBookedOrderCustomerAgnostic-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
body|body|object|true|Bulk upsert request object
» orders|body|[object]|false|No description
»» order|body|[Order](#schemaorder)|false|No description


> Example responses

```json
{
  "job_id": "string",
  "message": "string"
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="bulkUpsertBookedOrderCustomerAgnostic-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[BulkOrderCreateResponse](#schemabulkordercreateresponse)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: orders )
</aside>

## reviseOrderOriginByID

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_origin \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_origin HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_origin',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "address": {
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_origin',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_origin',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_origin', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_origin");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /customers/{customerID}/orders/{orderID}/revise_origin`

*Revise the origin of an order by ID*

> Body parameter

```json
{
  "address": {
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  }
}
```
<h3 id="reviseOrderOriginByID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.
orderID|path|string(uuid)|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.
body|body|[OrderAddressReviseRequest](#schemaorderaddressreviserequest)|true|Revise order address request object
» address|body|[OrderAddress](#schemaorderaddress)|false|Order address
»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|body|string|false|Organization name
»» contact_name|body|string|false|Contact name
»» address_1|body|string|false|Address line 1
»» address_2|body|string|false|Address line 2
»» suite|body|string|false|Suite number
»» city|body|string|false|City
»» state|body|string|false|State / Province
»» country|body|string|false|Country (2 letter ISO)
»» postal|body|string|false|Postal / Zip code
»» phone|body|string|false|Phone number
»» phone_ext|body|string|false|Phone extension
»» email|body|string|false|Email
»» fax|body|string|false|Fax
»» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|body|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|body|string(date-time)|false|Business hours range (end). This field value can be _null_


> Example responses

```json
{
  "order": {
    "id": "string",
    "sequence_id": 0,
    "external_id": "string",
    "public_id": "string",
    "customer": {
      "id": "string",
      "external_id": "string",
      "short_code": "string"
    },
    "origin": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "destination": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "billing": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "status": "new",
    "billing_option": "prepaid",
    "notes": "string",
    "po_num": "string",
    "tender_num": "string",
    "ref_num": "string",
    "custom_broker": "string",
    "declared_value": 0,
    "declared_value_currency": "cad",
    "pickup_start_at": "2018-09-19T05:22:07Z",
    "pickup_end_at": "2018-09-19T05:22:07Z",
    "pickup_appt_start_at": "2018-09-19T05:22:07Z",
    "pickup_appt_end_at": "2018-09-19T05:22:07Z",
    "delivery_start_at": "2018-09-19T05:22:07Z",
    "delivery_end_at": "2018-09-19T05:22:07Z",
    "delivery_appt_start_at": "2018-09-19T05:22:07Z",
    "delivery_appt_end_at": "2018-09-19T05:22:07Z",
    "dim_type": "ltl",
    "commodities": [
      {
        "id": "string",
        "measurement_unit": "inch",
        "weight_unit": "lb",
        "freight_class": "string",
        "commodity_type": "skid",
        "commodity_type_other": "string",
        "description": "string",
        "feet": 0,
        "volume": 0,
        "length": 0,
        "width": 0,
        "height": 0,
        "weight": 0,
        "nmfc": "string",
        "is_stackable": true,
        "quantity": 0,
        "pieces": 0,
        "sku": "string"
      }
    ],
    "accessorials": [
      "string"
    ]
  },
  "legs": [
    {
      "id": "string",
      "sequence_id": 0,
      "version": 0,
      "external_id": "string",
      "public_id": "string",
      "order_id": "string",
      "manifest_id": "string",
      "origin_stop_id": "string",
      "destination_stop_id": "string",
      "origin": {
        "terminal_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0
      },
      "destination": {
        "terminal_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0
      },
      "status": "available",
      "origin_start_at": "2018-09-19T05:22:07Z",
      "origin_end_at": "2018-09-19T05:22:07Z",
      "origin_appt_start_at": "2018-09-19T05:22:07Z",
      "origin_appt_end_at": "2018-09-19T05:22:07Z",
      "destination_start_at": "2018-09-19T05:22:07Z",
      "destination_end_at": "2018-09-19T05:22:07Z",
      "destination_appt_start_at": "2018-09-19T05:22:07Z",
      "destination_appt_end_at": "2018-09-19T05:22:07Z",
      "commodities": [
        {
          "id": "string",
          "measurement_unit": "inch",
          "weight_unit": "lb",
          "freight_class": "string",
          "commodity_type": "skid",
          "commodity_type_other": "string",
          "description": "string",
          "feet": 0,
          "volume": 0,
          "length": 0,
          "width": 0,
          "height": 0,
          "weight": 0,
          "nmfc": "string",
          "is_stackable": true,
          "quantity": 0,
          "pieces": 0,
          "sku": "string"
        }
      ],
      "accessorials": [
        "string"
      ],
      "history": {
        "origin_arrived_at": "2018-09-19T05:22:07Z",
        "origin_in_at": "2018-09-19T05:22:07Z",
        "origin_pickedup_at": "2018-09-19T05:22:07Z",
        "origin_out_at": "2018-09-19T05:22:07Z",
        "destination_arrived_at": "2018-09-19T05:22:07Z",
        "destination_in_at": "2018-09-19T05:22:07Z",
        "destination_delivered_at": "2018-09-19T05:22:07Z",
        "destination_out_at": "2018-09-19T05:22:07Z"
      }
    }
  ]
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="reviseOrderOriginByID-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[OrderAndLegsResponse](#schemaorderandlegsresponse)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: orders )
</aside>

## reviseOrderDestinationByID

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_destination \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_destination HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_destination',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "address": {
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_destination',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_destination',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_destination', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_destination");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /customers/{customerID}/orders/{orderID}/revise_destination`

*Revise the destination of an order by ID*

> Body parameter

```json
{
  "address": {
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  }
}
```
<h3 id="reviseOrderDestinationByID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.
orderID|path|string(uuid)|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.
body|body|[OrderAddressReviseRequest](#schemaorderaddressreviserequest)|true|Revise order address request object
» address|body|[OrderAddress](#schemaorderaddress)|false|Order address
»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|body|string|false|Organization name
»» contact_name|body|string|false|Contact name
»» address_1|body|string|false|Address line 1
»» address_2|body|string|false|Address line 2
»» suite|body|string|false|Suite number
»» city|body|string|false|City
»» state|body|string|false|State / Province
»» country|body|string|false|Country (2 letter ISO)
»» postal|body|string|false|Postal / Zip code
»» phone|body|string|false|Phone number
»» phone_ext|body|string|false|Phone extension
»» email|body|string|false|Email
»» fax|body|string|false|Fax
»» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|body|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|body|string(date-time)|false|Business hours range (end). This field value can be _null_


> Example responses

```json
{
  "order": {
    "id": "string",
    "sequence_id": 0,
    "external_id": "string",
    "public_id": "string",
    "customer": {
      "id": "string",
      "external_id": "string",
      "short_code": "string"
    },
    "origin": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "destination": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "billing": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "status": "new",
    "billing_option": "prepaid",
    "notes": "string",
    "po_num": "string",
    "tender_num": "string",
    "ref_num": "string",
    "custom_broker": "string",
    "declared_value": 0,
    "declared_value_currency": "cad",
    "pickup_start_at": "2018-09-19T05:22:07Z",
    "pickup_end_at": "2018-09-19T05:22:07Z",
    "pickup_appt_start_at": "2018-09-19T05:22:07Z",
    "pickup_appt_end_at": "2018-09-19T05:22:07Z",
    "delivery_start_at": "2018-09-19T05:22:07Z",
    "delivery_end_at": "2018-09-19T05:22:07Z",
    "delivery_appt_start_at": "2018-09-19T05:22:07Z",
    "delivery_appt_end_at": "2018-09-19T05:22:07Z",
    "dim_type": "ltl",
    "commodities": [
      {
        "id": "string",
        "measurement_unit": "inch",
        "weight_unit": "lb",
        "freight_class": "string",
        "commodity_type": "skid",
        "commodity_type_other": "string",
        "description": "string",
        "feet": 0,
        "volume": 0,
        "length": 0,
        "width": 0,
        "height": 0,
        "weight": 0,
        "nmfc": "string",
        "is_stackable": true,
        "quantity": 0,
        "pieces": 0,
        "sku": "string"
      }
    ],
    "accessorials": [
      "string"
    ]
  },
  "legs": [
    {
      "id": "string",
      "sequence_id": 0,
      "version": 0,
      "external_id": "string",
      "public_id": "string",
      "order_id": "string",
      "manifest_id": "string",
      "origin_stop_id": "string",
      "destination_stop_id": "string",
      "origin": {
        "terminal_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0
      },
      "destination": {
        "terminal_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0
      },
      "status": "available",
      "origin_start_at": "2018-09-19T05:22:07Z",
      "origin_end_at": "2018-09-19T05:22:07Z",
      "origin_appt_start_at": "2018-09-19T05:22:07Z",
      "origin_appt_end_at": "2018-09-19T05:22:07Z",
      "destination_start_at": "2018-09-19T05:22:07Z",
      "destination_end_at": "2018-09-19T05:22:07Z",
      "destination_appt_start_at": "2018-09-19T05:22:07Z",
      "destination_appt_end_at": "2018-09-19T05:22:07Z",
      "commodities": [
        {
          "id": "string",
          "measurement_unit": "inch",
          "weight_unit": "lb",
          "freight_class": "string",
          "commodity_type": "skid",
          "commodity_type_other": "string",
          "description": "string",
          "feet": 0,
          "volume": 0,
          "length": 0,
          "width": 0,
          "height": 0,
          "weight": 0,
          "nmfc": "string",
          "is_stackable": true,
          "quantity": 0,
          "pieces": 0,
          "sku": "string"
        }
      ],
      "accessorials": [
        "string"
      ],
      "history": {
        "origin_arrived_at": "2018-09-19T05:22:07Z",
        "origin_in_at": "2018-09-19T05:22:07Z",
        "origin_pickedup_at": "2018-09-19T05:22:07Z",
        "origin_out_at": "2018-09-19T05:22:07Z",
        "destination_arrived_at": "2018-09-19T05:22:07Z",
        "destination_in_at": "2018-09-19T05:22:07Z",
        "destination_delivered_at": "2018-09-19T05:22:07Z",
        "destination_out_at": "2018-09-19T05:22:07Z"
      }
    }
  ]
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="reviseOrderDestinationByID-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[OrderAndLegsResponse](#schemaorderandlegsresponse)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: orders )
</aside>

## reviseOrderCommoditiesByID

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_commodities \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_commodities HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_commodities',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "commodities": [
    {
      "measurement_unit": "inch",
      "weight_unit": "lb",
      "freight_class": "string",
      "commodity_type": "skid",
      "commodity_type_other": "string",
      "description": "string",
      "feet": 0,
      "volume": 0,
      "length": 0,
      "width": 0,
      "height": 0,
      "weight": 0,
      "nmfc": "string",
      "is_stackable": true,
      "quantity": 0,
      "pieces": 0,
      "sku": "string"
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_commodities',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_commodities',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_commodities', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_commodities");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /customers/{customerID}/orders/{orderID}/revise_commodities`

*Revise the commodities of an order by ID*

> Body parameter

```json
{
  "commodities": [
    {
      "measurement_unit": "inch",
      "weight_unit": "lb",
      "freight_class": "string",
      "commodity_type": "skid",
      "commodity_type_other": "string",
      "description": "string",
      "feet": 0,
      "volume": 0,
      "length": 0,
      "width": 0,
      "height": 0,
      "weight": 0,
      "nmfc": "string",
      "is_stackable": true,
      "quantity": 0,
      "pieces": 0,
      "sku": "string"
    }
  ]
}
```
<h3 id="reviseOrderCommoditiesByID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.
orderID|path|string(uuid)|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.
body|body|[CommodityReviseRequest](#schemacommodityreviserequest)|true|Revise order commodities request object
» commodities|body|[[Commodity](#schemacommodity)]|false|No description
»» id|body|string(uuid)|false|Auto generated commodity id
»» measurement_unit|body|string|false|Measurement unit
»» weight_unit|body|string|false|Weight unit
»» freight_class|body|string|false|Freight class
»» commodity_type|body|string|false|Commodity type
»» commodity_type_other|body|string|false|If commodity type is set to _other_, then this field must have value
»» description|body|string|false|Description of the commodity
»» feet|body|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»» volume|body|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»» length|body|number(float)|false|Length of the commodity
»» width|body|number(float)|false|Width of the commodity
»» height|body|number(float)|false|Height of the commodity
»» weight|body|number(float)|false|Weight of the commodity
»» nmfc|body|string|false|NMFC number
»» is_stackable|body|boolean|false|Is this commodity can be stacked?
»» quantity|body|integer|false|Quantity of the commodity
»» pieces|body|integer|false|Total number of pieces. This field value can be _null_
»» sku|body|string|false|SKU number


#### Enumerated Values

|Parameter|Value|
|---|---|
»» measurement_unit|inch|
»» measurement_unit|cm|
»» weight_unit|lb|
»» weight_unit|kg|
»» commodity_type|skid|
»» commodity_type|other|

> Example responses

```json
{
  "order": {
    "id": "string",
    "sequence_id": 0,
    "external_id": "string",
    "public_id": "string",
    "customer": {
      "id": "string",
      "external_id": "string",
      "short_code": "string"
    },
    "origin": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "destination": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "billing": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "status": "new",
    "billing_option": "prepaid",
    "notes": "string",
    "po_num": "string",
    "tender_num": "string",
    "ref_num": "string",
    "custom_broker": "string",
    "declared_value": 0,
    "declared_value_currency": "cad",
    "pickup_start_at": "2018-09-19T05:22:07Z",
    "pickup_end_at": "2018-09-19T05:22:07Z",
    "pickup_appt_start_at": "2018-09-19T05:22:07Z",
    "pickup_appt_end_at": "2018-09-19T05:22:07Z",
    "delivery_start_at": "2018-09-19T05:22:07Z",
    "delivery_end_at": "2018-09-19T05:22:07Z",
    "delivery_appt_start_at": "2018-09-19T05:22:07Z",
    "delivery_appt_end_at": "2018-09-19T05:22:07Z",
    "dim_type": "ltl",
    "commodities": [
      {
        "id": "string",
        "measurement_unit": "inch",
        "weight_unit": "lb",
        "freight_class": "string",
        "commodity_type": "skid",
        "commodity_type_other": "string",
        "description": "string",
        "feet": 0,
        "volume": 0,
        "length": 0,
        "width": 0,
        "height": 0,
        "weight": 0,
        "nmfc": "string",
        "is_stackable": true,
        "quantity": 0,
        "pieces": 0,
        "sku": "string"
      }
    ],
    "accessorials": [
      "string"
    ]
  },
  "legs": [
    {
      "id": "string",
      "sequence_id": 0,
      "version": 0,
      "external_id": "string",
      "public_id": "string",
      "order_id": "string",
      "manifest_id": "string",
      "origin_stop_id": "string",
      "destination_stop_id": "string",
      "origin": {
        "terminal_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0
      },
      "destination": {
        "terminal_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0
      },
      "status": "available",
      "origin_start_at": "2018-09-19T05:22:07Z",
      "origin_end_at": "2018-09-19T05:22:07Z",
      "origin_appt_start_at": "2018-09-19T05:22:07Z",
      "origin_appt_end_at": "2018-09-19T05:22:07Z",
      "destination_start_at": "2018-09-19T05:22:07Z",
      "destination_end_at": "2018-09-19T05:22:07Z",
      "destination_appt_start_at": "2018-09-19T05:22:07Z",
      "destination_appt_end_at": "2018-09-19T05:22:07Z",
      "commodities": [
        {
          "id": "string",
          "measurement_unit": "inch",
          "weight_unit": "lb",
          "freight_class": "string",
          "commodity_type": "skid",
          "commodity_type_other": "string",
          "description": "string",
          "feet": 0,
          "volume": 0,
          "length": 0,
          "width": 0,
          "height": 0,
          "weight": 0,
          "nmfc": "string",
          "is_stackable": true,
          "quantity": 0,
          "pieces": 0,
          "sku": "string"
        }
      ],
      "accessorials": [
        "string"
      ],
      "history": {
        "origin_arrived_at": "2018-09-19T05:22:07Z",
        "origin_in_at": "2018-09-19T05:22:07Z",
        "origin_pickedup_at": "2018-09-19T05:22:07Z",
        "origin_out_at": "2018-09-19T05:22:07Z",
        "destination_arrived_at": "2018-09-19T05:22:07Z",
        "destination_in_at": "2018-09-19T05:22:07Z",
        "destination_delivered_at": "2018-09-19T05:22:07Z",
        "destination_out_at": "2018-09-19T05:22:07Z"
      }
    }
  ]
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="reviseOrderCommoditiesByID-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[OrderAndLegsResponse](#schemaorderandlegsresponse)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: orders )
</aside>

## getOrderByID

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID} \
  -H 'Accept: application/json'

```

```http
GET https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID} HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /customers/{customerID}/orders/{orderID}`

*Get customer's order by ID*

<h3 id="getOrderByID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.
orderID|path|string(uuid)|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.


> Example responses

```json
{
  "order": {
    "id": "string",
    "sequence_id": 0,
    "external_id": "string",
    "public_id": "string",
    "customer": {
      "id": "string",
      "external_id": "string",
      "short_code": "string"
    },
    "origin": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "destination": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "billing": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "status": "new",
    "billing_option": "prepaid",
    "notes": "string",
    "po_num": "string",
    "tender_num": "string",
    "ref_num": "string",
    "custom_broker": "string",
    "declared_value": 0,
    "declared_value_currency": "cad",
    "pickup_start_at": "2018-09-19T05:22:07Z",
    "pickup_end_at": "2018-09-19T05:22:07Z",
    "pickup_appt_start_at": "2018-09-19T05:22:07Z",
    "pickup_appt_end_at": "2018-09-19T05:22:07Z",
    "delivery_start_at": "2018-09-19T05:22:07Z",
    "delivery_end_at": "2018-09-19T05:22:07Z",
    "delivery_appt_start_at": "2018-09-19T05:22:07Z",
    "delivery_appt_end_at": "2018-09-19T05:22:07Z",
    "dim_type": "ltl",
    "commodities": [
      {
        "id": "string",
        "measurement_unit": "inch",
        "weight_unit": "lb",
        "freight_class": "string",
        "commodity_type": "skid",
        "commodity_type_other": "string",
        "description": "string",
        "feet": 0,
        "volume": 0,
        "length": 0,
        "width": 0,
        "height": 0,
        "weight": 0,
        "nmfc": "string",
        "is_stackable": true,
        "quantity": 0,
        "pieces": 0,
        "sku": "string"
      }
    ],
    "accessorials": [
      "string"
    ]
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="getOrderByID-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="getOrderByID-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
order|[Order](#schemaorder)|false|Customer's order
» id|string(uuid)|false|Auto generated system ID
» sequence_id|integer|false|Auto generated sequence ID per customer
» external_id|string|false|External ID for mapping the order to an external system. This field value can be _null_
» public_id|string|false|Auto generated human readable ID
» customer|[OrderCustomer](#schemaordercustomer)|false|Customer
»» id|string(uuid)|false|Auto generated customer id
»» external_id|string|false|Customer external id. This field value can be _null_
»» short_code|string|false|Customer's short code
» origin|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
» destination|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
» billing|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
» status|string|false|Order Status
» billing_option|string|false|Billing Option
» notes|string|false|Notes that will appear on BOL
» po_num|string|false|Purchase order numbers (if multiple use comma separated values)
» tender_num|string|false|Tender number
» ref_num|string|false|Reference number
» custom_broker|string|false|Custom broker information
» declared_value|number(float)|false|Declared value
» declared_value_currency|string|false|Declared value currency
» pickup_start_at|string(date-time)|false|Pickup time range (start)
» pickup_end_at|string(date-time)|false|Pickup time range (end)
» pickup_appt_start_at|string(date-time)|false|Pickup appointment time range (start). This field value can be _null_
» pickup_appt_end_at|string(date-time)|false|Pickup appointment time range (end). This field value can be _null_
» delivery_start_at|string(date-time)|false|Expected delivery time range (start). This field value can be _null_
» delivery_end_at|string(date-time)|false|Expected delivery time range (end). This field value can be _null_
» delivery_appt_start_at|string(date-time)|false|Delivery appointment time range (start). This field value can be _null_
» delivery_appt_end_at|string(date-time)|false|Delivery appointment time range (end). This field value can be _null_
» dim_type|string|false|Dimension type
» commodities|[[Commodity](#schemacommodity)]|false|Commodities items
»» id|string(uuid)|false|Auto generated commodity id
»» measurement_unit|string|false|Measurement unit
»» weight_unit|string|false|Weight unit
»» freight_class|string|false|Freight class
»» commodity_type|string|false|Commodity type
»» commodity_type_other|string|false|If commodity type is set to _other_, then this field must have value
»» description|string|false|Description of the commodity
»» feet|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»» volume|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»» length|number(float)|false|Length of the commodity
»» width|number(float)|false|Width of the commodity
»» height|number(float)|false|Height of the commodity
»» weight|number(float)|false|Weight of the commodity
»» nmfc|string|false|NMFC number
»» is_stackable|boolean|false|Is this commodity can be stacked?
»» quantity|integer|false|Quantity of the commodity
»» pieces|integer|false|Total number of pieces. This field value can be _null_
»» sku|string|false|SKU number
» accessorials|[string(uuid)]|false|No description



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: orders )
</aside>

## updateOrderByID

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID} HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "external_id": "string",
  "customer": {},
  "origin": {
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  },
  "destination": {
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  },
  "billing": {
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  },
  "billing_option": "prepaid",
  "notes": "string",
  "po_num": "string",
  "tender_num": "string",
  "ref_num": "string",
  "custom_broker": "string",
  "declared_value": 0,
  "declared_value_currency": "cad",
  "pickup_start_at": "2018-09-19T05:22:07Z",
  "pickup_end_at": "2018-09-19T05:22:07Z",
  "pickup_appt_start_at": "2018-09-19T05:22:07Z",
  "pickup_appt_end_at": "2018-09-19T05:22:07Z",
  "delivery_start_at": "2018-09-19T05:22:07Z",
  "delivery_end_at": "2018-09-19T05:22:07Z",
  "delivery_appt_start_at": "2018-09-19T05:22:07Z",
  "delivery_appt_end_at": "2018-09-19T05:22:07Z",
  "dim_type": "ltl",
  "commodities": [
    {
      "measurement_unit": "inch",
      "weight_unit": "lb",
      "freight_class": "string",
      "commodity_type": "skid",
      "commodity_type_other": "string",
      "description": "string",
      "feet": 0,
      "volume": 0,
      "length": 0,
      "width": 0,
      "height": 0,
      "weight": 0,
      "nmfc": "string",
      "is_stackable": true,
      "quantity": 0,
      "pieces": 0,
      "sku": "string"
    }
  ],
  "accessorials": [
    "string"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /customers/{customerID}/orders/{orderID}`

*Update customer's order by ID*

> Body parameter

```json
{
  "external_id": "string",
  "customer": {},
  "origin": {
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  },
  "destination": {
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  },
  "billing": {
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  },
  "billing_option": "prepaid",
  "notes": "string",
  "po_num": "string",
  "tender_num": "string",
  "ref_num": "string",
  "custom_broker": "string",
  "declared_value": 0,
  "declared_value_currency": "cad",
  "pickup_start_at": "2018-09-19T05:22:07Z",
  "pickup_end_at": "2018-09-19T05:22:07Z",
  "pickup_appt_start_at": "2018-09-19T05:22:07Z",
  "pickup_appt_end_at": "2018-09-19T05:22:07Z",
  "delivery_start_at": "2018-09-19T05:22:07Z",
  "delivery_end_at": "2018-09-19T05:22:07Z",
  "delivery_appt_start_at": "2018-09-19T05:22:07Z",
  "delivery_appt_end_at": "2018-09-19T05:22:07Z",
  "dim_type": "ltl",
  "commodities": [
    {
      "measurement_unit": "inch",
      "weight_unit": "lb",
      "freight_class": "string",
      "commodity_type": "skid",
      "commodity_type_other": "string",
      "description": "string",
      "feet": 0,
      "volume": 0,
      "length": 0,
      "width": 0,
      "height": 0,
      "weight": 0,
      "nmfc": "string",
      "is_stackable": true,
      "quantity": 0,
      "pieces": 0,
      "sku": "string"
    }
  ],
  "accessorials": [
    "string"
  ]
}
```
<h3 id="updateOrderByID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.
orderID|path|string(uuid)|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.
body|body|[Order](#schemaorder)|true|Order object
» id|body|string(uuid)|false|Auto generated system ID
» sequence_id|body|integer|false|Auto generated sequence ID per customer
» external_id|body|string|false|External ID for mapping the order to an external system. This field value can be _null_
» public_id|body|string|false|Auto generated human readable ID
» customer|body|[OrderCustomer](#schemaordercustomer)|false|Customer
»» id|body|string(uuid)|false|Auto generated customer id
»» external_id|body|string|false|Customer external id. This field value can be _null_
»» short_code|body|string|false|Customer's short code
» origin|body|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|body|string|false|Organization name
»» contact_name|body|string|false|Contact name
»» address_1|body|string|false|Address line 1
»» address_2|body|string|false|Address line 2
»» suite|body|string|false|Suite number
»» city|body|string|false|City
»» state|body|string|false|State / Province
»» country|body|string|false|Country (2 letter ISO)
»» postal|body|string|false|Postal / Zip code
»» phone|body|string|false|Phone number
»» phone_ext|body|string|false|Phone extension
»» email|body|string|false|Email
»» fax|body|string|false|Fax
»» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|body|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|body|string(date-time)|false|Business hours range (end). This field value can be _null_
» destination|body|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|body|string|false|Organization name
»» contact_name|body|string|false|Contact name
»» address_1|body|string|false|Address line 1
»» address_2|body|string|false|Address line 2
»» suite|body|string|false|Suite number
»» city|body|string|false|City
»» state|body|string|false|State / Province
»» country|body|string|false|Country (2 letter ISO)
»» postal|body|string|false|Postal / Zip code
»» phone|body|string|false|Phone number
»» phone_ext|body|string|false|Phone extension
»» email|body|string|false|Email
»» fax|body|string|false|Fax
»» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|body|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|body|string(date-time)|false|Business hours range (end). This field value can be _null_
» billing|body|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|body|string|false|Organization name
»» contact_name|body|string|false|Contact name
»» address_1|body|string|false|Address line 1
»» address_2|body|string|false|Address line 2
»» suite|body|string|false|Suite number
»» city|body|string|false|City
»» state|body|string|false|State / Province
»» country|body|string|false|Country (2 letter ISO)
»» postal|body|string|false|Postal / Zip code
»» phone|body|string|false|Phone number
»» phone_ext|body|string|false|Phone extension
»» email|body|string|false|Email
»» fax|body|string|false|Fax
»» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|body|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|body|string(date-time)|false|Business hours range (end). This field value can be _null_
» status|body|string|false|Order Status
» billing_option|body|string|false|Billing Option
» notes|body|string|false|Notes that will appear on BOL
» po_num|body|string|false|Purchase order numbers (if multiple use comma separated values)
» tender_num|body|string|false|Tender number
» ref_num|body|string|false|Reference number
» custom_broker|body|string|false|Custom broker information
» declared_value|body|number(float)|false|Declared value
» declared_value_currency|body|string|false|Declared value currency
» pickup_start_at|body|string(date-time)|false|Pickup time range (start)
» pickup_end_at|body|string(date-time)|false|Pickup time range (end)
» pickup_appt_start_at|body|string(date-time)|false|Pickup appointment time range (start). This field value can be _null_
» pickup_appt_end_at|body|string(date-time)|false|Pickup appointment time range (end). This field value can be _null_
» delivery_start_at|body|string(date-time)|false|Expected delivery time range (start). This field value can be _null_
» delivery_end_at|body|string(date-time)|false|Expected delivery time range (end). This field value can be _null_
» delivery_appt_start_at|body|string(date-time)|false|Delivery appointment time range (start). This field value can be _null_
» delivery_appt_end_at|body|string(date-time)|false|Delivery appointment time range (end). This field value can be _null_
» dim_type|body|string|false|Dimension type
» commodities|body|[[Commodity](#schemacommodity)]|false|Commodities items
»» id|body|string(uuid)|false|Auto generated commodity id
»» measurement_unit|body|string|false|Measurement unit
»» weight_unit|body|string|false|Weight unit
»» freight_class|body|string|false|Freight class
»» commodity_type|body|string|false|Commodity type
»» commodity_type_other|body|string|false|If commodity type is set to _other_, then this field must have value
»» description|body|string|false|Description of the commodity
»» feet|body|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»» volume|body|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»» length|body|number(float)|false|Length of the commodity
»» width|body|number(float)|false|Width of the commodity
»» height|body|number(float)|false|Height of the commodity
»» weight|body|number(float)|false|Weight of the commodity
»» nmfc|body|string|false|NMFC number
»» is_stackable|body|boolean|false|Is this commodity can be stacked?
»» quantity|body|integer|false|Quantity of the commodity
»» pieces|body|integer|false|Total number of pieces. This field value can be _null_
»» sku|body|string|false|SKU number
» accessorials|body|[string(uuid)]|false|No description


#### Enumerated Values

|Parameter|Value|
|---|---|
» status|new|
» status|saved|
» status|cancelled|
» status|quoting|
» status|quoted|
» status|no-quote|
» status|spot-quote-requested|
» status|pending-dispatch|
» status|dispatched|
» status|in-transit|
» status|delivered|
» status|archived|
» status|invoice-created|
» status|invoice-sent|
» status|invoice-paid|
» status|claim|
» status|draft-quick-quote|
» status|quick-quoting|
» status|quick-quoted|
» status|no-quick-quote|
» status|spot-qq-requested|
» status|pickup-request|
» status|rejected|
» billing_option|prepaid|
» billing_option|collect|
» billing_option|thirdparty|
» declared_value_currency|cad|
» declared_value_currency|usd|
» dim_type|ltl|
» dim_type|ftl|
» dim_type|volume|
»» measurement_unit|inch|
»» measurement_unit|cm|
»» weight_unit|lb|
»» weight_unit|kg|
»» commodity_type|skid|
»» commodity_type|other|

> Example responses

```json
{
  "order": {
    "id": "string",
    "sequence_id": 0,
    "external_id": "string",
    "public_id": "string",
    "customer": {
      "id": "string",
      "external_id": "string",
      "short_code": "string"
    },
    "origin": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "destination": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "billing": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "status": "new",
    "billing_option": "prepaid",
    "notes": "string",
    "po_num": "string",
    "tender_num": "string",
    "ref_num": "string",
    "custom_broker": "string",
    "declared_value": 0,
    "declared_value_currency": "cad",
    "pickup_start_at": "2018-09-19T05:22:07Z",
    "pickup_end_at": "2018-09-19T05:22:07Z",
    "pickup_appt_start_at": "2018-09-19T05:22:07Z",
    "pickup_appt_end_at": "2018-09-19T05:22:07Z",
    "delivery_start_at": "2018-09-19T05:22:07Z",
    "delivery_end_at": "2018-09-19T05:22:07Z",
    "delivery_appt_start_at": "2018-09-19T05:22:07Z",
    "delivery_appt_end_at": "2018-09-19T05:22:07Z",
    "dim_type": "ltl",
    "commodities": [
      {
        "id": "string",
        "measurement_unit": "inch",
        "weight_unit": "lb",
        "freight_class": "string",
        "commodity_type": "skid",
        "commodity_type_other": "string",
        "description": "string",
        "feet": 0,
        "volume": 0,
        "length": 0,
        "width": 0,
        "height": 0,
        "weight": 0,
        "nmfc": "string",
        "is_stackable": true,
        "quantity": 0,
        "pieces": 0,
        "sku": "string"
      }
    ],
    "accessorials": [
      "string"
    ]
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="updateOrderByID-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="updateOrderByID-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
order|[Order](#schemaorder)|false|Customer's order
» id|string(uuid)|false|Auto generated system ID
» sequence_id|integer|false|Auto generated sequence ID per customer
» external_id|string|false|External ID for mapping the order to an external system. This field value can be _null_
» public_id|string|false|Auto generated human readable ID
» customer|[OrderCustomer](#schemaordercustomer)|false|Customer
»» id|string(uuid)|false|Auto generated customer id
»» external_id|string|false|Customer external id. This field value can be _null_
»» short_code|string|false|Customer's short code
» origin|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
» destination|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
» billing|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
» status|string|false|Order Status
» billing_option|string|false|Billing Option
» notes|string|false|Notes that will appear on BOL
» po_num|string|false|Purchase order numbers (if multiple use comma separated values)
» tender_num|string|false|Tender number
» ref_num|string|false|Reference number
» custom_broker|string|false|Custom broker information
» declared_value|number(float)|false|Declared value
» declared_value_currency|string|false|Declared value currency
» pickup_start_at|string(date-time)|false|Pickup time range (start)
» pickup_end_at|string(date-time)|false|Pickup time range (end)
» pickup_appt_start_at|string(date-time)|false|Pickup appointment time range (start). This field value can be _null_
» pickup_appt_end_at|string(date-time)|false|Pickup appointment time range (end). This field value can be _null_
» delivery_start_at|string(date-time)|false|Expected delivery time range (start). This field value can be _null_
» delivery_end_at|string(date-time)|false|Expected delivery time range (end). This field value can be _null_
» delivery_appt_start_at|string(date-time)|false|Delivery appointment time range (start). This field value can be _null_
» delivery_appt_end_at|string(date-time)|false|Delivery appointment time range (end). This field value can be _null_
» dim_type|string|false|Dimension type
» commodities|[[Commodity](#schemacommodity)]|false|Commodities items
»» id|string(uuid)|false|Auto generated commodity id
»» measurement_unit|string|false|Measurement unit
»» weight_unit|string|false|Weight unit
»» freight_class|string|false|Freight class
»» commodity_type|string|false|Commodity type
»» commodity_type_other|string|false|If commodity type is set to _other_, then this field must have value
»» description|string|false|Description of the commodity
»» feet|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»» volume|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»» length|number(float)|false|Length of the commodity
»» width|number(float)|false|Width of the commodity
»» height|number(float)|false|Height of the commodity
»» weight|number(float)|false|Weight of the commodity
»» nmfc|string|false|NMFC number
»» is_stackable|boolean|false|Is this commodity can be stacked?
»» quantity|integer|false|Quantity of the commodity
»» pieces|integer|false|Total number of pieces. This field value can be _null_
»» sku|string|false|SKU number
» accessorials|[string(uuid)]|false|No description



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: orders )
</aside>

## deleteOrderByID

> Code samples

```shell
# You can also use wget
curl -X DELETE https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID} \
  -H 'Accept: application/json'

```

```http
DELETE https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID} HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`DELETE /customers/{customerID}/orders/{orderID}`

*Delete customer's order by ID*

<h3 id="deleteOrderByID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.
orderID|path|string(uuid)|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.


> Example responses

```json
{
  "order": {
    "id": "string",
    "sequence_id": 0,
    "external_id": "string",
    "public_id": "string",
    "customer": {
      "id": "string",
      "external_id": "string",
      "short_code": "string"
    },
    "origin": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "destination": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "billing": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "status": "new",
    "billing_option": "prepaid",
    "notes": "string",
    "po_num": "string",
    "tender_num": "string",
    "ref_num": "string",
    "custom_broker": "string",
    "declared_value": 0,
    "declared_value_currency": "cad",
    "pickup_start_at": "2018-09-19T05:22:07Z",
    "pickup_end_at": "2018-09-19T05:22:07Z",
    "pickup_appt_start_at": "2018-09-19T05:22:07Z",
    "pickup_appt_end_at": "2018-09-19T05:22:07Z",
    "delivery_start_at": "2018-09-19T05:22:07Z",
    "delivery_end_at": "2018-09-19T05:22:07Z",
    "delivery_appt_start_at": "2018-09-19T05:22:07Z",
    "delivery_appt_end_at": "2018-09-19T05:22:07Z",
    "dim_type": "ltl",
    "commodities": [
      {
        "id": "string",
        "measurement_unit": "inch",
        "weight_unit": "lb",
        "freight_class": "string",
        "commodity_type": "skid",
        "commodity_type_other": "string",
        "description": "string",
        "feet": 0,
        "volume": 0,
        "length": 0,
        "width": 0,
        "height": 0,
        "weight": 0,
        "nmfc": "string",
        "is_stackable": true,
        "quantity": 0,
        "pieces": 0,
        "sku": "string"
      }
    ],
    "accessorials": [
      "string"
    ]
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="deleteOrderByID-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="deleteOrderByID-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
order|[Order](#schemaorder)|false|Customer's order
» id|string(uuid)|false|Auto generated system ID
» sequence_id|integer|false|Auto generated sequence ID per customer
» external_id|string|false|External ID for mapping the order to an external system. This field value can be _null_
» public_id|string|false|Auto generated human readable ID
» customer|[OrderCustomer](#schemaordercustomer)|false|Customer
»» id|string(uuid)|false|Auto generated customer id
»» external_id|string|false|Customer external id. This field value can be _null_
»» short_code|string|false|Customer's short code
» origin|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
» destination|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
» billing|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
» status|string|false|Order Status
» billing_option|string|false|Billing Option
» notes|string|false|Notes that will appear on BOL
» po_num|string|false|Purchase order numbers (if multiple use comma separated values)
» tender_num|string|false|Tender number
» ref_num|string|false|Reference number
» custom_broker|string|false|Custom broker information
» declared_value|number(float)|false|Declared value
» declared_value_currency|string|false|Declared value currency
» pickup_start_at|string(date-time)|false|Pickup time range (start)
» pickup_end_at|string(date-time)|false|Pickup time range (end)
» pickup_appt_start_at|string(date-time)|false|Pickup appointment time range (start). This field value can be _null_
» pickup_appt_end_at|string(date-time)|false|Pickup appointment time range (end). This field value can be _null_
» delivery_start_at|string(date-time)|false|Expected delivery time range (start). This field value can be _null_
» delivery_end_at|string(date-time)|false|Expected delivery time range (end). This field value can be _null_
» delivery_appt_start_at|string(date-time)|false|Delivery appointment time range (start). This field value can be _null_
» delivery_appt_end_at|string(date-time)|false|Delivery appointment time range (end). This field value can be _null_
» dim_type|string|false|Dimension type
» commodities|[[Commodity](#schemacommodity)]|false|Commodities items
»» id|string(uuid)|false|Auto generated commodity id
»» measurement_unit|string|false|Measurement unit
»» weight_unit|string|false|Weight unit
»» freight_class|string|false|Freight class
»» commodity_type|string|false|Commodity type
»» commodity_type_other|string|false|If commodity type is set to _other_, then this field must have value
»» description|string|false|Description of the commodity
»» feet|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»» volume|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»» length|number(float)|false|Length of the commodity
»» width|number(float)|false|Width of the commodity
»» height|number(float)|false|Height of the commodity
»» weight|number(float)|false|Weight of the commodity
»» nmfc|string|false|NMFC number
»» is_stackable|boolean|false|Is this commodity can be stacked?
»» quantity|integer|false|Quantity of the commodity
»» pieces|integer|false|Total number of pieces. This field value can be _null_
»» sku|string|false|SKU number
» accessorials|[string(uuid)]|false|No description



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: orders )
</aside>

## createBookedOrder

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/customers/{customerID}/create_booked_order \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST https://platform.roserocket.com/v1/customers/{customerID}/create_booked_order HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerID}/create_booked_order',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "external_id": "string",
  "customer": {},
  "origin": {
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  },
  "destination": {
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  },
  "billing": {
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  },
  "billing_option": "prepaid",
  "notes": "string",
  "po_num": "string",
  "tender_num": "string",
  "ref_num": "string",
  "custom_broker": "string",
  "declared_value": 0,
  "declared_value_currency": "cad",
  "pickup_start_at": "2018-09-19T05:22:07Z",
  "pickup_end_at": "2018-09-19T05:22:07Z",
  "pickup_appt_start_at": "2018-09-19T05:22:07Z",
  "pickup_appt_end_at": "2018-09-19T05:22:07Z",
  "delivery_start_at": "2018-09-19T05:22:07Z",
  "delivery_end_at": "2018-09-19T05:22:07Z",
  "delivery_appt_start_at": "2018-09-19T05:22:07Z",
  "delivery_appt_end_at": "2018-09-19T05:22:07Z",
  "dim_type": "ltl",
  "commodities": [
    {
      "measurement_unit": "inch",
      "weight_unit": "lb",
      "freight_class": "string",
      "commodity_type": "skid",
      "commodity_type_other": "string",
      "description": "string",
      "feet": 0,
      "volume": 0,
      "length": 0,
      "width": 0,
      "height": 0,
      "weight": 0,
      "nmfc": "string",
      "is_stackable": true,
      "quantity": 0,
      "pieces": 0,
      "sku": "string"
    }
  ],
  "accessorials": [
    "string"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers/{customerID}/create_booked_order',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'https://platform.roserocket.com/v1/customers/{customerID}/create_booked_order',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('https://platform.roserocket.com/v1/customers/{customerID}/create_booked_order', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerID}/create_booked_order");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /customers/{customerID}/create_booked_order`

*Create a booked order*

> Body parameter

```json
{
  "external_id": "string",
  "customer": {},
  "origin": {
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  },
  "destination": {
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  },
  "billing": {
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  },
  "billing_option": "prepaid",
  "notes": "string",
  "po_num": "string",
  "tender_num": "string",
  "ref_num": "string",
  "custom_broker": "string",
  "declared_value": 0,
  "declared_value_currency": "cad",
  "pickup_start_at": "2018-09-19T05:22:07Z",
  "pickup_end_at": "2018-09-19T05:22:07Z",
  "pickup_appt_start_at": "2018-09-19T05:22:07Z",
  "pickup_appt_end_at": "2018-09-19T05:22:07Z",
  "delivery_start_at": "2018-09-19T05:22:07Z",
  "delivery_end_at": "2018-09-19T05:22:07Z",
  "delivery_appt_start_at": "2018-09-19T05:22:07Z",
  "delivery_appt_end_at": "2018-09-19T05:22:07Z",
  "dim_type": "ltl",
  "commodities": [
    {
      "measurement_unit": "inch",
      "weight_unit": "lb",
      "freight_class": "string",
      "commodity_type": "skid",
      "commodity_type_other": "string",
      "description": "string",
      "feet": 0,
      "volume": 0,
      "length": 0,
      "width": 0,
      "height": 0,
      "weight": 0,
      "nmfc": "string",
      "is_stackable": true,
      "quantity": 0,
      "pieces": 0,
      "sku": "string"
    }
  ],
  "accessorials": [
    "string"
  ]
}
```
<h3 id="createBookedOrder-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
customerID|path|string(uuid)|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.
body|body|[Order](#schemaorder)|true|Order object
» id|body|string(uuid)|false|Auto generated system ID
» sequence_id|body|integer|false|Auto generated sequence ID per customer
» external_id|body|string|false|External ID for mapping the order to an external system. This field value can be _null_
» public_id|body|string|false|Auto generated human readable ID
» customer|body|[OrderCustomer](#schemaordercustomer)|false|Customer
»» id|body|string(uuid)|false|Auto generated customer id
»» external_id|body|string|false|Customer external id. This field value can be _null_
»» short_code|body|string|false|Customer's short code
» origin|body|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|body|string|false|Organization name
»» contact_name|body|string|false|Contact name
»» address_1|body|string|false|Address line 1
»» address_2|body|string|false|Address line 2
»» suite|body|string|false|Suite number
»» city|body|string|false|City
»» state|body|string|false|State / Province
»» country|body|string|false|Country (2 letter ISO)
»» postal|body|string|false|Postal / Zip code
»» phone|body|string|false|Phone number
»» phone_ext|body|string|false|Phone extension
»» email|body|string|false|Email
»» fax|body|string|false|Fax
»» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|body|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|body|string(date-time)|false|Business hours range (end). This field value can be _null_
» destination|body|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|body|string|false|Organization name
»» contact_name|body|string|false|Contact name
»» address_1|body|string|false|Address line 1
»» address_2|body|string|false|Address line 2
»» suite|body|string|false|Suite number
»» city|body|string|false|City
»» state|body|string|false|State / Province
»» country|body|string|false|Country (2 letter ISO)
»» postal|body|string|false|Postal / Zip code
»» phone|body|string|false|Phone number
»» phone_ext|body|string|false|Phone extension
»» email|body|string|false|Email
»» fax|body|string|false|Fax
»» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|body|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|body|string(date-time)|false|Business hours range (end). This field value can be _null_
» billing|body|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|body|string|false|Organization name
»» contact_name|body|string|false|Contact name
»» address_1|body|string|false|Address line 1
»» address_2|body|string|false|Address line 2
»» suite|body|string|false|Suite number
»» city|body|string|false|City
»» state|body|string|false|State / Province
»» country|body|string|false|Country (2 letter ISO)
»» postal|body|string|false|Postal / Zip code
»» phone|body|string|false|Phone number
»» phone_ext|body|string|false|Phone extension
»» email|body|string|false|Email
»» fax|body|string|false|Fax
»» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|body|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|body|string(date-time)|false|Business hours range (end). This field value can be _null_
» status|body|string|false|Order Status
» billing_option|body|string|false|Billing Option
» notes|body|string|false|Notes that will appear on BOL
» po_num|body|string|false|Purchase order numbers (if multiple use comma separated values)
» tender_num|body|string|false|Tender number
» ref_num|body|string|false|Reference number
» custom_broker|body|string|false|Custom broker information
» declared_value|body|number(float)|false|Declared value
» declared_value_currency|body|string|false|Declared value currency
» pickup_start_at|body|string(date-time)|false|Pickup time range (start)
» pickup_end_at|body|string(date-time)|false|Pickup time range (end)
» pickup_appt_start_at|body|string(date-time)|false|Pickup appointment time range (start). This field value can be _null_
» pickup_appt_end_at|body|string(date-time)|false|Pickup appointment time range (end). This field value can be _null_
» delivery_start_at|body|string(date-time)|false|Expected delivery time range (start). This field value can be _null_
» delivery_end_at|body|string(date-time)|false|Expected delivery time range (end). This field value can be _null_
» delivery_appt_start_at|body|string(date-time)|false|Delivery appointment time range (start). This field value can be _null_
» delivery_appt_end_at|body|string(date-time)|false|Delivery appointment time range (end). This field value can be _null_
» dim_type|body|string|false|Dimension type
» commodities|body|[[Commodity](#schemacommodity)]|false|Commodities items
»» id|body|string(uuid)|false|Auto generated commodity id
»» measurement_unit|body|string|false|Measurement unit
»» weight_unit|body|string|false|Weight unit
»» freight_class|body|string|false|Freight class
»» commodity_type|body|string|false|Commodity type
»» commodity_type_other|body|string|false|If commodity type is set to _other_, then this field must have value
»» description|body|string|false|Description of the commodity
»» feet|body|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»» volume|body|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»» length|body|number(float)|false|Length of the commodity
»» width|body|number(float)|false|Width of the commodity
»» height|body|number(float)|false|Height of the commodity
»» weight|body|number(float)|false|Weight of the commodity
»» nmfc|body|string|false|NMFC number
»» is_stackable|body|boolean|false|Is this commodity can be stacked?
»» quantity|body|integer|false|Quantity of the commodity
»» pieces|body|integer|false|Total number of pieces. This field value can be _null_
»» sku|body|string|false|SKU number
» accessorials|body|[string(uuid)]|false|No description


#### Enumerated Values

|Parameter|Value|
|---|---|
» status|new|
» status|saved|
» status|cancelled|
» status|quoting|
» status|quoted|
» status|no-quote|
» status|spot-quote-requested|
» status|pending-dispatch|
» status|dispatched|
» status|in-transit|
» status|delivered|
» status|archived|
» status|invoice-created|
» status|invoice-sent|
» status|invoice-paid|
» status|claim|
» status|draft-quick-quote|
» status|quick-quoting|
» status|quick-quoted|
» status|no-quick-quote|
» status|spot-qq-requested|
» status|pickup-request|
» status|rejected|
» billing_option|prepaid|
» billing_option|collect|
» billing_option|thirdparty|
» declared_value_currency|cad|
» declared_value_currency|usd|
» dim_type|ltl|
» dim_type|ftl|
» dim_type|volume|
»» measurement_unit|inch|
»» measurement_unit|cm|
»» weight_unit|lb|
»» weight_unit|kg|
»» commodity_type|skid|
»» commodity_type|other|

> Example responses

```json
{
  "order": {
    "id": "string",
    "sequence_id": 0,
    "external_id": "string",
    "public_id": "string",
    "customer": {
      "id": "string",
      "external_id": "string",
      "short_code": "string"
    },
    "origin": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "destination": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "billing": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "status": "new",
    "billing_option": "prepaid",
    "notes": "string",
    "po_num": "string",
    "tender_num": "string",
    "ref_num": "string",
    "custom_broker": "string",
    "declared_value": 0,
    "declared_value_currency": "cad",
    "pickup_start_at": "2018-09-19T05:22:07Z",
    "pickup_end_at": "2018-09-19T05:22:07Z",
    "pickup_appt_start_at": "2018-09-19T05:22:07Z",
    "pickup_appt_end_at": "2018-09-19T05:22:07Z",
    "delivery_start_at": "2018-09-19T05:22:07Z",
    "delivery_end_at": "2018-09-19T05:22:07Z",
    "delivery_appt_start_at": "2018-09-19T05:22:07Z",
    "delivery_appt_end_at": "2018-09-19T05:22:07Z",
    "dim_type": "ltl",
    "commodities": [
      {
        "id": "string",
        "measurement_unit": "inch",
        "weight_unit": "lb",
        "freight_class": "string",
        "commodity_type": "skid",
        "commodity_type_other": "string",
        "description": "string",
        "feet": 0,
        "volume": 0,
        "length": 0,
        "width": 0,
        "height": 0,
        "weight": 0,
        "nmfc": "string",
        "is_stackable": true,
        "quantity": 0,
        "pieces": 0,
        "sku": "string"
      }
    ],
    "accessorials": [
      "string"
    ]
  },
  "legs": [
    {
      "id": "string",
      "sequence_id": 0,
      "version": 0,
      "external_id": "string",
      "public_id": "string",
      "order_id": "string",
      "manifest_id": "string",
      "origin_stop_id": "string",
      "destination_stop_id": "string",
      "origin": {
        "terminal_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0
      },
      "destination": {
        "terminal_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0
      },
      "status": "available",
      "origin_start_at": "2018-09-19T05:22:07Z",
      "origin_end_at": "2018-09-19T05:22:07Z",
      "origin_appt_start_at": "2018-09-19T05:22:07Z",
      "origin_appt_end_at": "2018-09-19T05:22:07Z",
      "destination_start_at": "2018-09-19T05:22:07Z",
      "destination_end_at": "2018-09-19T05:22:07Z",
      "destination_appt_start_at": "2018-09-19T05:22:07Z",
      "destination_appt_end_at": "2018-09-19T05:22:07Z",
      "commodities": [
        {
          "id": "string",
          "measurement_unit": "inch",
          "weight_unit": "lb",
          "freight_class": "string",
          "commodity_type": "skid",
          "commodity_type_other": "string",
          "description": "string",
          "feet": 0,
          "volume": 0,
          "length": 0,
          "width": 0,
          "height": 0,
          "weight": 0,
          "nmfc": "string",
          "is_stackable": true,
          "quantity": 0,
          "pieces": 0,
          "sku": "string"
        }
      ],
      "accessorials": [
        "string"
      ],
      "history": {
        "origin_arrived_at": "2018-09-19T05:22:07Z",
        "origin_in_at": "2018-09-19T05:22:07Z",
        "origin_pickedup_at": "2018-09-19T05:22:07Z",
        "origin_out_at": "2018-09-19T05:22:07Z",
        "destination_arrived_at": "2018-09-19T05:22:07Z",
        "destination_in_at": "2018-09-19T05:22:07Z",
        "destination_delivered_at": "2018-09-19T05:22:07Z",
        "destination_out_at": "2018-09-19T05:22:07Z"
      }
    }
  ]
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="createBookedOrder-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="createBookedOrder-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
order|[Order](#schemaorder)|false|Customer's order
» id|string(uuid)|false|Auto generated system ID
» sequence_id|integer|false|Auto generated sequence ID per customer
» external_id|string|false|External ID for mapping the order to an external system. This field value can be _null_
» public_id|string|false|Auto generated human readable ID
» customer|[OrderCustomer](#schemaordercustomer)|false|Customer
»» id|string(uuid)|false|Auto generated customer id
»» external_id|string|false|Customer external id. This field value can be _null_
»» short_code|string|false|Customer's short code
» origin|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
» destination|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
» billing|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
» status|string|false|Order Status
» billing_option|string|false|Billing Option
» notes|string|false|Notes that will appear on BOL
» po_num|string|false|Purchase order numbers (if multiple use comma separated values)
» tender_num|string|false|Tender number
» ref_num|string|false|Reference number
» custom_broker|string|false|Custom broker information
» declared_value|number(float)|false|Declared value
» declared_value_currency|string|false|Declared value currency
» pickup_start_at|string(date-time)|false|Pickup time range (start)
» pickup_end_at|string(date-time)|false|Pickup time range (end)
» pickup_appt_start_at|string(date-time)|false|Pickup appointment time range (start). This field value can be _null_
» pickup_appt_end_at|string(date-time)|false|Pickup appointment time range (end). This field value can be _null_
» delivery_start_at|string(date-time)|false|Expected delivery time range (start). This field value can be _null_
» delivery_end_at|string(date-time)|false|Expected delivery time range (end). This field value can be _null_
» delivery_appt_start_at|string(date-time)|false|Delivery appointment time range (start). This field value can be _null_
» delivery_appt_end_at|string(date-time)|false|Delivery appointment time range (end). This field value can be _null_
» dim_type|string|false|Dimension type
» commodities|[[Commodity](#schemacommodity)]|false|Commodities items
»» id|string(uuid)|false|Auto generated commodity id
»» measurement_unit|string|false|Measurement unit
»» weight_unit|string|false|Weight unit
»» freight_class|string|false|Freight class
»» commodity_type|string|false|Commodity type
»» commodity_type_other|string|false|If commodity type is set to _other_, then this field must have value
»» description|string|false|Description of the commodity
»» feet|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»» volume|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»» length|number(float)|false|Length of the commodity
»» width|number(float)|false|Width of the commodity
»» height|number(float)|false|Height of the commodity
»» weight|number(float)|false|Weight of the commodity
»» nmfc|string|false|NMFC number
»» is_stackable|boolean|false|Is this commodity can be stacked?
»» quantity|integer|false|Quantity of the commodity
»» pieces|integer|false|Total number of pieces. This field value can be _null_
»» sku|string|false|SKU number
» accessorials|[string(uuid)]|false|No description
legs|[[Leg](#schemaleg)]|false|No description
» id|string(uuid)|false|Auto generated system ID
» sequence_id|integer|false|Auto generated sequence ID per customer
» version|integer|false|Auto generated version number (incremental)
» external_id|string|false|External ID for mapping the leg to an external system. This field value can be _null_
» public_id|string|false|Auto generated human readable ID
» order_id|string|false|Related order ID
» manifest_id|string|false|Related manifest ID (assigned). This field value can be _null_
» origin_stop_id|string|false|Stop ID of the origin (only if this leg has been assigned to a manifest). This field value can be _null_
» destination_stop_id|string|false|Stop ID of the destination (only if this leg has been assigned to a manifest). This field value can be _null_
» origin|[LegAddress](#schemalegaddress)|false|Leg address
»» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» destination|[LegAddress](#schemalegaddress)|false|Leg address
»» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» status|string|false|Leg Status
» origin_start_at|string(date-time)|false|Origin ready time range (start)
» origin_end_at|string(date-time)|false|Origin ready time range (end)
» origin_appt_start_at|string(date-time)|false|Origin appointment time range (start). This field value can be _null_
» origin_appt_end_at|string(date-time)|false|Origin appointment time range (end). This field value can be _null_
» destination_start_at|string(date-time)|false|Destination expected time range (start). This field value can be _null_
» destination_end_at|string(date-time)|false|Destination expected time range (end). This field value can be _null_
» destination_appt_start_at|string(date-time)|false|Destination appointment time range (start). This field value can be _null_
» destination_appt_end_at|string(date-time)|false|Destination appointment time range (end). This field value can be _null_
» history|[LegHistory](#schemaleghistory)|false|Historical timestamps of a leg
»» origin_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at origin
»» origin_in_at|string(date-time)|false|The timestamp of when the driver/partner in at origin
»» origin_pickedup_at|string(date-time)|false|The timestamp of when the driver/partner picked up at origin
»» origin_out_at|string(date-time)|false|The timestamp of when the driver/partner out at origin
»» destination_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at destination
»» destination_in_at|string(date-time)|false|The timestamp of when the driver/partner in at destination
»» destination_delivered_at|string(date-time)|false|The timestamp of when the driver/partner delievered up at destination
»» destination_out_at|string(date-time)|false|The timestamp of when the driver/partner out at destination
» commodities|[[Commodity](#schemacommodity)]|false|Commodities items
»» id|string(uuid)|false|Auto generated commodity id
»» measurement_unit|string|false|Measurement unit
»» weight_unit|string|false|Weight unit
»» freight_class|string|false|Freight class
»» commodity_type|string|false|Commodity type
»» commodity_type_other|string|false|If commodity type is set to _other_, then this field must have value
»» description|string|false|Description of the commodity
»» feet|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»» volume|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»» length|number(float)|false|Length of the commodity
»» width|number(float)|false|Width of the commodity
»» height|number(float)|false|Height of the commodity
»» weight|number(float)|false|Weight of the commodity
»» nmfc|string|false|NMFC number
»» is_stackable|boolean|false|Is this commodity can be stacked?
»» quantity|integer|false|Quantity of the commodity
»» pieces|integer|false|Total number of pieces. This field value can be _null_
»» sku|string|false|SKU number
» accessorials|[string(uuid)]|false|No description



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: orders )
</aside>

## getOrderFilesById

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files \
  -H 'Accept: application/json'

```

```http
GET https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /customers/{customerID}/orders/{orderID}/files`

*Get all leg files/documents for a given ID of a leg*

<h3 id="getOrderFilesById-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
orderID|path|string|true|ID of the order to get files for. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.
customerID|path|string|true|ID of the customer to of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.


> Example responses

```json
{
  "leg_files": [
    {
      "id": "string",
      "created_at": "2018-09-19T05:22:07Z",
      "updated_at": "2018-09-19T05:22:07Z",
      "org_id": "string",
      "leg_id": "string",
      "uploaded_by": "string",
      "uploaded_at": "string",
      "type": "other",
      "url": "string",
      "description": "string",
      "latitude": 0,
      "longitude": 0,
      "metadata": {}
    }
  ]
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="getOrderFilesById-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="getOrderFilesById-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
leg_files|[[OrderFile](#schemaorderfile)]|false|No description
» id|string(uuid)|false|The uuid for the order file
» created_at|string(date-time)|false|The timestamp for the creation of the order file
» updated_at|string(date-time)|false|The timestamp for the last update of the order file
» org_id|string(uuid)|false|The uuid for the organization of the order file
» leg_id|string(uuid)|false|The uuid of the order corresponding to the order file
» uploaded_by|string(uuid)|false|The uuid of the user who uploaded the order file
» uploaded_at|string(uuid)|false|The uuid
» type|string|false|The type of order file
» url|string|false|The url location for the order file
» description|string|false|A description of the order file
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» metadata|object|false|Metadata object for the order file



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: legs )
</aside>

## addOrderFileByLegId

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "type": "other",
  "url": "string",
  "description": "string",
  "latitude": 0,
  "longitude": 0,
  "metadata": {}
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /customers/{customerID}/orders/{orderID}/files`

*Add a file/document to a specified order*

> Body parameter

```json
{
  "type": "other",
  "url": "string",
  "description": "string",
  "latitude": 0,
  "longitude": 0,
  "metadata": {}
}
```
<h3 id="addOrderFileByLegId-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
orderID|path|string|true|ID of the order to get files for. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.
customerID|path|string|true|ID of the customer to of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.
body|body|[OrderFileRequest](#schemaorderfilerequest)|true|Order file create request
» type|body|string|false|The type of order file
» url|body|string|false|The url location for the order file
» description|body|string|false|A description of the order file
» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_
» metadata|body|object|false|Metadata object for the order file


#### Enumerated Values

|Parameter|Value|
|---|---|
» type|other|
» type|comm-invoice|
» type|pod|
» type|pop|
» type|pod-sig|
» type|pop-sig|
» type|carrier-invoice|
» type|smc|
» type|bol|

> Example responses

```json
{
  "leg_file": {
    "id": "string",
    "created_at": "2018-09-19T05:22:07Z",
    "updated_at": "2018-09-19T05:22:07Z",
    "org_id": "string",
    "leg_id": "string",
    "uploaded_by": "string",
    "uploaded_at": "string",
    "type": "other",
    "url": "string",
    "description": "string",
    "latitude": 0,
    "longitude": 0,
    "metadata": {}
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="addOrderFileByLegId-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="addOrderFileByLegId-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
leg_file|[OrderFile](#schemaorderfile)|false|The file for the order
» id|string(uuid)|false|The uuid for the order file
» created_at|string(date-time)|false|The timestamp for the creation of the order file
» updated_at|string(date-time)|false|The timestamp for the last update of the order file
» org_id|string(uuid)|false|The uuid for the organization of the order file
» leg_id|string(uuid)|false|The uuid of the order corresponding to the order file
» uploaded_by|string(uuid)|false|The uuid of the user who uploaded the order file
» uploaded_at|string(uuid)|false|The uuid
» type|string|false|The type of order file
» url|string|false|The url location for the order file
» description|string|false|A description of the order file
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» metadata|object|false|Metadata object for the order file



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: legs )
</aside>

## updateFileByOrderAndFileID

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files/{fileID} \
  -H 'Content-Type: multipart/form-data' \
  -H 'Accept: application/json'

```

```http
PUT https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files/{fileID} HTTP/1.1
Host: platform.roserocket.com
Content-Type: multipart/form-data
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files/{fileID}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "type": "other",
  "url": "string",
  "description": "string",
  "latitude": 0,
  "longitude": 0,
  "metadata": {}
}';
const headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files/{fileID}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'multipart/form-data',
  'Accept' => 'application/json'
}

result = RestClient.put 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files/{fileID}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'Accept': 'application/json'
}

r = requests.put('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files/{fileID}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files/{fileID}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /customers/{customerID}/orders/{orderID}/files/{fileID}`

*Update a file for a specified order*

> Body parameter

```yaml
type: other
url: string
description: string
latitude: 0
longitude: 0
metadata: {}

```
<h3 id="updateFileByOrderAndFileID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
orderID|path|string|true|ID of the order to get files for. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.
fileID|path|string|true|ID of the order file.
customerID|path|string|true|ID of the customer to of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.
body|body|[OrderFileRequest](#schemaorderfilerequest)|true|Order file create request
» type|body|string|false|The type of order file
» url|body|string|false|The url location for the order file
» description|body|string|false|A description of the order file
» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_
» metadata|body|object|false|Metadata object for the order file


#### Enumerated Values

|Parameter|Value|
|---|---|
» type|other|
» type|comm-invoice|
» type|pod|
» type|pop|
» type|pod-sig|
» type|pop-sig|
» type|carrier-invoice|
» type|smc|
» type|bol|

> Example responses

```json
{
  "leg_file": {
    "id": "string",
    "created_at": "2018-09-19T05:22:07Z",
    "updated_at": "2018-09-19T05:22:07Z",
    "org_id": "string",
    "leg_id": "string",
    "uploaded_by": "string",
    "uploaded_at": "string",
    "type": "other",
    "url": "string",
    "description": "string",
    "latitude": 0,
    "longitude": 0,
    "metadata": {}
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="updateFileByOrderAndFileID-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="updateFileByOrderAndFileID-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
leg_file|[OrderFile](#schemaorderfile)|false|The file for the order
» id|string(uuid)|false|The uuid for the order file
» created_at|string(date-time)|false|The timestamp for the creation of the order file
» updated_at|string(date-time)|false|The timestamp for the last update of the order file
» org_id|string(uuid)|false|The uuid for the organization of the order file
» leg_id|string(uuid)|false|The uuid of the order corresponding to the order file
» uploaded_by|string(uuid)|false|The uuid of the user who uploaded the order file
» uploaded_at|string(uuid)|false|The uuid
» type|string|false|The type of order file
» url|string|false|The url location for the order file
» description|string|false|A description of the order file
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» metadata|object|false|Metadata object for the order file



<aside class="success">
This operation does not require authentication
</aside>

## deleteFileByOrderAndFileID

> Code samples

```shell
# You can also use wget
curl -X DELETE https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files/{fileID} \
  -H 'Accept: application/json'

```

```http
DELETE https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files/{fileID} HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files/{fileID}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files/{fileID}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files/{fileID}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files/{fileID}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files/{fileID}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`DELETE /customers/{customerID}/orders/{orderID}/files/{fileID}`

*Delete a file for a specified order*

<h3 id="deleteFileByOrderAndFileID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
orderID|path|string|true|ID of the order to get files for. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.
fileID|path|string|true|ID of the order file.
customerID|path|string|true|ID of the customer to of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.


> Example responses

```json
{
  "Message": "Success"
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="deleteFileByOrderAndFileID-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="deleteFileByOrderAndFileID-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
Message|string|false|No description



<aside class="success">
This operation does not require authentication
</aside>

## uploadOrderBOL

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/upload_bol \
  -H 'Content-Type: multipart/form-data' \
  -H 'Accept: application/json'

```

```http
POST https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/upload_bol HTTP/1.1
Host: platform.roserocket.com
Content-Type: multipart/form-data
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/upload_bol',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "file": "string"
}';
const headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/upload_bol',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'multipart/form-data',
  'Accept' => 'application/json'
}

result = RestClient.post 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/upload_bol',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'Accept': 'application/json'
}

r = requests.post('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/upload_bol', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/upload_bol");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /customers/{customerID}/orders/{orderID}/upload_bol`

*Upload BOL for a specified order*

> Body parameter

```yaml
file: string

```
<h3 id="uploadOrderBOL-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
orderID|path|string|true|ID of the order to get files for. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.
customerID|path|string|true|ID of the customer to of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.
body|body|[uploadLegBOLByLegID](#schema+uploadlegbolbylegid)|false|No description
» file|body|string(binary)|true|File to upload


> Example responses

```json
{
  "order_file": {
    "id": "string",
    "created_at": "2018-09-19T05:22:07Z",
    "updated_at": "2018-09-19T05:22:07Z",
    "org_id": "string",
    "leg_id": "string",
    "uploaded_by": "string",
    "uploaded_at": "string",
    "type": "other",
    "url": "string",
    "description": "string",
    "latitude": 0,
    "longitude": 0,
    "metadata": {}
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="uploadOrderBOL-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="uploadOrderBOL-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
order_file|[OrderFile](#schemaorderfile)|false|The file for the order
» id|string(uuid)|false|The uuid for the order file
» created_at|string(date-time)|false|The timestamp for the creation of the order file
» updated_at|string(date-time)|false|The timestamp for the last update of the order file
» org_id|string(uuid)|false|The uuid for the organization of the order file
» leg_id|string(uuid)|false|The uuid of the order corresponding to the order file
» uploaded_by|string(uuid)|false|The uuid of the user who uploaded the order file
» uploaded_at|string(uuid)|false|The uuid
» type|string|false|The type of order file
» url|string|false|The url location for the order file
» description|string|false|A description of the order file
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» metadata|object|false|Metadata object for the order file



<aside class="success">
This operation does not require authentication
</aside>

## uploadOrderFile

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/upload_file \
  -H 'Content-Type: multipart/form-data' \
  -H 'Accept: application/json'

```

```http
POST https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/upload_file HTTP/1.1
Host: platform.roserocket.com
Content-Type: multipart/form-data
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/upload_file',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "file": "string",
  "type": "other"
}';
const headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/upload_file',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'multipart/form-data',
  'Accept' => 'application/json'
}

result = RestClient.post 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/upload_file',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'Accept': 'application/json'
}

r = requests.post('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/upload_file', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/upload_file");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /customers/{customerID}/orders/{orderID}/upload_file`

*Upload file for a specified order*

> Body parameter

```yaml
file: string
type: other

```
<h3 id="uploadOrderFile-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
orderID|path|string|true|ID of the order to get files for. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.
customerID|path|string|true|ID of the customer to of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.
body|body|[uploadOrderFile](#schema+uploadorderfile)|false|No description
» file|body|string(binary)|true|File to upload
» type|body|string|false|Type of order file to upload


#### Enumerated Values

|Parameter|Value|
|---|---|
» type|other|
» type|comm-invoice|
» type|pod|
» type|pop|
» type|pod-sig|
» type|pop-sig|
» type|carrier-invoice|
» type|smc|
» type|bol|

> Example responses

```json
{
  "order_file": {
    "id": "string",
    "created_at": "2018-09-19T05:22:07Z",
    "updated_at": "2018-09-19T05:22:07Z",
    "org_id": "string",
    "leg_id": "string",
    "uploaded_by": "string",
    "uploaded_at": "string",
    "type": "other",
    "url": "string",
    "description": "string",
    "latitude": 0,
    "longitude": 0,
    "metadata": {}
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="uploadOrderFile-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="uploadOrderFile-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
order_file|[OrderFile](#schemaorderfile)|false|The file for the order
» id|string(uuid)|false|The uuid for the order file
» created_at|string(date-time)|false|The timestamp for the creation of the order file
» updated_at|string(date-time)|false|The timestamp for the last update of the order file
» org_id|string(uuid)|false|The uuid for the organization of the order file
» leg_id|string(uuid)|false|The uuid of the order corresponding to the order file
» uploaded_by|string(uuid)|false|The uuid of the user who uploaded the order file
» uploaded_at|string(uuid)|false|The uuid
» type|string|false|The type of order file
» url|string|false|The url location for the order file
» description|string|false|A description of the order file
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» metadata|object|false|Metadata object for the order file



<aside class="success">
This operation does not require authentication
</aside>

## updateOrderFile

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/upload_file/{fileID} \
  -H 'Content-Type: multipart/form-data' \
  -H 'Accept: application/json'

```

```http
PUT https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/upload_file/{fileID} HTTP/1.1
Host: platform.roserocket.com
Content-Type: multipart/form-data
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/upload_file/{fileID}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "file": "string",
  "type": "other"
}';
const headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/upload_file/{fileID}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'multipart/form-data',
  'Accept' => 'application/json'
}

result = RestClient.put 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/upload_file/{fileID}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'Accept': 'application/json'
}

r = requests.put('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/upload_file/{fileID}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/upload_file/{fileID}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /customers/{customerID}/orders/{orderID}/upload_file/{fileID}`

*Update an uploaded file for a specified order*

> Body parameter

```yaml
file: string
type: other

```
<h3 id="updateOrderFile-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
orderID|path|string|true|ID of the order to get files for. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.
fileID|path|string|true|ID of the order file.
customerID|path|string|true|ID of the customer to of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.
body|body|[uploadOrderFile](#schema+uploadorderfile)|false|No description
» file|body|string(binary)|true|File to upload
» type|body|string|false|Type of order file to upload


#### Enumerated Values

|Parameter|Value|
|---|---|
» type|other|
» type|comm-invoice|
» type|pod|
» type|pop|
» type|pod-sig|
» type|pop-sig|
» type|carrier-invoice|
» type|smc|
» type|bol|

> Example responses

```json
{
  "order_file": {
    "id": "string",
    "created_at": "2018-09-19T05:22:07Z",
    "updated_at": "2018-09-19T05:22:07Z",
    "org_id": "string",
    "leg_id": "string",
    "uploaded_by": "string",
    "uploaded_at": "string",
    "type": "other",
    "url": "string",
    "description": "string",
    "latitude": 0,
    "longitude": 0,
    "metadata": {}
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="updateOrderFile-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="updateOrderFile-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
order_file|[OrderFile](#schemaorderfile)|false|The file for the order
» id|string(uuid)|false|The uuid for the order file
» created_at|string(date-time)|false|The timestamp for the creation of the order file
» updated_at|string(date-time)|false|The timestamp for the last update of the order file
» org_id|string(uuid)|false|The uuid for the organization of the order file
» leg_id|string(uuid)|false|The uuid of the order corresponding to the order file
» uploaded_by|string(uuid)|false|The uuid of the user who uploaded the order file
» uploaded_at|string(uuid)|false|The uuid
» type|string|false|The type of order file
» url|string|false|The url location for the order file
» description|string|false|A description of the order file
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» metadata|object|false|Metadata object for the order file



<aside class="success">
This operation does not require authentication
</aside>

# leg

## searchLegs

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/legs \
  -H 'Accept: application/json'

```

```http
GET https://platform.roserocket.com/v1/legs HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/legs',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/legs',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://platform.roserocket.com/v1/legs',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://platform.roserocket.com/v1/legs', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/legs");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /legs`

*Search legs*

<h3 id="searchLegs-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
created_start_at|query|string(date-time)|false|Date range (start)
created_end_at|query|string(date-time)|false|Date range (end)
search_term|query|string|false|Search term
external_id|query|string|false|External ID to filter by
offset|query|integer|false|Pagination offset
limit|query|integer|false|Pagination limit


> Example responses

```json
{
  "legs": [
    {
      "id": "string",
      "sequence_id": 0,
      "version": 0,
      "external_id": "string",
      "public_id": "string",
      "order_id": "string",
      "manifest_id": "string",
      "origin_stop_id": "string",
      "destination_stop_id": "string",
      "origin": {
        "terminal_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0
      },
      "destination": {
        "terminal_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0
      },
      "status": "available",
      "origin_start_at": "2018-09-19T05:22:07Z",
      "origin_end_at": "2018-09-19T05:22:07Z",
      "origin_appt_start_at": "2018-09-19T05:22:07Z",
      "origin_appt_end_at": "2018-09-19T05:22:07Z",
      "destination_start_at": "2018-09-19T05:22:07Z",
      "destination_end_at": "2018-09-19T05:22:07Z",
      "destination_appt_start_at": "2018-09-19T05:22:07Z",
      "destination_appt_end_at": "2018-09-19T05:22:07Z",
      "commodities": [
        {
          "id": "string",
          "measurement_unit": "inch",
          "weight_unit": "lb",
          "freight_class": "string",
          "commodity_type": "skid",
          "commodity_type_other": "string",
          "description": "string",
          "feet": 0,
          "volume": 0,
          "length": 0,
          "width": 0,
          "height": 0,
          "weight": 0,
          "nmfc": "string",
          "is_stackable": true,
          "quantity": 0,
          "pieces": 0,
          "sku": "string"
        }
      ],
      "accessorials": [
        "string"
      ],
      "history": {
        "origin_arrived_at": "2018-09-19T05:22:07Z",
        "origin_in_at": "2018-09-19T05:22:07Z",
        "origin_pickedup_at": "2018-09-19T05:22:07Z",
        "origin_out_at": "2018-09-19T05:22:07Z",
        "destination_arrived_at": "2018-09-19T05:22:07Z",
        "destination_in_at": "2018-09-19T05:22:07Z",
        "destination_delivered_at": "2018-09-19T05:22:07Z",
        "destination_out_at": "2018-09-19T05:22:07Z"
      }
    }
  ],
  "offset": 0,
  "limit": 0,
  "total": 0
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="searchLegs-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="searchLegs-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
offset|integer|false|No description
limit|integer|false|No description
total|integer|false|No description
legs|[[Leg](#schemaleg)]|false|No description
» id|string(uuid)|false|Auto generated system ID
» sequence_id|integer|false|Auto generated sequence ID per customer
» version|integer|false|Auto generated version number (incremental)
» external_id|string|false|External ID for mapping the leg to an external system. This field value can be _null_
» public_id|string|false|Auto generated human readable ID
» order_id|string|false|Related order ID
» manifest_id|string|false|Related manifest ID (assigned). This field value can be _null_
» origin_stop_id|string|false|Stop ID of the origin (only if this leg has been assigned to a manifest). This field value can be _null_
» destination_stop_id|string|false|Stop ID of the destination (only if this leg has been assigned to a manifest). This field value can be _null_
» origin|[LegAddress](#schemalegaddress)|false|Leg address
»» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» destination|[LegAddress](#schemalegaddress)|false|Leg address
»» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» status|string|false|Leg Status
» origin_start_at|string(date-time)|false|Origin ready time range (start)
» origin_end_at|string(date-time)|false|Origin ready time range (end)
» origin_appt_start_at|string(date-time)|false|Origin appointment time range (start). This field value can be _null_
» origin_appt_end_at|string(date-time)|false|Origin appointment time range (end). This field value can be _null_
» destination_start_at|string(date-time)|false|Destination expected time range (start). This field value can be _null_
» destination_end_at|string(date-time)|false|Destination expected time range (end). This field value can be _null_
» destination_appt_start_at|string(date-time)|false|Destination appointment time range (start). This field value can be _null_
» destination_appt_end_at|string(date-time)|false|Destination appointment time range (end). This field value can be _null_
» history|[LegHistory](#schemaleghistory)|false|Historical timestamps of a leg
»» origin_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at origin
»» origin_in_at|string(date-time)|false|The timestamp of when the driver/partner in at origin
»» origin_pickedup_at|string(date-time)|false|The timestamp of when the driver/partner picked up at origin
»» origin_out_at|string(date-time)|false|The timestamp of when the driver/partner out at origin
»» destination_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at destination
»» destination_in_at|string(date-time)|false|The timestamp of when the driver/partner in at destination
»» destination_delivered_at|string(date-time)|false|The timestamp of when the driver/partner delievered up at destination
»» destination_out_at|string(date-time)|false|The timestamp of when the driver/partner out at destination
» commodities|[[Commodity](#schemacommodity)]|false|Commodities items
»» id|string(uuid)|false|Auto generated commodity id
»» measurement_unit|string|false|Measurement unit
»» weight_unit|string|false|Weight unit
»» freight_class|string|false|Freight class
»» commodity_type|string|false|Commodity type
»» commodity_type_other|string|false|If commodity type is set to _other_, then this field must have value
»» description|string|false|Description of the commodity
»» feet|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»» volume|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»» length|number(float)|false|Length of the commodity
»» width|number(float)|false|Width of the commodity
»» height|number(float)|false|Height of the commodity
»» weight|number(float)|false|Weight of the commodity
»» nmfc|string|false|NMFC number
»» is_stackable|boolean|false|Is this commodity can be stacked?
»» quantity|integer|false|Quantity of the commodity
»» pieces|integer|false|Total number of pieces. This field value can be _null_
»» sku|string|false|SKU number
» accessorials|[string(uuid)]|false|No description



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: legs )
</aside>

## reviseLegOriginById

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/legs/{legID}/revise_origin \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT https://platform.roserocket.com/v1/legs/{legID}/revise_origin HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/legs/{legID}/revise_origin',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "address": {
    "terminal_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/legs/{legID}/revise_origin',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'https://platform.roserocket.com/v1/legs/{legID}/revise_origin',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('https://platform.roserocket.com/v1/legs/{legID}/revise_origin', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/legs/{legID}/revise_origin");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /legs/{legID}/revise_origin`

*Revise the origin of a leg by ID*

> Body parameter

```json
{
  "address": {
    "terminal_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0
  }
}
```
<h3 id="reviseLegOriginById-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
legID|path|string|true|ID of the leg to revise. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.
body|body|[LegAddressReviseRequest](#schemalegaddressreviserequest)|true|Leg address revise object
» address|body|[LegAddress](#schemalegaddress)|false|Leg address
»» terminal_id|body|string(uuid)|false|Related terminal ID. This field value can be _null_
»» org_name|body|string|false|Organization name
»» contact_name|body|string|false|Contact name
»» address_1|body|string|false|Address line 1
»» address_2|body|string|false|Address line 2
»» suite|body|string|false|Suite number
»» city|body|string|false|City
»» state|body|string|false|State / Province
»» country|body|string|false|Country (2 letter ISO)
»» postal|body|string|false|Postal / Zip code
»» phone|body|string|false|Phone number
»» phone_ext|body|string|false|Phone extension
»» email|body|string|false|Email
»» fax|body|string|false|Fax
»» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_


> Example responses

```json
{
  "leg": {
    "id": "string",
    "sequence_id": 0,
    "version": 0,
    "external_id": "string",
    "public_id": "string",
    "order_id": "string",
    "manifest_id": "string",
    "origin_stop_id": "string",
    "destination_stop_id": "string",
    "origin": {
      "terminal_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0
    },
    "destination": {
      "terminal_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0
    },
    "status": "available",
    "origin_start_at": "2018-09-19T05:22:07Z",
    "origin_end_at": "2018-09-19T05:22:07Z",
    "origin_appt_start_at": "2018-09-19T05:22:07Z",
    "origin_appt_end_at": "2018-09-19T05:22:07Z",
    "destination_start_at": "2018-09-19T05:22:07Z",
    "destination_end_at": "2018-09-19T05:22:07Z",
    "destination_appt_start_at": "2018-09-19T05:22:07Z",
    "destination_appt_end_at": "2018-09-19T05:22:07Z",
    "commodities": [
      {
        "id": "string",
        "measurement_unit": "inch",
        "weight_unit": "lb",
        "freight_class": "string",
        "commodity_type": "skid",
        "commodity_type_other": "string",
        "description": "string",
        "feet": 0,
        "volume": 0,
        "length": 0,
        "width": 0,
        "height": 0,
        "weight": 0,
        "nmfc": "string",
        "is_stackable": true,
        "quantity": 0,
        "pieces": 0,
        "sku": "string"
      }
    ],
    "accessorials": [
      "string"
    ],
    "history": {
      "origin_arrived_at": "2018-09-19T05:22:07Z",
      "origin_in_at": "2018-09-19T05:22:07Z",
      "origin_pickedup_at": "2018-09-19T05:22:07Z",
      "origin_out_at": "2018-09-19T05:22:07Z",
      "destination_arrived_at": "2018-09-19T05:22:07Z",
      "destination_in_at": "2018-09-19T05:22:07Z",
      "destination_delivered_at": "2018-09-19T05:22:07Z",
      "destination_out_at": "2018-09-19T05:22:07Z"
    }
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="reviseLegOriginById-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="reviseLegOriginById-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
leg|[Leg](#schemaleg)|false|Leg
» id|string(uuid)|false|Auto generated system ID
» sequence_id|integer|false|Auto generated sequence ID per customer
» version|integer|false|Auto generated version number (incremental)
» external_id|string|false|External ID for mapping the leg to an external system. This field value can be _null_
» public_id|string|false|Auto generated human readable ID
» order_id|string|false|Related order ID
» manifest_id|string|false|Related manifest ID (assigned). This field value can be _null_
» origin_stop_id|string|false|Stop ID of the origin (only if this leg has been assigned to a manifest). This field value can be _null_
» destination_stop_id|string|false|Stop ID of the destination (only if this leg has been assigned to a manifest). This field value can be _null_
» origin|[LegAddress](#schemalegaddress)|false|Leg address
»» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» destination|[LegAddress](#schemalegaddress)|false|Leg address
»» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» status|string|false|Leg Status
» origin_start_at|string(date-time)|false|Origin ready time range (start)
» origin_end_at|string(date-time)|false|Origin ready time range (end)
» origin_appt_start_at|string(date-time)|false|Origin appointment time range (start). This field value can be _null_
» origin_appt_end_at|string(date-time)|false|Origin appointment time range (end). This field value can be _null_
» destination_start_at|string(date-time)|false|Destination expected time range (start). This field value can be _null_
» destination_end_at|string(date-time)|false|Destination expected time range (end). This field value can be _null_
» destination_appt_start_at|string(date-time)|false|Destination appointment time range (start). This field value can be _null_
» destination_appt_end_at|string(date-time)|false|Destination appointment time range (end). This field value can be _null_
» history|[LegHistory](#schemaleghistory)|false|Historical timestamps of a leg
»» origin_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at origin
»» origin_in_at|string(date-time)|false|The timestamp of when the driver/partner in at origin
»» origin_pickedup_at|string(date-time)|false|The timestamp of when the driver/partner picked up at origin
»» origin_out_at|string(date-time)|false|The timestamp of when the driver/partner out at origin
»» destination_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at destination
»» destination_in_at|string(date-time)|false|The timestamp of when the driver/partner in at destination
»» destination_delivered_at|string(date-time)|false|The timestamp of when the driver/partner delievered up at destination
»» destination_out_at|string(date-time)|false|The timestamp of when the driver/partner out at destination
» commodities|[[Commodity](#schemacommodity)]|false|Commodities items
»» id|string(uuid)|false|Auto generated commodity id
»» measurement_unit|string|false|Measurement unit
»» weight_unit|string|false|Weight unit
»» freight_class|string|false|Freight class
»» commodity_type|string|false|Commodity type
»» commodity_type_other|string|false|If commodity type is set to _other_, then this field must have value
»» description|string|false|Description of the commodity
»» feet|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»» volume|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»» length|number(float)|false|Length of the commodity
»» width|number(float)|false|Width of the commodity
»» height|number(float)|false|Height of the commodity
»» weight|number(float)|false|Weight of the commodity
»» nmfc|string|false|NMFC number
»» is_stackable|boolean|false|Is this commodity can be stacked?
»» quantity|integer|false|Quantity of the commodity
»» pieces|integer|false|Total number of pieces. This field value can be _null_
»» sku|string|false|SKU number
» accessorials|[string(uuid)]|false|No description



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: legs )
</aside>

## reviseLegDestinationById

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/legs/{legID}/revise_destination \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT https://platform.roserocket.com/v1/legs/{legID}/revise_destination HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/legs/{legID}/revise_destination',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "address": {
    "terminal_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/legs/{legID}/revise_destination',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'https://platform.roserocket.com/v1/legs/{legID}/revise_destination',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('https://platform.roserocket.com/v1/legs/{legID}/revise_destination', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/legs/{legID}/revise_destination");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /legs/{legID}/revise_destination`

*Revise the destination of a leg by ID*

> Body parameter

```json
{
  "address": {
    "terminal_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0
  }
}
```
<h3 id="reviseLegDestinationById-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
legID|path|string|true|ID of the leg to revise. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.
body|body|[LegAddressReviseRequest](#schemalegaddressreviserequest)|true|Leg address revise object
» address|body|[LegAddress](#schemalegaddress)|false|Leg address
»» terminal_id|body|string(uuid)|false|Related terminal ID. This field value can be _null_
»» org_name|body|string|false|Organization name
»» contact_name|body|string|false|Contact name
»» address_1|body|string|false|Address line 1
»» address_2|body|string|false|Address line 2
»» suite|body|string|false|Suite number
»» city|body|string|false|City
»» state|body|string|false|State / Province
»» country|body|string|false|Country (2 letter ISO)
»» postal|body|string|false|Postal / Zip code
»» phone|body|string|false|Phone number
»» phone_ext|body|string|false|Phone extension
»» email|body|string|false|Email
»» fax|body|string|false|Fax
»» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_


> Example responses

```json
{
  "leg": {
    "id": "string",
    "sequence_id": 0,
    "version": 0,
    "external_id": "string",
    "public_id": "string",
    "order_id": "string",
    "manifest_id": "string",
    "origin_stop_id": "string",
    "destination_stop_id": "string",
    "origin": {
      "terminal_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0
    },
    "destination": {
      "terminal_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0
    },
    "status": "available",
    "origin_start_at": "2018-09-19T05:22:07Z",
    "origin_end_at": "2018-09-19T05:22:07Z",
    "origin_appt_start_at": "2018-09-19T05:22:07Z",
    "origin_appt_end_at": "2018-09-19T05:22:07Z",
    "destination_start_at": "2018-09-19T05:22:07Z",
    "destination_end_at": "2018-09-19T05:22:07Z",
    "destination_appt_start_at": "2018-09-19T05:22:07Z",
    "destination_appt_end_at": "2018-09-19T05:22:07Z",
    "commodities": [
      {
        "id": "string",
        "measurement_unit": "inch",
        "weight_unit": "lb",
        "freight_class": "string",
        "commodity_type": "skid",
        "commodity_type_other": "string",
        "description": "string",
        "feet": 0,
        "volume": 0,
        "length": 0,
        "width": 0,
        "height": 0,
        "weight": 0,
        "nmfc": "string",
        "is_stackable": true,
        "quantity": 0,
        "pieces": 0,
        "sku": "string"
      }
    ],
    "accessorials": [
      "string"
    ],
    "history": {
      "origin_arrived_at": "2018-09-19T05:22:07Z",
      "origin_in_at": "2018-09-19T05:22:07Z",
      "origin_pickedup_at": "2018-09-19T05:22:07Z",
      "origin_out_at": "2018-09-19T05:22:07Z",
      "destination_arrived_at": "2018-09-19T05:22:07Z",
      "destination_in_at": "2018-09-19T05:22:07Z",
      "destination_delivered_at": "2018-09-19T05:22:07Z",
      "destination_out_at": "2018-09-19T05:22:07Z"
    }
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="reviseLegDestinationById-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="reviseLegDestinationById-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
leg|[Leg](#schemaleg)|false|Leg
» id|string(uuid)|false|Auto generated system ID
» sequence_id|integer|false|Auto generated sequence ID per customer
» version|integer|false|Auto generated version number (incremental)
» external_id|string|false|External ID for mapping the leg to an external system. This field value can be _null_
» public_id|string|false|Auto generated human readable ID
» order_id|string|false|Related order ID
» manifest_id|string|false|Related manifest ID (assigned). This field value can be _null_
» origin_stop_id|string|false|Stop ID of the origin (only if this leg has been assigned to a manifest). This field value can be _null_
» destination_stop_id|string|false|Stop ID of the destination (only if this leg has been assigned to a manifest). This field value can be _null_
» origin|[LegAddress](#schemalegaddress)|false|Leg address
»» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» destination|[LegAddress](#schemalegaddress)|false|Leg address
»» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» status|string|false|Leg Status
» origin_start_at|string(date-time)|false|Origin ready time range (start)
» origin_end_at|string(date-time)|false|Origin ready time range (end)
» origin_appt_start_at|string(date-time)|false|Origin appointment time range (start). This field value can be _null_
» origin_appt_end_at|string(date-time)|false|Origin appointment time range (end). This field value can be _null_
» destination_start_at|string(date-time)|false|Destination expected time range (start). This field value can be _null_
» destination_end_at|string(date-time)|false|Destination expected time range (end). This field value can be _null_
» destination_appt_start_at|string(date-time)|false|Destination appointment time range (start). This field value can be _null_
» destination_appt_end_at|string(date-time)|false|Destination appointment time range (end). This field value can be _null_
» history|[LegHistory](#schemaleghistory)|false|Historical timestamps of a leg
»» origin_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at origin
»» origin_in_at|string(date-time)|false|The timestamp of when the driver/partner in at origin
»» origin_pickedup_at|string(date-time)|false|The timestamp of when the driver/partner picked up at origin
»» origin_out_at|string(date-time)|false|The timestamp of when the driver/partner out at origin
»» destination_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at destination
»» destination_in_at|string(date-time)|false|The timestamp of when the driver/partner in at destination
»» destination_delivered_at|string(date-time)|false|The timestamp of when the driver/partner delievered up at destination
»» destination_out_at|string(date-time)|false|The timestamp of when the driver/partner out at destination
» commodities|[[Commodity](#schemacommodity)]|false|Commodities items
»» id|string(uuid)|false|Auto generated commodity id
»» measurement_unit|string|false|Measurement unit
»» weight_unit|string|false|Weight unit
»» freight_class|string|false|Freight class
»» commodity_type|string|false|Commodity type
»» commodity_type_other|string|false|If commodity type is set to _other_, then this field must have value
»» description|string|false|Description of the commodity
»» feet|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»» volume|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»» length|number(float)|false|Length of the commodity
»» width|number(float)|false|Width of the commodity
»» height|number(float)|false|Height of the commodity
»» weight|number(float)|false|Weight of the commodity
»» nmfc|string|false|NMFC number
»» is_stackable|boolean|false|Is this commodity can be stacked?
»» quantity|integer|false|Quantity of the commodity
»» pieces|integer|false|Total number of pieces. This field value can be _null_
»» sku|string|false|SKU number
» accessorials|[string(uuid)]|false|No description



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: legs )
</aside>

## reviseLegCommoditiesById

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/legs/{legID}/revise_commodities \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT https://platform.roserocket.com/v1/legs/{legID}/revise_commodities HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/legs/{legID}/revise_commodities',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "commodities": [
    {
      "measurement_unit": "inch",
      "weight_unit": "lb",
      "freight_class": "string",
      "commodity_type": "skid",
      "commodity_type_other": "string",
      "description": "string",
      "feet": 0,
      "volume": 0,
      "length": 0,
      "width": 0,
      "height": 0,
      "weight": 0,
      "nmfc": "string",
      "is_stackable": true,
      "quantity": 0,
      "pieces": 0,
      "sku": "string"
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/legs/{legID}/revise_commodities',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'https://platform.roserocket.com/v1/legs/{legID}/revise_commodities',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('https://platform.roserocket.com/v1/legs/{legID}/revise_commodities', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/legs/{legID}/revise_commodities");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /legs/{legID}/revise_commodities`

*Revise the commodities of a leg by ID*

> Body parameter

```json
{
  "commodities": [
    {
      "measurement_unit": "inch",
      "weight_unit": "lb",
      "freight_class": "string",
      "commodity_type": "skid",
      "commodity_type_other": "string",
      "description": "string",
      "feet": 0,
      "volume": 0,
      "length": 0,
      "width": 0,
      "height": 0,
      "weight": 0,
      "nmfc": "string",
      "is_stackable": true,
      "quantity": 0,
      "pieces": 0,
      "sku": "string"
    }
  ]
}
```
<h3 id="reviseLegCommoditiesById-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
legID|path|string|true|ID of the leg to revise. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.
body|body|[CommodityReviseRequest](#schemacommodityreviserequest)|true|Leg address revise object
» commodities|body|[[Commodity](#schemacommodity)]|false|No description
»» id|body|string(uuid)|false|Auto generated commodity id
»» measurement_unit|body|string|false|Measurement unit
»» weight_unit|body|string|false|Weight unit
»» freight_class|body|string|false|Freight class
»» commodity_type|body|string|false|Commodity type
»» commodity_type_other|body|string|false|If commodity type is set to _other_, then this field must have value
»» description|body|string|false|Description of the commodity
»» feet|body|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»» volume|body|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»» length|body|number(float)|false|Length of the commodity
»» width|body|number(float)|false|Width of the commodity
»» height|body|number(float)|false|Height of the commodity
»» weight|body|number(float)|false|Weight of the commodity
»» nmfc|body|string|false|NMFC number
»» is_stackable|body|boolean|false|Is this commodity can be stacked?
»» quantity|body|integer|false|Quantity of the commodity
»» pieces|body|integer|false|Total number of pieces. This field value can be _null_
»» sku|body|string|false|SKU number


#### Enumerated Values

|Parameter|Value|
|---|---|
»» measurement_unit|inch|
»» measurement_unit|cm|
»» weight_unit|lb|
»» weight_unit|kg|
»» commodity_type|skid|
»» commodity_type|other|

> Example responses

```json
{
  "leg": {
    "id": "string",
    "sequence_id": 0,
    "version": 0,
    "external_id": "string",
    "public_id": "string",
    "order_id": "string",
    "manifest_id": "string",
    "origin_stop_id": "string",
    "destination_stop_id": "string",
    "origin": {
      "terminal_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0
    },
    "destination": {
      "terminal_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0
    },
    "status": "available",
    "origin_start_at": "2018-09-19T05:22:07Z",
    "origin_end_at": "2018-09-19T05:22:07Z",
    "origin_appt_start_at": "2018-09-19T05:22:07Z",
    "origin_appt_end_at": "2018-09-19T05:22:07Z",
    "destination_start_at": "2018-09-19T05:22:07Z",
    "destination_end_at": "2018-09-19T05:22:07Z",
    "destination_appt_start_at": "2018-09-19T05:22:07Z",
    "destination_appt_end_at": "2018-09-19T05:22:07Z",
    "commodities": [
      {
        "id": "string",
        "measurement_unit": "inch",
        "weight_unit": "lb",
        "freight_class": "string",
        "commodity_type": "skid",
        "commodity_type_other": "string",
        "description": "string",
        "feet": 0,
        "volume": 0,
        "length": 0,
        "width": 0,
        "height": 0,
        "weight": 0,
        "nmfc": "string",
        "is_stackable": true,
        "quantity": 0,
        "pieces": 0,
        "sku": "string"
      }
    ],
    "accessorials": [
      "string"
    ],
    "history": {
      "origin_arrived_at": "2018-09-19T05:22:07Z",
      "origin_in_at": "2018-09-19T05:22:07Z",
      "origin_pickedup_at": "2018-09-19T05:22:07Z",
      "origin_out_at": "2018-09-19T05:22:07Z",
      "destination_arrived_at": "2018-09-19T05:22:07Z",
      "destination_in_at": "2018-09-19T05:22:07Z",
      "destination_delivered_at": "2018-09-19T05:22:07Z",
      "destination_out_at": "2018-09-19T05:22:07Z"
    }
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="reviseLegCommoditiesById-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="reviseLegCommoditiesById-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
leg|[Leg](#schemaleg)|false|Leg
» id|string(uuid)|false|Auto generated system ID
» sequence_id|integer|false|Auto generated sequence ID per customer
» version|integer|false|Auto generated version number (incremental)
» external_id|string|false|External ID for mapping the leg to an external system. This field value can be _null_
» public_id|string|false|Auto generated human readable ID
» order_id|string|false|Related order ID
» manifest_id|string|false|Related manifest ID (assigned). This field value can be _null_
» origin_stop_id|string|false|Stop ID of the origin (only if this leg has been assigned to a manifest). This field value can be _null_
» destination_stop_id|string|false|Stop ID of the destination (only if this leg has been assigned to a manifest). This field value can be _null_
» origin|[LegAddress](#schemalegaddress)|false|Leg address
»» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» destination|[LegAddress](#schemalegaddress)|false|Leg address
»» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» status|string|false|Leg Status
» origin_start_at|string(date-time)|false|Origin ready time range (start)
» origin_end_at|string(date-time)|false|Origin ready time range (end)
» origin_appt_start_at|string(date-time)|false|Origin appointment time range (start). This field value can be _null_
» origin_appt_end_at|string(date-time)|false|Origin appointment time range (end). This field value can be _null_
» destination_start_at|string(date-time)|false|Destination expected time range (start). This field value can be _null_
» destination_end_at|string(date-time)|false|Destination expected time range (end). This field value can be _null_
» destination_appt_start_at|string(date-time)|false|Destination appointment time range (start). This field value can be _null_
» destination_appt_end_at|string(date-time)|false|Destination appointment time range (end). This field value can be _null_
» history|[LegHistory](#schemaleghistory)|false|Historical timestamps of a leg
»» origin_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at origin
»» origin_in_at|string(date-time)|false|The timestamp of when the driver/partner in at origin
»» origin_pickedup_at|string(date-time)|false|The timestamp of when the driver/partner picked up at origin
»» origin_out_at|string(date-time)|false|The timestamp of when the driver/partner out at origin
»» destination_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at destination
»» destination_in_at|string(date-time)|false|The timestamp of when the driver/partner in at destination
»» destination_delivered_at|string(date-time)|false|The timestamp of when the driver/partner delievered up at destination
»» destination_out_at|string(date-time)|false|The timestamp of when the driver/partner out at destination
» commodities|[[Commodity](#schemacommodity)]|false|Commodities items
»» id|string(uuid)|false|Auto generated commodity id
»» measurement_unit|string|false|Measurement unit
»» weight_unit|string|false|Weight unit
»» freight_class|string|false|Freight class
»» commodity_type|string|false|Commodity type
»» commodity_type_other|string|false|If commodity type is set to _other_, then this field must have value
»» description|string|false|Description of the commodity
»» feet|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»» volume|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»» length|number(float)|false|Length of the commodity
»» width|number(float)|false|Width of the commodity
»» height|number(float)|false|Height of the commodity
»» weight|number(float)|false|Weight of the commodity
»» nmfc|string|false|NMFC number
»» is_stackable|boolean|false|Is this commodity can be stacked?
»» quantity|integer|false|Quantity of the commodity
»» pieces|integer|false|Total number of pieces. This field value can be _null_
»» sku|string|false|SKU number
» accessorials|[string(uuid)]|false|No description



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: legs )
</aside>

## loadLegById

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/legs/{legID}/load \
  -H 'Accept: application/json'

```

```http
POST https://platform.roserocket.com/v1/legs/{legID}/load HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/legs/{legID}/load',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/legs/{legID}/load',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'https://platform.roserocket.com/v1/legs/{legID}/load',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('https://platform.roserocket.com/v1/legs/{legID}/load', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/legs/{legID}/load");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /legs/{legID}/load`

*Load leg by ID*

<h3 id="loadLegById-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
legID|path|string|true|ID of the leg to load. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.
from_arrive_at|query|string(date-time)|false|From arrive at
from_in_at|query|string(date-time)|false|From in at
from_out_at|query|string(date-time)|false|From out at
pickedup_at|query|string(date-time)|false|Picked up at


> Example responses

```json
{
  "leg": {
    "id": "string",
    "sequence_id": 0,
    "version": 0,
    "external_id": "string",
    "public_id": "string",
    "order_id": "string",
    "manifest_id": "string",
    "origin_stop_id": "string",
    "destination_stop_id": "string",
    "origin": {
      "terminal_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0
    },
    "destination": {
      "terminal_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0
    },
    "status": "available",
    "origin_start_at": "2018-09-19T05:22:07Z",
    "origin_end_at": "2018-09-19T05:22:07Z",
    "origin_appt_start_at": "2018-09-19T05:22:07Z",
    "origin_appt_end_at": "2018-09-19T05:22:07Z",
    "destination_start_at": "2018-09-19T05:22:07Z",
    "destination_end_at": "2018-09-19T05:22:07Z",
    "destination_appt_start_at": "2018-09-19T05:22:07Z",
    "destination_appt_end_at": "2018-09-19T05:22:07Z",
    "commodities": [
      {
        "id": "string",
        "measurement_unit": "inch",
        "weight_unit": "lb",
        "freight_class": "string",
        "commodity_type": "skid",
        "commodity_type_other": "string",
        "description": "string",
        "feet": 0,
        "volume": 0,
        "length": 0,
        "width": 0,
        "height": 0,
        "weight": 0,
        "nmfc": "string",
        "is_stackable": true,
        "quantity": 0,
        "pieces": 0,
        "sku": "string"
      }
    ],
    "accessorials": [
      "string"
    ],
    "history": {
      "origin_arrived_at": "2018-09-19T05:22:07Z",
      "origin_in_at": "2018-09-19T05:22:07Z",
      "origin_pickedup_at": "2018-09-19T05:22:07Z",
      "origin_out_at": "2018-09-19T05:22:07Z",
      "destination_arrived_at": "2018-09-19T05:22:07Z",
      "destination_in_at": "2018-09-19T05:22:07Z",
      "destination_delivered_at": "2018-09-19T05:22:07Z",
      "destination_out_at": "2018-09-19T05:22:07Z"
    }
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="loadLegById-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="loadLegById-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
leg|[Leg](#schemaleg)|false|Leg
» id|string(uuid)|false|Auto generated system ID
» sequence_id|integer|false|Auto generated sequence ID per customer
» version|integer|false|Auto generated version number (incremental)
» external_id|string|false|External ID for mapping the leg to an external system. This field value can be _null_
» public_id|string|false|Auto generated human readable ID
» order_id|string|false|Related order ID
» manifest_id|string|false|Related manifest ID (assigned). This field value can be _null_
» origin_stop_id|string|false|Stop ID of the origin (only if this leg has been assigned to a manifest). This field value can be _null_
» destination_stop_id|string|false|Stop ID of the destination (only if this leg has been assigned to a manifest). This field value can be _null_
» origin|[LegAddress](#schemalegaddress)|false|Leg address
»» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» destination|[LegAddress](#schemalegaddress)|false|Leg address
»» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» status|string|false|Leg Status
» origin_start_at|string(date-time)|false|Origin ready time range (start)
» origin_end_at|string(date-time)|false|Origin ready time range (end)
» origin_appt_start_at|string(date-time)|false|Origin appointment time range (start). This field value can be _null_
» origin_appt_end_at|string(date-time)|false|Origin appointment time range (end). This field value can be _null_
» destination_start_at|string(date-time)|false|Destination expected time range (start). This field value can be _null_
» destination_end_at|string(date-time)|false|Destination expected time range (end). This field value can be _null_
» destination_appt_start_at|string(date-time)|false|Destination appointment time range (start). This field value can be _null_
» destination_appt_end_at|string(date-time)|false|Destination appointment time range (end). This field value can be _null_
» history|[LegHistory](#schemaleghistory)|false|Historical timestamps of a leg
»» origin_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at origin
»» origin_in_at|string(date-time)|false|The timestamp of when the driver/partner in at origin
»» origin_pickedup_at|string(date-time)|false|The timestamp of when the driver/partner picked up at origin
»» origin_out_at|string(date-time)|false|The timestamp of when the driver/partner out at origin
»» destination_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at destination
»» destination_in_at|string(date-time)|false|The timestamp of when the driver/partner in at destination
»» destination_delivered_at|string(date-time)|false|The timestamp of when the driver/partner delievered up at destination
»» destination_out_at|string(date-time)|false|The timestamp of when the driver/partner out at destination
» commodities|[[Commodity](#schemacommodity)]|false|Commodities items
»» id|string(uuid)|false|Auto generated commodity id
»» measurement_unit|string|false|Measurement unit
»» weight_unit|string|false|Weight unit
»» freight_class|string|false|Freight class
»» commodity_type|string|false|Commodity type
»» commodity_type_other|string|false|If commodity type is set to _other_, then this field must have value
»» description|string|false|Description of the commodity
»» feet|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»» volume|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»» length|number(float)|false|Length of the commodity
»» width|number(float)|false|Width of the commodity
»» height|number(float)|false|Height of the commodity
»» weight|number(float)|false|Weight of the commodity
»» nmfc|string|false|NMFC number
»» is_stackable|boolean|false|Is this commodity can be stacked?
»» quantity|integer|false|Quantity of the commodity
»» pieces|integer|false|Total number of pieces. This field value can be _null_
»» sku|string|false|SKU number
» accessorials|[string(uuid)]|false|No description



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: legs )
</aside>

## unloadLegById

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/legs/{legID}/unload \
  -H 'Accept: application/json'

```

```http
POST https://platform.roserocket.com/v1/legs/{legID}/unload HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/legs/{legID}/unload',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/legs/{legID}/unload',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'https://platform.roserocket.com/v1/legs/{legID}/unload',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('https://platform.roserocket.com/v1/legs/{legID}/unload', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/legs/{legID}/unload");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /legs/{legID}/unload`

*Unload leg by ID*

<h3 id="unloadLegById-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
legID|path|string|true|ID of the leg to unload. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.
to_arrive_at|query|string(date-time)|false|From arrive at
to_in_at|query|string(date-time)|false|From in at
to_out_at|query|string(date-time)|false|From out at
delivered_at|query|string(date-time)|false|Picked up at


> Example responses

```json
{
  "leg": {
    "id": "string",
    "sequence_id": 0,
    "version": 0,
    "external_id": "string",
    "public_id": "string",
    "order_id": "string",
    "manifest_id": "string",
    "origin_stop_id": "string",
    "destination_stop_id": "string",
    "origin": {
      "terminal_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0
    },
    "destination": {
      "terminal_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0
    },
    "status": "available",
    "origin_start_at": "2018-09-19T05:22:07Z",
    "origin_end_at": "2018-09-19T05:22:07Z",
    "origin_appt_start_at": "2018-09-19T05:22:07Z",
    "origin_appt_end_at": "2018-09-19T05:22:07Z",
    "destination_start_at": "2018-09-19T05:22:07Z",
    "destination_end_at": "2018-09-19T05:22:07Z",
    "destination_appt_start_at": "2018-09-19T05:22:07Z",
    "destination_appt_end_at": "2018-09-19T05:22:07Z",
    "commodities": [
      {
        "id": "string",
        "measurement_unit": "inch",
        "weight_unit": "lb",
        "freight_class": "string",
        "commodity_type": "skid",
        "commodity_type_other": "string",
        "description": "string",
        "feet": 0,
        "volume": 0,
        "length": 0,
        "width": 0,
        "height": 0,
        "weight": 0,
        "nmfc": "string",
        "is_stackable": true,
        "quantity": 0,
        "pieces": 0,
        "sku": "string"
      }
    ],
    "accessorials": [
      "string"
    ],
    "history": {
      "origin_arrived_at": "2018-09-19T05:22:07Z",
      "origin_in_at": "2018-09-19T05:22:07Z",
      "origin_pickedup_at": "2018-09-19T05:22:07Z",
      "origin_out_at": "2018-09-19T05:22:07Z",
      "destination_arrived_at": "2018-09-19T05:22:07Z",
      "destination_in_at": "2018-09-19T05:22:07Z",
      "destination_delivered_at": "2018-09-19T05:22:07Z",
      "destination_out_at": "2018-09-19T05:22:07Z"
    }
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="unloadLegById-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="unloadLegById-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
leg|[Leg](#schemaleg)|false|Leg
» id|string(uuid)|false|Auto generated system ID
» sequence_id|integer|false|Auto generated sequence ID per customer
» version|integer|false|Auto generated version number (incremental)
» external_id|string|false|External ID for mapping the leg to an external system. This field value can be _null_
» public_id|string|false|Auto generated human readable ID
» order_id|string|false|Related order ID
» manifest_id|string|false|Related manifest ID (assigned). This field value can be _null_
» origin_stop_id|string|false|Stop ID of the origin (only if this leg has been assigned to a manifest). This field value can be _null_
» destination_stop_id|string|false|Stop ID of the destination (only if this leg has been assigned to a manifest). This field value can be _null_
» origin|[LegAddress](#schemalegaddress)|false|Leg address
»» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» destination|[LegAddress](#schemalegaddress)|false|Leg address
»» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» status|string|false|Leg Status
» origin_start_at|string(date-time)|false|Origin ready time range (start)
» origin_end_at|string(date-time)|false|Origin ready time range (end)
» origin_appt_start_at|string(date-time)|false|Origin appointment time range (start). This field value can be _null_
» origin_appt_end_at|string(date-time)|false|Origin appointment time range (end). This field value can be _null_
» destination_start_at|string(date-time)|false|Destination expected time range (start). This field value can be _null_
» destination_end_at|string(date-time)|false|Destination expected time range (end). This field value can be _null_
» destination_appt_start_at|string(date-time)|false|Destination appointment time range (start). This field value can be _null_
» destination_appt_end_at|string(date-time)|false|Destination appointment time range (end). This field value can be _null_
» history|[LegHistory](#schemaleghistory)|false|Historical timestamps of a leg
»» origin_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at origin
»» origin_in_at|string(date-time)|false|The timestamp of when the driver/partner in at origin
»» origin_pickedup_at|string(date-time)|false|The timestamp of when the driver/partner picked up at origin
»» origin_out_at|string(date-time)|false|The timestamp of when the driver/partner out at origin
»» destination_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at destination
»» destination_in_at|string(date-time)|false|The timestamp of when the driver/partner in at destination
»» destination_delivered_at|string(date-time)|false|The timestamp of when the driver/partner delievered up at destination
»» destination_out_at|string(date-time)|false|The timestamp of when the driver/partner out at destination
» commodities|[[Commodity](#schemacommodity)]|false|Commodities items
»» id|string(uuid)|false|Auto generated commodity id
»» measurement_unit|string|false|Measurement unit
»» weight_unit|string|false|Weight unit
»» freight_class|string|false|Freight class
»» commodity_type|string|false|Commodity type
»» commodity_type_other|string|false|If commodity type is set to _other_, then this field must have value
»» description|string|false|Description of the commodity
»» feet|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»» volume|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»» length|number(float)|false|Length of the commodity
»» width|number(float)|false|Width of the commodity
»» height|number(float)|false|Height of the commodity
»» weight|number(float)|false|Weight of the commodity
»» nmfc|string|false|NMFC number
»» is_stackable|boolean|false|Is this commodity can be stacked?
»» quantity|integer|false|Quantity of the commodity
»» pieces|integer|false|Total number of pieces. This field value can be _null_
»» sku|string|false|SKU number
» accessorials|[string(uuid)]|false|No description



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: legs )
</aside>

## updateLegFileByLegIdAndFileID

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/legs/{legID}/files/{fileID} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT https://platform.roserocket.com/v1/legs/{legID}/files/{fileID} HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/legs/{legID}/files/{fileID}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "type": "other",
  "url": "string",
  "description": "string",
  "latitude": 0,
  "longitude": 0,
  "metadata": {}
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/legs/{legID}/files/{fileID}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'https://platform.roserocket.com/v1/legs/{legID}/files/{fileID}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('https://platform.roserocket.com/v1/legs/{legID}/files/{fileID}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/legs/{legID}/files/{fileID}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /legs/{legID}/files/{fileID}`

*Add a file/document to a specified leg*

> Body parameter

```json
{
  "type": "other",
  "url": "string",
  "description": "string",
  "latitude": 0,
  "longitude": 0,
  "metadata": {}
}
```
<h3 id="updateLegFileByLegIdAndFileID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
legID|path|string|true|ID of the leg for which to update a file/document. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.
fileID|path|string|true|ID of the leg file
body|body|[LegFileRequest](#schemalegfilerequest)|true|Leg file create request
» type|body|string|false|The type of leg file
» url|body|string|false|The url location for the leg file
» description|body|string|false|A description of the leg file
» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_
» metadata|body|object|false|Metadata object for the leg file


#### Enumerated Values

|Parameter|Value|
|---|---|
» type|other|
» type|comm-invoice|
» type|pod|
» type|pop|
» type|pod-sig|
» type|pop-sig|
» type|carrier-invoice|
» type|smc|
» type|bol|

> Example responses

```json
{
  "leg_file": {
    "id": "string",
    "created_at": "2018-09-19T05:22:07Z",
    "updated_at": "2018-09-19T05:22:07Z",
    "org_id": "string",
    "leg_id": "string",
    "uploaded_by": "string",
    "uploaded_at": "string",
    "type": "other",
    "url": "string",
    "description": "string",
    "latitude": 0,
    "longitude": 0,
    "metadata": {},
    "task_id": "string"
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="updateLegFileByLegIdAndFileID-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="updateLegFileByLegIdAndFileID-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
leg_file|[LegFile](#schemalegfile)|false|The file for the leg
» id|string(uuid)|false|The uuid for the leg file
» created_at|string(date-time)|false|The timestamp for the creation of the leg file
» updated_at|string(date-time)|false|The timestamp for the last update of the leg file
» org_id|string(uuid)|false|The uuid for the organization of the leg file
» leg_id|string(uuid)|false|The uuid of the leg corresponding to the leg file
» uploaded_by|string(uuid)|false|The uuid of the user who uploaded the leg file
» uploaded_at|string(uuid)|false|The uuid
» type|string|false|The type of leg file
» url|string|false|The url location for the leg file
» description|string|false|A description of the leg file
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» metadata|object|false|Metadata object for the leg file
» task_id|string(uuid)|false|The task id of the leg that corresponds to the leg file



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: legs )
</aside>

## deleteLegFileByLegIdAndFileID

> Code samples

```shell
# You can also use wget
curl -X DELETE https://platform.roserocket.com/v1/legs/{legID}/files/{fileID} \
  -H 'Accept: application/json'

```

```http
DELETE https://platform.roserocket.com/v1/legs/{legID}/files/{fileID} HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/legs/{legID}/files/{fileID}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/legs/{legID}/files/{fileID}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete 'https://platform.roserocket.com/v1/legs/{legID}/files/{fileID}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('https://platform.roserocket.com/v1/legs/{legID}/files/{fileID}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/legs/{legID}/files/{fileID}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`DELETE /legs/{legID}/files/{fileID}`

*Delete a file/document from a specified leg*

<h3 id="deleteLegFileByLegIdAndFileID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
legID|path|string|true|ID of the leg for which to delete file/document. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.
fileID|path|string|true|ID of the leg file to delete


> Example responses

```json
{
  "Message": "Success"
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="deleteLegFileByLegIdAndFileID-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="deleteLegFileByLegIdAndFileID-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
Message|string|false|No description



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: legs )
</aside>

## getLegFilesById

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/legs/{legID}/files \
  -H 'Accept: application/json'

```

```http
GET https://platform.roserocket.com/v1/legs/{legID}/files HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/legs/{legID}/files',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/legs/{legID}/files',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://platform.roserocket.com/v1/legs/{legID}/files',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://platform.roserocket.com/v1/legs/{legID}/files', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/legs/{legID}/files");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /legs/{legID}/files`

*Get all leg files/documents for a given ID of a leg*

<h3 id="getLegFilesById-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
legID|path|string|true|ID of the leg to get files for. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.


> Example responses

```json
{
  "leg_files": [
    {
      "id": "string",
      "created_at": "2018-09-19T05:22:07Z",
      "updated_at": "2018-09-19T05:22:07Z",
      "org_id": "string",
      "leg_id": "string",
      "uploaded_by": "string",
      "uploaded_at": "string",
      "type": "other",
      "url": "string",
      "description": "string",
      "latitude": 0,
      "longitude": 0,
      "metadata": {},
      "task_id": "string"
    }
  ]
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="getLegFilesById-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="getLegFilesById-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
leg_files|[[LegFile](#schemalegfile)]|false|No description
» id|string(uuid)|false|The uuid for the leg file
» created_at|string(date-time)|false|The timestamp for the creation of the leg file
» updated_at|string(date-time)|false|The timestamp for the last update of the leg file
» org_id|string(uuid)|false|The uuid for the organization of the leg file
» leg_id|string(uuid)|false|The uuid of the leg corresponding to the leg file
» uploaded_by|string(uuid)|false|The uuid of the user who uploaded the leg file
» uploaded_at|string(uuid)|false|The uuid
» type|string|false|The type of leg file
» url|string|false|The url location for the leg file
» description|string|false|A description of the leg file
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» metadata|object|false|Metadata object for the leg file
» task_id|string(uuid)|false|The task id of the leg that corresponds to the leg file



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: legs )
</aside>

## addLegFileByLegId

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/legs/{legID}/files \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST https://platform.roserocket.com/v1/legs/{legID}/files HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/legs/{legID}/files',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "type": "other",
  "url": "string",
  "description": "string",
  "latitude": 0,
  "longitude": 0,
  "metadata": {}
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/legs/{legID}/files',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'https://platform.roserocket.com/v1/legs/{legID}/files',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('https://platform.roserocket.com/v1/legs/{legID}/files', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/legs/{legID}/files");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /legs/{legID}/files`

*Add a file/document to a specified leg*

> Body parameter

```json
{
  "type": "other",
  "url": "string",
  "description": "string",
  "latitude": 0,
  "longitude": 0,
  "metadata": {}
}
```
<h3 id="addLegFileByLegId-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
legID|path|string|true|ID of the leg for which to add a file/document. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.
body|body|[LegFileRequest](#schemalegfilerequest)|true|Leg file create request
» type|body|string|false|The type of leg file
» url|body|string|false|The url location for the leg file
» description|body|string|false|A description of the leg file
» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_
» metadata|body|object|false|Metadata object for the leg file


#### Enumerated Values

|Parameter|Value|
|---|---|
» type|other|
» type|comm-invoice|
» type|pod|
» type|pop|
» type|pod-sig|
» type|pop-sig|
» type|carrier-invoice|
» type|smc|
» type|bol|

> Example responses

```json
{
  "leg_file": {
    "id": "string",
    "created_at": "2018-09-19T05:22:07Z",
    "updated_at": "2018-09-19T05:22:07Z",
    "org_id": "string",
    "leg_id": "string",
    "uploaded_by": "string",
    "uploaded_at": "string",
    "type": "other",
    "url": "string",
    "description": "string",
    "latitude": 0,
    "longitude": 0,
    "metadata": {},
    "task_id": "string"
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="addLegFileByLegId-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="addLegFileByLegId-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
leg_file|[LegFile](#schemalegfile)|false|The file for the leg
» id|string(uuid)|false|The uuid for the leg file
» created_at|string(date-time)|false|The timestamp for the creation of the leg file
» updated_at|string(date-time)|false|The timestamp for the last update of the leg file
» org_id|string(uuid)|false|The uuid for the organization of the leg file
» leg_id|string(uuid)|false|The uuid of the leg corresponding to the leg file
» uploaded_by|string(uuid)|false|The uuid of the user who uploaded the leg file
» uploaded_at|string(uuid)|false|The uuid
» type|string|false|The type of leg file
» url|string|false|The url location for the leg file
» description|string|false|A description of the leg file
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» metadata|object|false|Metadata object for the leg file
» task_id|string(uuid)|false|The task id of the leg that corresponds to the leg file



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: legs )
</aside>

## uploadLegBOLByLegID

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/legs/{legID}/upload_bol \
  -H 'Content-Type: multipart/form-data' \
  -H 'Accept: application/json'

```

```http
POST https://platform.roserocket.com/v1/legs/{legID}/upload_bol HTTP/1.1
Host: platform.roserocket.com
Content-Type: multipart/form-data
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/legs/{legID}/upload_bol',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "file": "string"
}';
const headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/legs/{legID}/upload_bol',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'multipart/form-data',
  'Accept' => 'application/json'
}

result = RestClient.post 'https://platform.roserocket.com/v1/legs/{legID}/upload_bol',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'Accept': 'application/json'
}

r = requests.post('https://platform.roserocket.com/v1/legs/{legID}/upload_bol', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/legs/{legID}/upload_bol");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /legs/{legID}/upload_bol`

*Upload BOL for a specified leg*

> Body parameter

```yaml
file: string

```
<h3 id="uploadLegBOLByLegID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
legID|path|string|true|ID of the leg. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.
body|body|[uploadLegBOLByLegID](#schema+uploadlegbolbylegid)|false|No description
» file|body|string(binary)|true|File to upload


> Example responses

```json
{
  "leg_file": {
    "id": "string",
    "created_at": "2018-09-19T05:22:07Z",
    "updated_at": "2018-09-19T05:22:07Z",
    "org_id": "string",
    "leg_id": "string",
    "uploaded_by": "string",
    "uploaded_at": "string",
    "type": "other",
    "url": "string",
    "description": "string",
    "latitude": 0,
    "longitude": 0,
    "metadata": {},
    "task_id": "string"
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="uploadLegBOLByLegID-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="uploadLegBOLByLegID-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
leg_file|[LegFile](#schemalegfile)|false|The file for the leg
» id|string(uuid)|false|The uuid for the leg file
» created_at|string(date-time)|false|The timestamp for the creation of the leg file
» updated_at|string(date-time)|false|The timestamp for the last update of the leg file
» org_id|string(uuid)|false|The uuid for the organization of the leg file
» leg_id|string(uuid)|false|The uuid of the leg corresponding to the leg file
» uploaded_by|string(uuid)|false|The uuid of the user who uploaded the leg file
» uploaded_at|string(uuid)|false|The uuid
» type|string|false|The type of leg file
» url|string|false|The url location for the leg file
» description|string|false|A description of the leg file
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» metadata|object|false|Metadata object for the leg file
» task_id|string(uuid)|false|The task id of the leg that corresponds to the leg file



<aside class="success">
This operation does not require authentication
</aside>

## uploadLegFileByLegID

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/legs/{legID}/upload_file \
  -H 'Content-Type: multipart/form-data' \
  -H 'Accept: application/json'

```

```http
POST https://platform.roserocket.com/v1/legs/{legID}/upload_file HTTP/1.1
Host: platform.roserocket.com
Content-Type: multipart/form-data
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/legs/{legID}/upload_file',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "file": "string",
  "type": "other"
}';
const headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/legs/{legID}/upload_file',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'multipart/form-data',
  'Accept' => 'application/json'
}

result = RestClient.post 'https://platform.roserocket.com/v1/legs/{legID}/upload_file',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'Accept': 'application/json'
}

r = requests.post('https://platform.roserocket.com/v1/legs/{legID}/upload_file', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/legs/{legID}/upload_file");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /legs/{legID}/upload_file`

*Upload file for a specified leg*

> Body parameter

```yaml
file: string
type: other

```
<h3 id="uploadLegFileByLegID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
legID|path|string|true|ID of the leg. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.
body|body|[uploadLegFileByLegID](#schema+uploadlegfilebylegid)|false|No description
» file|body|string(binary)|true|File to upload
» type|body|string|false|Type of leg file to upload


#### Enumerated Values

|Parameter|Value|
|---|---|
» type|other|
» type|comm-invoice|
» type|pod|
» type|pop|
» type|pod-sig|
» type|pop-sig|
» type|carrier-invoice|
» type|smc|
» type|bol|

> Example responses

```json
{
  "leg_file": {
    "id": "string",
    "created_at": "2018-09-19T05:22:07Z",
    "updated_at": "2018-09-19T05:22:07Z",
    "org_id": "string",
    "leg_id": "string",
    "uploaded_by": "string",
    "uploaded_at": "string",
    "type": "other",
    "url": "string",
    "description": "string",
    "latitude": 0,
    "longitude": 0,
    "metadata": {},
    "task_id": "string"
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="uploadLegFileByLegID-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="uploadLegFileByLegID-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
leg_file|[LegFile](#schemalegfile)|false|The file for the leg
» id|string(uuid)|false|The uuid for the leg file
» created_at|string(date-time)|false|The timestamp for the creation of the leg file
» updated_at|string(date-time)|false|The timestamp for the last update of the leg file
» org_id|string(uuid)|false|The uuid for the organization of the leg file
» leg_id|string(uuid)|false|The uuid of the leg corresponding to the leg file
» uploaded_by|string(uuid)|false|The uuid of the user who uploaded the leg file
» uploaded_at|string(uuid)|false|The uuid
» type|string|false|The type of leg file
» url|string|false|The url location for the leg file
» description|string|false|A description of the leg file
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» metadata|object|false|Metadata object for the leg file
» task_id|string(uuid)|false|The task id of the leg that corresponds to the leg file



<aside class="success">
This operation does not require authentication
</aside>

## updateUploadedFileByLegAndFileID

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/legs/{legID}/upload_file/{fileID} \
  -H 'Content-Type: multipart/form-data' \
  -H 'Accept: application/json'

```

```http
PUT https://platform.roserocket.com/v1/legs/{legID}/upload_file/{fileID} HTTP/1.1
Host: platform.roserocket.com
Content-Type: multipart/form-data
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/legs/{legID}/upload_file/{fileID}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "file": "string",
  "type": "other"
}';
const headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/legs/{legID}/upload_file/{fileID}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'multipart/form-data',
  'Accept' => 'application/json'
}

result = RestClient.put 'https://platform.roserocket.com/v1/legs/{legID}/upload_file/{fileID}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'Accept': 'application/json'
}

r = requests.put('https://platform.roserocket.com/v1/legs/{legID}/upload_file/{fileID}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/legs/{legID}/upload_file/{fileID}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /legs/{legID}/upload_file/{fileID}`

*Update an uploaded file for a specified leg*

> Body parameter

```yaml
file: string
type: other

```
<h3 id="updateUploadedFileByLegAndFileID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
legID|path|string|true|ID of the leg to get files for. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.
fileID|path|string|true|ID of the leg file.
body|body|[uploadLegFileByLegID](#schema+uploadlegfilebylegid)|false|No description
» file|body|string(binary)|true|File to upload
» type|body|string|false|Type of leg file to upload


#### Enumerated Values

|Parameter|Value|
|---|---|
» type|other|
» type|comm-invoice|
» type|pod|
» type|pop|
» type|pod-sig|
» type|pop-sig|
» type|carrier-invoice|
» type|smc|
» type|bol|

> Example responses

```json
{
  "leg_file": {
    "id": "string",
    "created_at": "2018-09-19T05:22:07Z",
    "updated_at": "2018-09-19T05:22:07Z",
    "org_id": "string",
    "leg_id": "string",
    "uploaded_by": "string",
    "uploaded_at": "string",
    "type": "other",
    "url": "string",
    "description": "string",
    "latitude": 0,
    "longitude": 0,
    "metadata": {},
    "task_id": "string"
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="updateUploadedFileByLegAndFileID-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="updateUploadedFileByLegAndFileID-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
leg_file|[LegFile](#schemalegfile)|false|The file for the leg
» id|string(uuid)|false|The uuid for the leg file
» created_at|string(date-time)|false|The timestamp for the creation of the leg file
» updated_at|string(date-time)|false|The timestamp for the last update of the leg file
» org_id|string(uuid)|false|The uuid for the organization of the leg file
» leg_id|string(uuid)|false|The uuid of the leg corresponding to the leg file
» uploaded_by|string(uuid)|false|The uuid of the user who uploaded the leg file
» uploaded_at|string(uuid)|false|The uuid
» type|string|false|The type of leg file
» url|string|false|The url location for the leg file
» description|string|false|A description of the leg file
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» metadata|object|false|Metadata object for the leg file
» task_id|string(uuid)|false|The task id of the leg that corresponds to the leg file



<aside class="success">
This operation does not require authentication
</aside>

## getLegsByOrder

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/orders/{orderID}/legs \
  -H 'Accept: application/json'

```

```http
GET https://platform.roserocket.com/v1/orders/{orderID}/legs HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/orders/{orderID}/legs',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/orders/{orderID}/legs',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://platform.roserocket.com/v1/orders/{orderID}/legs',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://platform.roserocket.com/v1/orders/{orderID}/legs', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/orders/{orderID}/legs");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /orders/{orderID}/legs`

*Get legs by order ID*

<h3 id="getLegsByOrder-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
orderID|path|string|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.


> Example responses

```json
{
  "legs": [
    {
      "id": "string",
      "sequence_id": 0,
      "version": 0,
      "external_id": "string",
      "public_id": "string",
      "order_id": "string",
      "manifest_id": "string",
      "origin_stop_id": "string",
      "destination_stop_id": "string",
      "origin": {
        "terminal_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0
      },
      "destination": {
        "terminal_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0
      },
      "status": "available",
      "origin_start_at": "2018-09-19T05:22:07Z",
      "origin_end_at": "2018-09-19T05:22:07Z",
      "origin_appt_start_at": "2018-09-19T05:22:07Z",
      "origin_appt_end_at": "2018-09-19T05:22:07Z",
      "destination_start_at": "2018-09-19T05:22:07Z",
      "destination_end_at": "2018-09-19T05:22:07Z",
      "destination_appt_start_at": "2018-09-19T05:22:07Z",
      "destination_appt_end_at": "2018-09-19T05:22:07Z",
      "commodities": [
        {
          "id": "string",
          "measurement_unit": "inch",
          "weight_unit": "lb",
          "freight_class": "string",
          "commodity_type": "skid",
          "commodity_type_other": "string",
          "description": "string",
          "feet": 0,
          "volume": 0,
          "length": 0,
          "width": 0,
          "height": 0,
          "weight": 0,
          "nmfc": "string",
          "is_stackable": true,
          "quantity": 0,
          "pieces": 0,
          "sku": "string"
        }
      ],
      "accessorials": [
        "string"
      ],
      "history": {
        "origin_arrived_at": "2018-09-19T05:22:07Z",
        "origin_in_at": "2018-09-19T05:22:07Z",
        "origin_pickedup_at": "2018-09-19T05:22:07Z",
        "origin_out_at": "2018-09-19T05:22:07Z",
        "destination_arrived_at": "2018-09-19T05:22:07Z",
        "destination_in_at": "2018-09-19T05:22:07Z",
        "destination_delivered_at": "2018-09-19T05:22:07Z",
        "destination_out_at": "2018-09-19T05:22:07Z"
      }
    }
  ]
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="getLegsByOrder-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="getLegsByOrder-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
legs|[[Leg](#schemaleg)]|false|No description
» id|string(uuid)|false|Auto generated system ID
» sequence_id|integer|false|Auto generated sequence ID per customer
» version|integer|false|Auto generated version number (incremental)
» external_id|string|false|External ID for mapping the leg to an external system. This field value can be _null_
» public_id|string|false|Auto generated human readable ID
» order_id|string|false|Related order ID
» manifest_id|string|false|Related manifest ID (assigned). This field value can be _null_
» origin_stop_id|string|false|Stop ID of the origin (only if this leg has been assigned to a manifest). This field value can be _null_
» destination_stop_id|string|false|Stop ID of the destination (only if this leg has been assigned to a manifest). This field value can be _null_
» origin|[LegAddress](#schemalegaddress)|false|Leg address
»» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» destination|[LegAddress](#schemalegaddress)|false|Leg address
»» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» status|string|false|Leg Status
» origin_start_at|string(date-time)|false|Origin ready time range (start)
» origin_end_at|string(date-time)|false|Origin ready time range (end)
» origin_appt_start_at|string(date-time)|false|Origin appointment time range (start). This field value can be _null_
» origin_appt_end_at|string(date-time)|false|Origin appointment time range (end). This field value can be _null_
» destination_start_at|string(date-time)|false|Destination expected time range (start). This field value can be _null_
» destination_end_at|string(date-time)|false|Destination expected time range (end). This field value can be _null_
» destination_appt_start_at|string(date-time)|false|Destination appointment time range (start). This field value can be _null_
» destination_appt_end_at|string(date-time)|false|Destination appointment time range (end). This field value can be _null_
» history|[LegHistory](#schemaleghistory)|false|Historical timestamps of a leg
»» origin_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at origin
»» origin_in_at|string(date-time)|false|The timestamp of when the driver/partner in at origin
»» origin_pickedup_at|string(date-time)|false|The timestamp of when the driver/partner picked up at origin
»» origin_out_at|string(date-time)|false|The timestamp of when the driver/partner out at origin
»» destination_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at destination
»» destination_in_at|string(date-time)|false|The timestamp of when the driver/partner in at destination
»» destination_delivered_at|string(date-time)|false|The timestamp of when the driver/partner delievered up at destination
»» destination_out_at|string(date-time)|false|The timestamp of when the driver/partner out at destination
» commodities|[[Commodity](#schemacommodity)]|false|Commodities items
»» id|string(uuid)|false|Auto generated commodity id
»» measurement_unit|string|false|Measurement unit
»» weight_unit|string|false|Weight unit
»» freight_class|string|false|Freight class
»» commodity_type|string|false|Commodity type
»» commodity_type_other|string|false|If commodity type is set to _other_, then this field must have value
»» description|string|false|Description of the commodity
»» feet|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»» volume|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»» length|number(float)|false|Length of the commodity
»» width|number(float)|false|Width of the commodity
»» height|number(float)|false|Height of the commodity
»» weight|number(float)|false|Weight of the commodity
»» nmfc|string|false|NMFC number
»» is_stackable|boolean|false|Is this commodity can be stacked?
»» quantity|integer|false|Quantity of the commodity
»» pieces|integer|false|Total number of pieces. This field value can be _null_
»» sku|string|false|SKU number
» accessorials|[string(uuid)]|false|No description



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: legs )
</aside>

## getLegByID

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/legs/{legID} \
  -H 'Accept: application/json'

```

```http
GET https://platform.roserocket.com/v1/legs/{legID} HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/legs/{legID}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/legs/{legID}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://platform.roserocket.com/v1/legs/{legID}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://platform.roserocket.com/v1/legs/{legID}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/legs/{legID}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /legs/{legID}`

*Get leg by ID*

<h3 id="getLegByID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
legID|path|string|true|ID of the leg. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.


> Example responses

```json
{
  "leg": {
    "id": "string",
    "sequence_id": 0,
    "version": 0,
    "external_id": "string",
    "public_id": "string",
    "order_id": "string",
    "manifest_id": "string",
    "origin_stop_id": "string",
    "destination_stop_id": "string",
    "origin": {
      "terminal_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0
    },
    "destination": {
      "terminal_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0
    },
    "status": "available",
    "origin_start_at": "2018-09-19T05:22:07Z",
    "origin_end_at": "2018-09-19T05:22:07Z",
    "origin_appt_start_at": "2018-09-19T05:22:07Z",
    "origin_appt_end_at": "2018-09-19T05:22:07Z",
    "destination_start_at": "2018-09-19T05:22:07Z",
    "destination_end_at": "2018-09-19T05:22:07Z",
    "destination_appt_start_at": "2018-09-19T05:22:07Z",
    "destination_appt_end_at": "2018-09-19T05:22:07Z",
    "commodities": [
      {
        "id": "string",
        "measurement_unit": "inch",
        "weight_unit": "lb",
        "freight_class": "string",
        "commodity_type": "skid",
        "commodity_type_other": "string",
        "description": "string",
        "feet": 0,
        "volume": 0,
        "length": 0,
        "width": 0,
        "height": 0,
        "weight": 0,
        "nmfc": "string",
        "is_stackable": true,
        "quantity": 0,
        "pieces": 0,
        "sku": "string"
      }
    ],
    "accessorials": [
      "string"
    ],
    "history": {
      "origin_arrived_at": "2018-09-19T05:22:07Z",
      "origin_in_at": "2018-09-19T05:22:07Z",
      "origin_pickedup_at": "2018-09-19T05:22:07Z",
      "origin_out_at": "2018-09-19T05:22:07Z",
      "destination_arrived_at": "2018-09-19T05:22:07Z",
      "destination_in_at": "2018-09-19T05:22:07Z",
      "destination_delivered_at": "2018-09-19T05:22:07Z",
      "destination_out_at": "2018-09-19T05:22:07Z"
    }
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="getLegByID-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="getLegByID-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
leg|[Leg](#schemaleg)|false|Leg
» id|string(uuid)|false|Auto generated system ID
» sequence_id|integer|false|Auto generated sequence ID per customer
» version|integer|false|Auto generated version number (incremental)
» external_id|string|false|External ID for mapping the leg to an external system. This field value can be _null_
» public_id|string|false|Auto generated human readable ID
» order_id|string|false|Related order ID
» manifest_id|string|false|Related manifest ID (assigned). This field value can be _null_
» origin_stop_id|string|false|Stop ID of the origin (only if this leg has been assigned to a manifest). This field value can be _null_
» destination_stop_id|string|false|Stop ID of the destination (only if this leg has been assigned to a manifest). This field value can be _null_
» origin|[LegAddress](#schemalegaddress)|false|Leg address
»» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» destination|[LegAddress](#schemalegaddress)|false|Leg address
»» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» status|string|false|Leg Status
» origin_start_at|string(date-time)|false|Origin ready time range (start)
» origin_end_at|string(date-time)|false|Origin ready time range (end)
» origin_appt_start_at|string(date-time)|false|Origin appointment time range (start). This field value can be _null_
» origin_appt_end_at|string(date-time)|false|Origin appointment time range (end). This field value can be _null_
» destination_start_at|string(date-time)|false|Destination expected time range (start). This field value can be _null_
» destination_end_at|string(date-time)|false|Destination expected time range (end). This field value can be _null_
» destination_appt_start_at|string(date-time)|false|Destination appointment time range (start). This field value can be _null_
» destination_appt_end_at|string(date-time)|false|Destination appointment time range (end). This field value can be _null_
» history|[LegHistory](#schemaleghistory)|false|Historical timestamps of a leg
»» origin_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at origin
»» origin_in_at|string(date-time)|false|The timestamp of when the driver/partner in at origin
»» origin_pickedup_at|string(date-time)|false|The timestamp of when the driver/partner picked up at origin
»» origin_out_at|string(date-time)|false|The timestamp of when the driver/partner out at origin
»» destination_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at destination
»» destination_in_at|string(date-time)|false|The timestamp of when the driver/partner in at destination
»» destination_delivered_at|string(date-time)|false|The timestamp of when the driver/partner delievered up at destination
»» destination_out_at|string(date-time)|false|The timestamp of when the driver/partner out at destination
» commodities|[[Commodity](#schemacommodity)]|false|Commodities items
»» id|string(uuid)|false|Auto generated commodity id
»» measurement_unit|string|false|Measurement unit
»» weight_unit|string|false|Weight unit
»» freight_class|string|false|Freight class
»» commodity_type|string|false|Commodity type
»» commodity_type_other|string|false|If commodity type is set to _other_, then this field must have value
»» description|string|false|Description of the commodity
»» feet|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»» volume|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»» length|number(float)|false|Length of the commodity
»» width|number(float)|false|Width of the commodity
»» height|number(float)|false|Height of the commodity
»» weight|number(float)|false|Weight of the commodity
»» nmfc|string|false|NMFC number
»» is_stackable|boolean|false|Is this commodity can be stacked?
»» quantity|integer|false|Quantity of the commodity
»» pieces|integer|false|Total number of pieces. This field value can be _null_
»» sku|string|false|SKU number
» accessorials|[string(uuid)]|false|No description



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: legs )
</aside>

# manifest

## getManifestByID

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/manifests/{manifestID} \
  -H 'Accept: application/json'

```

```http
GET https://platform.roserocket.com/v1/manifests/{manifestID} HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/manifests/{manifestID}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/manifests/{manifestID}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://platform.roserocket.com/v1/manifests/{manifestID}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://platform.roserocket.com/v1/manifests/{manifestID}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/manifests/{manifestID}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /manifests/{manifestID}`

*Get manifest by ID*

<h3 id="getManifestByID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
manifestID|path|string|true|ID of the manifest. It could also be the external ID of the manifest, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the manifest's external ID is __test123__ then the value of manifestID should be __ext:test1234__ or __external_id:test1234__.


> Example responses

```json
{
  "manifest": {
    "id": "string",
    "nickname": "string",
    "org_id": "string",
    "vehicle_id": "string",
    "dispathcer_user_id": "string",
    "driver_user_id": "string",
    "trailer_id": "string",
    "partner_carrier_id": "string",
    "partner_carrier_service_id": "string",
    "sequential_id": "string",
    "full_id": "string",
    "scheduled_at": "2018-09-19T05:22:07Z",
    "status": "planning",
    "dispatched_at": "2018-09-19T05:22:07Z",
    "completed_at": "2018-09-19T05:22:07Z"
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="getManifestByID-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="getManifestByID-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
manifest|[Manifest](#schemamanifest)|false|No description
» id|string(uuid)|false|Id of the manifest
» nickname|string|false|The nickname for the manifest
» org_id|string(uuid)|false|Id of the organization to which the manifest belongs
» vehicle_id|string(uuid)|false|Id of the vehicle corresponding to the manifest
» dispathcer_user_id|string(uuid)|false|Id of the dispatcher of the manifest
» driver_user_id|string(uuid)|false|Id of the driver corresponding to the manifest
» trailer_id|string(uuid)|false|Id of the trailer corresponding to the manifest
» partner_carrier_id|string(uuid)|false|Id of the partner/carrier that corresponds to the manifest
» partner_carrier_service_id|string(uuid)|false|Id of the partner/carrier service that corresponds to the manifest
» sequential_id|string(uuid)|false|The manifest's sequential id
» full_id|string(uuid)|false|The full id of the string
» scheduled_at|string(date-time)|false|The time at which the manifest was scheduled
» status|string|false|The status of the manifest
» dispatched_at|string(date-time)|false|The time at which the manifest was dispatched
» completed_at|string(date-time)|false|The time at which the manifest was completed



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: manifests )
</aside>

## getLegsByManifestID

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/manifests/{manifestID}/legs \
  -H 'Accept: application/json'

```

```http
GET https://platform.roserocket.com/v1/manifests/{manifestID}/legs HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/manifests/{manifestID}/legs',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/manifests/{manifestID}/legs',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://platform.roserocket.com/v1/manifests/{manifestID}/legs',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://platform.roserocket.com/v1/manifests/{manifestID}/legs', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/manifests/{manifestID}/legs");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /manifests/{manifestID}/legs`

*Get legs by manifest ID*

<h3 id="getLegsByManifestID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
manifestID|path|string|true|ID of the manifest for which to get legs. It could also be the external ID of the manifest, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the manifest's external ID is __test123__ then the value of manifestID should be __ext:test1234__ or __external_id:test1234__.


> Example responses

```json
{
  "legs": [
    {
      "id": "string",
      "sequence_id": 0,
      "version": 0,
      "external_id": "string",
      "public_id": "string",
      "order_id": "string",
      "manifest_id": "string",
      "origin_stop_id": "string",
      "destination_stop_id": "string",
      "origin": {
        "terminal_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0
      },
      "destination": {
        "terminal_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0
      },
      "status": "available",
      "origin_start_at": "2018-09-19T05:22:07Z",
      "origin_end_at": "2018-09-19T05:22:07Z",
      "origin_appt_start_at": "2018-09-19T05:22:07Z",
      "origin_appt_end_at": "2018-09-19T05:22:07Z",
      "destination_start_at": "2018-09-19T05:22:07Z",
      "destination_end_at": "2018-09-19T05:22:07Z",
      "destination_appt_start_at": "2018-09-19T05:22:07Z",
      "destination_appt_end_at": "2018-09-19T05:22:07Z",
      "commodities": [
        {
          "id": "string",
          "measurement_unit": "inch",
          "weight_unit": "lb",
          "freight_class": "string",
          "commodity_type": "skid",
          "commodity_type_other": "string",
          "description": "string",
          "feet": 0,
          "volume": 0,
          "length": 0,
          "width": 0,
          "height": 0,
          "weight": 0,
          "nmfc": "string",
          "is_stackable": true,
          "quantity": 0,
          "pieces": 0,
          "sku": "string"
        }
      ],
      "accessorials": [
        "string"
      ],
      "history": {
        "origin_arrived_at": "2018-09-19T05:22:07Z",
        "origin_in_at": "2018-09-19T05:22:07Z",
        "origin_pickedup_at": "2018-09-19T05:22:07Z",
        "origin_out_at": "2018-09-19T05:22:07Z",
        "destination_arrived_at": "2018-09-19T05:22:07Z",
        "destination_in_at": "2018-09-19T05:22:07Z",
        "destination_delivered_at": "2018-09-19T05:22:07Z",
        "destination_out_at": "2018-09-19T05:22:07Z"
      }
    }
  ]
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="getLegsByManifestID-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="getLegsByManifestID-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
legs|[[Leg](#schemaleg)]|false|No description
» id|string(uuid)|false|Auto generated system ID
» sequence_id|integer|false|Auto generated sequence ID per customer
» version|integer|false|Auto generated version number (incremental)
» external_id|string|false|External ID for mapping the leg to an external system. This field value can be _null_
» public_id|string|false|Auto generated human readable ID
» order_id|string|false|Related order ID
» manifest_id|string|false|Related manifest ID (assigned). This field value can be _null_
» origin_stop_id|string|false|Stop ID of the origin (only if this leg has been assigned to a manifest). This field value can be _null_
» destination_stop_id|string|false|Stop ID of the destination (only if this leg has been assigned to a manifest). This field value can be _null_
» origin|[LegAddress](#schemalegaddress)|false|Leg address
»» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» destination|[LegAddress](#schemalegaddress)|false|Leg address
»» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» status|string|false|Leg Status
» origin_start_at|string(date-time)|false|Origin ready time range (start)
» origin_end_at|string(date-time)|false|Origin ready time range (end)
» origin_appt_start_at|string(date-time)|false|Origin appointment time range (start). This field value can be _null_
» origin_appt_end_at|string(date-time)|false|Origin appointment time range (end). This field value can be _null_
» destination_start_at|string(date-time)|false|Destination expected time range (start). This field value can be _null_
» destination_end_at|string(date-time)|false|Destination expected time range (end). This field value can be _null_
» destination_appt_start_at|string(date-time)|false|Destination appointment time range (start). This field value can be _null_
» destination_appt_end_at|string(date-time)|false|Destination appointment time range (end). This field value can be _null_
» history|[LegHistory](#schemaleghistory)|false|Historical timestamps of a leg
»» origin_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at origin
»» origin_in_at|string(date-time)|false|The timestamp of when the driver/partner in at origin
»» origin_pickedup_at|string(date-time)|false|The timestamp of when the driver/partner picked up at origin
»» origin_out_at|string(date-time)|false|The timestamp of when the driver/partner out at origin
»» destination_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at destination
»» destination_in_at|string(date-time)|false|The timestamp of when the driver/partner in at destination
»» destination_delivered_at|string(date-time)|false|The timestamp of when the driver/partner delievered up at destination
»» destination_out_at|string(date-time)|false|The timestamp of when the driver/partner out at destination
» commodities|[[Commodity](#schemacommodity)]|false|Commodities items
»» id|string(uuid)|false|Auto generated commodity id
»» measurement_unit|string|false|Measurement unit
»» weight_unit|string|false|Weight unit
»» freight_class|string|false|Freight class
»» commodity_type|string|false|Commodity type
»» commodity_type_other|string|false|If commodity type is set to _other_, then this field must have value
»» description|string|false|Description of the commodity
»» feet|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»» volume|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»» length|number(float)|false|Length of the commodity
»» width|number(float)|false|Width of the commodity
»» height|number(float)|false|Height of the commodity
»» weight|number(float)|false|Weight of the commodity
»» nmfc|string|false|NMFC number
»» is_stackable|boolean|false|Is this commodity can be stacked?
»» quantity|integer|false|Quantity of the commodity
»» pieces|integer|false|Total number of pieces. This field value can be _null_
»» sku|string|false|SKU number
» accessorials|[string(uuid)]|false|No description



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: manifests )
</aside>

## createNotesByManifestID

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/manifests/{manifestID}/notes \
  -H 'Accept: application/json'

```

```http
POST https://platform.roserocket.com/v1/manifests/{manifestID}/notes HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/manifests/{manifestID}/notes',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/manifests/{manifestID}/notes',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'https://platform.roserocket.com/v1/manifests/{manifestID}/notes',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('https://platform.roserocket.com/v1/manifests/{manifestID}/notes', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/manifests/{manifestID}/notes");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /manifests/{manifestID}/notes`

*Create notes event for a manifest by manifest ID*

<h3 id="createNotesByManifestID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
manifestID|path|string|true|ID of the manifest for which to create a notes event. It could also be the external ID of the manifest, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the manifest's external ID is __test123__ then the value of manifestID should be __ext:test1234__ or __external_id:test1234__.


> Example responses

```json
{
  "event": {
    "id": "string",
    "created_at": "2018-09-19T05:22:07Z",
    "updated_at": "2018-09-19T05:22:07Z",
    "user_id": "2018-09-19T05:22:07Z",
    "manifest_id": "string",
    "data": {
      "author": "string",
      "text": "string",
      "type": "notes"
    }
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="createNotesByManifestID-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="createNotesByManifestID-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
event|[ManifestEvent](#schemamanifestevent)|false|No description
» id|string(uuid)|false|The id of the manifest event
» created_at|string(date-time)|false|The time of the event's creation
» updated_at|string(date-time)|false|The time the event was last updated
» user_id|string(date-time)|false|The id of the user who created the event
» manifest_id|string(uuid)|false|The id of the manifest for which the event belongs
» data|object|false|No description
»» author|string|false|The name of the user who authored the event
»» text|string|false|The contents of the message
»» type|string|false|The type of manifest message



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: manifests )
</aside>

## getStopsByManifestID

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/manifests/{manifestID}/stops \
  -H 'Accept: application/json'

```

```http
GET https://platform.roserocket.com/v1/manifests/{manifestID}/stops HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/manifests/{manifestID}/stops',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/manifests/{manifestID}/stops',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://platform.roserocket.com/v1/manifests/{manifestID}/stops',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://platform.roserocket.com/v1/manifests/{manifestID}/stops', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/manifests/{manifestID}/stops");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /manifests/{manifestID}/stops`

*Get stops by manifest ID*

<h3 id="getStopsByManifestID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
manifestID|path|string|true|ID of the manifest for which to get stops. It could also be the external ID of the manifest, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the manifest's external ID is __test123__ then the value of manifestID should be __ext:test1234__ or __external_id:test1234__.


> Example responses

```json
{
  "stops": [
    {
      "id": "string",
      "manifest_id": "string",
      "ordinal": 0,
      "type": "stop",
      "schedule_start_at": "2018-09-19T05:22:07Z",
      "schedule_end_at": "2018-09-19T05:22:07Z",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0
    }
  ]
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="getStopsByManifestID-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="getStopsByManifestID-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
stops|[[Stop](#schemastop)]|false|No description
» id|string(uuid)|false|Auto generated system ID
» manifest_id|string|false|Related Manifest ID
» ordinal|integer|false|Ordinal of the stop in the manifest
» type|string|false|Stop Type
» schedule_start_at|string(date-time)|false|Scheduled time range (start)
» schedule_end_at|string(date-time)|false|Scheduled time range (end)
» org_name|string|false|Organization name
» contact_name|string|false|Contact name
» address_1|string|false|Address line 1
» address_2|string|false|Address line 2
» suite|string|false|Suite number
» city|string|false|City
» state|string|false|State / Province
» country|string|false|Country (2 letter ISO)
» postal|string|false|Postal / Zip code
» phone|string|false|Phone number
» phone_ext|string|false|Phone extension
» email|string|false|Email
» fax|string|false|Fax
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: manifests )
</aside>

## getManifestStopByID

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/manifests/{manifestID}/stops/{stopID} \
  -H 'Accept: application/json'

```

```http
GET https://platform.roserocket.com/v1/manifests/{manifestID}/stops/{stopID} HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/manifests/{manifestID}/stops/{stopID}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/manifests/{manifestID}/stops/{stopID}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://platform.roserocket.com/v1/manifests/{manifestID}/stops/{stopID}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://platform.roserocket.com/v1/manifests/{manifestID}/stops/{stopID}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/manifests/{manifestID}/stops/{stopID}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /manifests/{manifestID}/stops/{stopID}`

*Get manifest's stop by ID*

<h3 id="getManifestStopByID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
manifestID|path|string|true|ID of the manifest. It could also be the external ID of the manifest, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the manifest's external ID is __test123__ then the value of manifestID should be __ext:test1234__ or __external_id:test1234__.
stopID|path|string(uuid)|true|ID of the stop


> Example responses

```json
{
  "stop": {
    "id": "string",
    "manifest_id": "string",
    "ordinal": 0,
    "type": "stop",
    "schedule_start_at": "2018-09-19T05:22:07Z",
    "schedule_end_at": "2018-09-19T05:22:07Z",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="getManifestStopByID-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="getManifestStopByID-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
stop|[Stop](#schemastop)|false|Stop
» id|string(uuid)|false|Auto generated system ID
» manifest_id|string|false|Related Manifest ID
» ordinal|integer|false|Ordinal of the stop in the manifest
» type|string|false|Stop Type
» schedule_start_at|string(date-time)|false|Scheduled time range (start)
» schedule_end_at|string(date-time)|false|Scheduled time range (end)
» org_name|string|false|Organization name
» contact_name|string|false|Contact name
» address_1|string|false|Address line 1
» address_2|string|false|Address line 2
» suite|string|false|Suite number
» city|string|false|City
» state|string|false|State / Province
» country|string|false|Country (2 letter ISO)
» postal|string|false|Postal / Zip code
» phone|string|false|Phone number
» phone_ext|string|false|Phone extension
» email|string|false|Email
» fax|string|false|Fax
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: manifests )
</aside>

## updateManifestStopScheduleByID

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/manifests/{manifestID}/stops/{stopID}/update_schedule \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT https://platform.roserocket.com/v1/manifests/{manifestID}/stops/{stopID}/update_schedule HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/manifests/{manifestID}/stops/{stopID}/update_schedule',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "schedule_start_at": "2018-09-19T05:22:07Z",
  "schedule_end_at": "2018-09-19T05:22:07Z"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/manifests/{manifestID}/stops/{stopID}/update_schedule',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'https://platform.roserocket.com/v1/manifests/{manifestID}/stops/{stopID}/update_schedule',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('https://platform.roserocket.com/v1/manifests/{manifestID}/stops/{stopID}/update_schedule', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/manifests/{manifestID}/stops/{stopID}/update_schedule");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /manifests/{manifestID}/stops/{stopID}/update_schedule`

*Update manifest's stop schedule by ID*

> Body parameter

```json
{
  "schedule_start_at": "2018-09-19T05:22:07Z",
  "schedule_end_at": "2018-09-19T05:22:07Z"
}
```
<h3 id="updateManifestStopScheduleByID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
manifestID|path|string|true|ID of the manifest. It could also be the external ID of the manifest, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the manifest's external ID is __test123__ then the value of manifestID should be __ext:test1234__ or __external_id:test1234__.
stopID|path|string(uuid)|true|ID of the stop
body|body|object|true|Stop object
» schedule_start_at|body|string(date-time)|false|Schedule time range (start)
» schedule_end_at|body|string(date-time)|false|Schedule time range (start)


> Example responses

```json
{
  "stop": {
    "id": "string",
    "manifest_id": "string",
    "ordinal": 0,
    "type": "stop",
    "schedule_start_at": "2018-09-19T05:22:07Z",
    "schedule_end_at": "2018-09-19T05:22:07Z",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="updateManifestStopScheduleByID-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="updateManifestStopScheduleByID-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
stop|[Stop](#schemastop)|false|Stop
» id|string(uuid)|false|Auto generated system ID
» manifest_id|string|false|Related Manifest ID
» ordinal|integer|false|Ordinal of the stop in the manifest
» type|string|false|Stop Type
» schedule_start_at|string(date-time)|false|Scheduled time range (start)
» schedule_end_at|string(date-time)|false|Scheduled time range (end)
» org_name|string|false|Organization name
» contact_name|string|false|Contact name
» address_1|string|false|Address line 1
» address_2|string|false|Address line 2
» suite|string|false|Suite number
» city|string|false|City
» state|string|false|State / Province
» country|string|false|Country (2 letter ISO)
» postal|string|false|Postal / Zip code
» phone|string|false|Phone number
» phone_ext|string|false|Phone extension
» email|string|false|Email
» fax|string|false|Fax
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: manifests )
</aside>

# customer

Manage customers

## searchCustomers

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/customers \
  -H 'Accept: application/json'

```

```http
GET https://platform.roserocket.com/v1/customers HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://platform.roserocket.com/v1/customers',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://platform.roserocket.com/v1/customers', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /customers`

*Search customers*

<h3 id="searchCustomers-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
search_term|query|string|false|Search term
external_id|query|string|false|External ID to filter by
in_external_ids|query|array[string]|false|External IDs to filter by
offset|query|integer|false|Pagination offset
limit|query|integer|false|Pagination limit


> Example responses

```json
{
  "customers": [
    {
      "id": "string",
      "external_id": "string",
      "short_code": "string",
      "name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "default_billing_option": "prepaid",
      "default_dim_type": "ltl",
      "default_order_notes": "string",
      "currency": "cad",
      "is_active": false,
      "credit_limit": 0,
      "credit_balance": 0,
      "dispatch__contact_name": "string",
      "dispatch_contact_phone": "string",
      "dispatch_contact_email": "string",
      "billing_contact_name": "string",
      "billing_contact_phone": "string",
      "billing_contact_email": "string",
      "sales_contact_name": "string",
      "sales_contact_phone": "string",
      "sales_contact_email": "string",
      "management_contact_name": "string",
      "management_contact_phone": "string",
      "management_contact_email": "string",
      "other_contact_name": "string",
      "other_contact_phone": "string",
      "other_contact_email": "string"
    }
  ],
  "offset": 0,
  "limit": 0,
  "total": 0
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="searchCustomers-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="searchCustomers-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
offset|integer|false|No description
limit|integer|false|No description
total|integer|false|No description
customers|[[Customer](#schemacustomer)]|false|No description
» id|string(uuid)|false|Auto generated customner id
» external_id|string|false|Customer external id. This field value can be _null_
» short_code|string|false|Customer's short code
» name|string|false|Organization name
» address_1|string|false|Address line 1
» address_2|string|false|Address line 2
» suite|string|false|Suite number
» city|string|false|City
» state|string|false|State / Province
» country|string|false|Country (2 letter ISO)
» postal|string|false|Postal / Zip code
» phone|string|false|Phone number
» phone_ext|string|false|Phone extension
» email|string|false|Email
» fax|string|false|Fax
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» default_billing_option|string|false|Billing Option
» default_dim_type|string|false|Dimension type
» default_order_notes|string|false|This notes will always show up as internal note everytime an order is created for this customer
» currency|string|false|Currency used when doing billing/invoicing
» is_active|boolean|false|Is customer active?
» credit_limit|number(float)|false|Credit limit for this customer
» credit_balance|number(float)|false|Credit balance for this customer
» dispatch__contact_name|string|false|Dispatch contact name
» dispatch_contact_phone|string|false|Dispatch contact phone
» dispatch_contact_email|string|false|Dispatch contact email
» billing_contact_name|string|false|Billing contact name
» billing_contact_phone|string|false|Billing contact phone
» billing_contact_email|string|false|Billing contact email
» sales_contact_name|string|false|Sales contact name
» sales_contact_phone|string|false|Sales contact phone
» sales_contact_email|string|false|Sales contact email
» management_contact_name|string|false|Management contact name
» management_contact_phone|string|false|Management contact phone
» management_contact_email|string|false|Management contact email
» other_contact_name|string|false|Other contact name
» other_contact_phone|string|false|Other contact phone
» other_contact_email|string|false|Other contact email



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: customers )
</aside>

## createCustomer

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/customers \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST https://platform.roserocket.com/v1/customers HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "name": "string",
  "address_1": "string",
  "address_2": "string",
  "suite": "string",
  "city": "string",
  "state": "string",
  "country": "string",
  "postal": "string",
  "phone": "string",
  "phone_ext": "string",
  "email": "string",
  "fax": "string",
  "latitude": 0,
  "longitude": 0,
  "default_billing_option": "prepaid",
  "default_dim_type": "ltl",
  "default_order_notes": "string",
  "currency": "cad",
  "is_active": false,
  "credit_limit": 0,
  "credit_balance": 0,
  "dispatch__contact_name": "string",
  "dispatch_contact_phone": "string",
  "dispatch_contact_email": "string",
  "billing_contact_name": "string",
  "billing_contact_phone": "string",
  "billing_contact_email": "string",
  "sales_contact_name": "string",
  "sales_contact_phone": "string",
  "sales_contact_email": "string",
  "management_contact_name": "string",
  "management_contact_phone": "string",
  "management_contact_email": "string",
  "other_contact_name": "string",
  "other_contact_phone": "string",
  "other_contact_email": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'https://platform.roserocket.com/v1/customers',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('https://platform.roserocket.com/v1/customers', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /customers`

*Create new customer*

> Body parameter

```json
{
  "name": "string",
  "address_1": "string",
  "address_2": "string",
  "suite": "string",
  "city": "string",
  "state": "string",
  "country": "string",
  "postal": "string",
  "phone": "string",
  "phone_ext": "string",
  "email": "string",
  "fax": "string",
  "latitude": 0,
  "longitude": 0,
  "default_billing_option": "prepaid",
  "default_dim_type": "ltl",
  "default_order_notes": "string",
  "currency": "cad",
  "is_active": false,
  "credit_limit": 0,
  "credit_balance": 0,
  "dispatch__contact_name": "string",
  "dispatch_contact_phone": "string",
  "dispatch_contact_email": "string",
  "billing_contact_name": "string",
  "billing_contact_phone": "string",
  "billing_contact_email": "string",
  "sales_contact_name": "string",
  "sales_contact_phone": "string",
  "sales_contact_email": "string",
  "management_contact_name": "string",
  "management_contact_phone": "string",
  "management_contact_email": "string",
  "other_contact_name": "string",
  "other_contact_phone": "string",
  "other_contact_email": "string"
}
```
<h3 id="createCustomer-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
body|body|[Customer](#schemacustomer)|true|Order object
» id|body|string(uuid)|false|Auto generated customner id
» external_id|body|string|false|Customer external id. This field value can be _null_
» short_code|body|string|false|Customer's short code
» name|body|string|false|Organization name
» address_1|body|string|false|Address line 1
» address_2|body|string|false|Address line 2
» suite|body|string|false|Suite number
» city|body|string|false|City
» state|body|string|false|State / Province
» country|body|string|false|Country (2 letter ISO)
» postal|body|string|false|Postal / Zip code
» phone|body|string|false|Phone number
» phone_ext|body|string|false|Phone extension
» email|body|string|false|Email
» fax|body|string|false|Fax
» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_
» default_billing_option|body|string|false|Billing Option
» default_dim_type|body|string|false|Dimension type
» default_order_notes|body|string|false|This notes will always show up as internal note everytime an order is created for this customer
» currency|body|string|false|Currency used when doing billing/invoicing
» is_active|body|boolean|false|Is customer active?
» credit_limit|body|number(float)|false|Credit limit for this customer
» credit_balance|body|number(float)|false|Credit balance for this customer
» dispatch__contact_name|body|string|false|Dispatch contact name
» dispatch_contact_phone|body|string|false|Dispatch contact phone
» dispatch_contact_email|body|string|false|Dispatch contact email
» billing_contact_name|body|string|false|Billing contact name
» billing_contact_phone|body|string|false|Billing contact phone
» billing_contact_email|body|string|false|Billing contact email
» sales_contact_name|body|string|false|Sales contact name
» sales_contact_phone|body|string|false|Sales contact phone
» sales_contact_email|body|string|false|Sales contact email
» management_contact_name|body|string|false|Management contact name
» management_contact_phone|body|string|false|Management contact phone
» management_contact_email|body|string|false|Management contact email
» other_contact_name|body|string|false|Other contact name
» other_contact_phone|body|string|false|Other contact phone
» other_contact_email|body|string|false|Other contact email


#### Enumerated Values

|Parameter|Value|
|---|---|
» default_billing_option|prepaid|
» default_billing_option|collect|
» default_billing_option|thirdparty|
» default_dim_type|ltl|
» default_dim_type|ftl|
» default_dim_type|volume|
» currency|cad|
» currency|usd|

> Example responses

```json
{
  "customer": {
    "id": "string",
    "external_id": "string",
    "short_code": "string",
    "name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "default_billing_option": "prepaid",
    "default_dim_type": "ltl",
    "default_order_notes": "string",
    "currency": "cad",
    "is_active": false,
    "credit_limit": 0,
    "credit_balance": 0,
    "dispatch__contact_name": "string",
    "dispatch_contact_phone": "string",
    "dispatch_contact_email": "string",
    "billing_contact_name": "string",
    "billing_contact_phone": "string",
    "billing_contact_email": "string",
    "sales_contact_name": "string",
    "sales_contact_phone": "string",
    "sales_contact_email": "string",
    "management_contact_name": "string",
    "management_contact_phone": "string",
    "management_contact_email": "string",
    "other_contact_name": "string",
    "other_contact_phone": "string",
    "other_contact_email": "string"
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="createCustomer-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="createCustomer-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
customer|[Customer](#schemacustomer)|false|Customer
» id|string(uuid)|false|Auto generated customner id
» external_id|string|false|Customer external id. This field value can be _null_
» short_code|string|false|Customer's short code
» name|string|false|Organization name
» address_1|string|false|Address line 1
» address_2|string|false|Address line 2
» suite|string|false|Suite number
» city|string|false|City
» state|string|false|State / Province
» country|string|false|Country (2 letter ISO)
» postal|string|false|Postal / Zip code
» phone|string|false|Phone number
» phone_ext|string|false|Phone extension
» email|string|false|Email
» fax|string|false|Fax
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» default_billing_option|string|false|Billing Option
» default_dim_type|string|false|Dimension type
» default_order_notes|string|false|This notes will always show up as internal note everytime an order is created for this customer
» currency|string|false|Currency used when doing billing/invoicing
» is_active|boolean|false|Is customer active?
» credit_limit|number(float)|false|Credit limit for this customer
» credit_balance|number(float)|false|Credit balance for this customer
» dispatch__contact_name|string|false|Dispatch contact name
» dispatch_contact_phone|string|false|Dispatch contact phone
» dispatch_contact_email|string|false|Dispatch contact email
» billing_contact_name|string|false|Billing contact name
» billing_contact_phone|string|false|Billing contact phone
» billing_contact_email|string|false|Billing contact email
» sales_contact_name|string|false|Sales contact name
» sales_contact_phone|string|false|Sales contact phone
» sales_contact_email|string|false|Sales contact email
» management_contact_name|string|false|Management contact name
» management_contact_phone|string|false|Management contact phone
» management_contact_email|string|false|Management contact email
» other_contact_name|string|false|Other contact name
» other_contact_phone|string|false|Other contact phone
» other_contact_email|string|false|Other contact email



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: customers )
</aside>

## getCustomerByID

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/customers/{customerID} \
  -H 'Accept: application/json'

```

```http
GET https://platform.roserocket.com/v1/customers/{customerID} HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerID}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers/{customerID}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://platform.roserocket.com/v1/customers/{customerID}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://platform.roserocket.com/v1/customers/{customerID}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerID}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /customers/{customerID}`

*Get customer by ID*

<h3 id="getCustomerByID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.


> Example responses

```json
{
  "customer": {
    "id": "string",
    "external_id": "string",
    "short_code": "string",
    "name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "default_billing_option": "prepaid",
    "default_dim_type": "ltl",
    "default_order_notes": "string",
    "currency": "cad",
    "is_active": false,
    "credit_limit": 0,
    "credit_balance": 0,
    "dispatch__contact_name": "string",
    "dispatch_contact_phone": "string",
    "dispatch_contact_email": "string",
    "billing_contact_name": "string",
    "billing_contact_phone": "string",
    "billing_contact_email": "string",
    "sales_contact_name": "string",
    "sales_contact_phone": "string",
    "sales_contact_email": "string",
    "management_contact_name": "string",
    "management_contact_phone": "string",
    "management_contact_email": "string",
    "other_contact_name": "string",
    "other_contact_phone": "string",
    "other_contact_email": "string"
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="getCustomerByID-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="getCustomerByID-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
customer|[Customer](#schemacustomer)|false|Customer
» id|string(uuid)|false|Auto generated customner id
» external_id|string|false|Customer external id. This field value can be _null_
» short_code|string|false|Customer's short code
» name|string|false|Organization name
» address_1|string|false|Address line 1
» address_2|string|false|Address line 2
» suite|string|false|Suite number
» city|string|false|City
» state|string|false|State / Province
» country|string|false|Country (2 letter ISO)
» postal|string|false|Postal / Zip code
» phone|string|false|Phone number
» phone_ext|string|false|Phone extension
» email|string|false|Email
» fax|string|false|Fax
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» default_billing_option|string|false|Billing Option
» default_dim_type|string|false|Dimension type
» default_order_notes|string|false|This notes will always show up as internal note everytime an order is created for this customer
» currency|string|false|Currency used when doing billing/invoicing
» is_active|boolean|false|Is customer active?
» credit_limit|number(float)|false|Credit limit for this customer
» credit_balance|number(float)|false|Credit balance for this customer
» dispatch__contact_name|string|false|Dispatch contact name
» dispatch_contact_phone|string|false|Dispatch contact phone
» dispatch_contact_email|string|false|Dispatch contact email
» billing_contact_name|string|false|Billing contact name
» billing_contact_phone|string|false|Billing contact phone
» billing_contact_email|string|false|Billing contact email
» sales_contact_name|string|false|Sales contact name
» sales_contact_phone|string|false|Sales contact phone
» sales_contact_email|string|false|Sales contact email
» management_contact_name|string|false|Management contact name
» management_contact_phone|string|false|Management contact phone
» management_contact_email|string|false|Management contact email
» other_contact_name|string|false|Other contact name
» other_contact_phone|string|false|Other contact phone
» other_contact_email|string|false|Other contact email



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: customers )
</aside>

## updateCustomerByID

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/customers/{customerID} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT https://platform.roserocket.com/v1/customers/{customerID} HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerID}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "name": "string",
  "address_1": "string",
  "address_2": "string",
  "suite": "string",
  "city": "string",
  "state": "string",
  "country": "string",
  "postal": "string",
  "phone": "string",
  "phone_ext": "string",
  "email": "string",
  "fax": "string",
  "latitude": 0,
  "longitude": 0,
  "default_billing_option": "prepaid",
  "default_dim_type": "ltl",
  "default_order_notes": "string",
  "currency": "cad",
  "is_active": false,
  "credit_limit": 0,
  "credit_balance": 0,
  "dispatch__contact_name": "string",
  "dispatch_contact_phone": "string",
  "dispatch_contact_email": "string",
  "billing_contact_name": "string",
  "billing_contact_phone": "string",
  "billing_contact_email": "string",
  "sales_contact_name": "string",
  "sales_contact_phone": "string",
  "sales_contact_email": "string",
  "management_contact_name": "string",
  "management_contact_phone": "string",
  "management_contact_email": "string",
  "other_contact_name": "string",
  "other_contact_phone": "string",
  "other_contact_email": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers/{customerID}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'https://platform.roserocket.com/v1/customers/{customerID}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('https://platform.roserocket.com/v1/customers/{customerID}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerID}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /customers/{customerID}`

*Update customer by ID*

> Body parameter

```json
{
  "name": "string",
  "address_1": "string",
  "address_2": "string",
  "suite": "string",
  "city": "string",
  "state": "string",
  "country": "string",
  "postal": "string",
  "phone": "string",
  "phone_ext": "string",
  "email": "string",
  "fax": "string",
  "latitude": 0,
  "longitude": 0,
  "default_billing_option": "prepaid",
  "default_dim_type": "ltl",
  "default_order_notes": "string",
  "currency": "cad",
  "is_active": false,
  "credit_limit": 0,
  "credit_balance": 0,
  "dispatch__contact_name": "string",
  "dispatch_contact_phone": "string",
  "dispatch_contact_email": "string",
  "billing_contact_name": "string",
  "billing_contact_phone": "string",
  "billing_contact_email": "string",
  "sales_contact_name": "string",
  "sales_contact_phone": "string",
  "sales_contact_email": "string",
  "management_contact_name": "string",
  "management_contact_phone": "string",
  "management_contact_email": "string",
  "other_contact_name": "string",
  "other_contact_phone": "string",
  "other_contact_email": "string"
}
```
<h3 id="updateCustomerByID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.
body|body|[Customer](#schemacustomer)|true|Order object
» id|body|string(uuid)|false|Auto generated customner id
» external_id|body|string|false|Customer external id. This field value can be _null_
» short_code|body|string|false|Customer's short code
» name|body|string|false|Organization name
» address_1|body|string|false|Address line 1
» address_2|body|string|false|Address line 2
» suite|body|string|false|Suite number
» city|body|string|false|City
» state|body|string|false|State / Province
» country|body|string|false|Country (2 letter ISO)
» postal|body|string|false|Postal / Zip code
» phone|body|string|false|Phone number
» phone_ext|body|string|false|Phone extension
» email|body|string|false|Email
» fax|body|string|false|Fax
» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_
» default_billing_option|body|string|false|Billing Option
» default_dim_type|body|string|false|Dimension type
» default_order_notes|body|string|false|This notes will always show up as internal note everytime an order is created for this customer
» currency|body|string|false|Currency used when doing billing/invoicing
» is_active|body|boolean|false|Is customer active?
» credit_limit|body|number(float)|false|Credit limit for this customer
» credit_balance|body|number(float)|false|Credit balance for this customer
» dispatch__contact_name|body|string|false|Dispatch contact name
» dispatch_contact_phone|body|string|false|Dispatch contact phone
» dispatch_contact_email|body|string|false|Dispatch contact email
» billing_contact_name|body|string|false|Billing contact name
» billing_contact_phone|body|string|false|Billing contact phone
» billing_contact_email|body|string|false|Billing contact email
» sales_contact_name|body|string|false|Sales contact name
» sales_contact_phone|body|string|false|Sales contact phone
» sales_contact_email|body|string|false|Sales contact email
» management_contact_name|body|string|false|Management contact name
» management_contact_phone|body|string|false|Management contact phone
» management_contact_email|body|string|false|Management contact email
» other_contact_name|body|string|false|Other contact name
» other_contact_phone|body|string|false|Other contact phone
» other_contact_email|body|string|false|Other contact email


#### Enumerated Values

|Parameter|Value|
|---|---|
» default_billing_option|prepaid|
» default_billing_option|collect|
» default_billing_option|thirdparty|
» default_dim_type|ltl|
» default_dim_type|ftl|
» default_dim_type|volume|
» currency|cad|
» currency|usd|

> Example responses

```json
{
  "order": {
    "id": "string",
    "sequence_id": 0,
    "external_id": "string",
    "public_id": "string",
    "customer": {
      "id": "string",
      "external_id": "string",
      "short_code": "string"
    },
    "origin": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "destination": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "billing": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "status": "new",
    "billing_option": "prepaid",
    "notes": "string",
    "po_num": "string",
    "tender_num": "string",
    "ref_num": "string",
    "custom_broker": "string",
    "declared_value": 0,
    "declared_value_currency": "cad",
    "pickup_start_at": "2018-09-19T05:22:07Z",
    "pickup_end_at": "2018-09-19T05:22:07Z",
    "pickup_appt_start_at": "2018-09-19T05:22:07Z",
    "pickup_appt_end_at": "2018-09-19T05:22:07Z",
    "delivery_start_at": "2018-09-19T05:22:07Z",
    "delivery_end_at": "2018-09-19T05:22:07Z",
    "delivery_appt_start_at": "2018-09-19T05:22:07Z",
    "delivery_appt_end_at": "2018-09-19T05:22:07Z",
    "dim_type": "ltl",
    "commodities": [
      {
        "id": "string",
        "measurement_unit": "inch",
        "weight_unit": "lb",
        "freight_class": "string",
        "commodity_type": "skid",
        "commodity_type_other": "string",
        "description": "string",
        "feet": 0,
        "volume": 0,
        "length": 0,
        "width": 0,
        "height": 0,
        "weight": 0,
        "nmfc": "string",
        "is_stackable": true,
        "quantity": 0,
        "pieces": 0,
        "sku": "string"
      }
    ],
    "accessorials": [
      "string"
    ]
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="updateCustomerByID-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="updateCustomerByID-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
order|[Order](#schemaorder)|false|Customer's order
» id|string(uuid)|false|Auto generated system ID
» sequence_id|integer|false|Auto generated sequence ID per customer
» external_id|string|false|External ID for mapping the order to an external system. This field value can be _null_
» public_id|string|false|Auto generated human readable ID
» customer|[OrderCustomer](#schemaordercustomer)|false|Customer
»» id|string(uuid)|false|Auto generated customer id
»» external_id|string|false|Customer external id. This field value can be _null_
»» short_code|string|false|Customer's short code
» origin|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
» destination|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
» billing|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
» status|string|false|Order Status
» billing_option|string|false|Billing Option
» notes|string|false|Notes that will appear on BOL
» po_num|string|false|Purchase order numbers (if multiple use comma separated values)
» tender_num|string|false|Tender number
» ref_num|string|false|Reference number
» custom_broker|string|false|Custom broker information
» declared_value|number(float)|false|Declared value
» declared_value_currency|string|false|Declared value currency
» pickup_start_at|string(date-time)|false|Pickup time range (start)
» pickup_end_at|string(date-time)|false|Pickup time range (end)
» pickup_appt_start_at|string(date-time)|false|Pickup appointment time range (start). This field value can be _null_
» pickup_appt_end_at|string(date-time)|false|Pickup appointment time range (end). This field value can be _null_
» delivery_start_at|string(date-time)|false|Expected delivery time range (start). This field value can be _null_
» delivery_end_at|string(date-time)|false|Expected delivery time range (end). This field value can be _null_
» delivery_appt_start_at|string(date-time)|false|Delivery appointment time range (start). This field value can be _null_
» delivery_appt_end_at|string(date-time)|false|Delivery appointment time range (end). This field value can be _null_
» dim_type|string|false|Dimension type
» commodities|[[Commodity](#schemacommodity)]|false|Commodities items
»» id|string(uuid)|false|Auto generated commodity id
»» measurement_unit|string|false|Measurement unit
»» weight_unit|string|false|Weight unit
»» freight_class|string|false|Freight class
»» commodity_type|string|false|Commodity type
»» commodity_type_other|string|false|If commodity type is set to _other_, then this field must have value
»» description|string|false|Description of the commodity
»» feet|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»» volume|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»» length|number(float)|false|Length of the commodity
»» width|number(float)|false|Width of the commodity
»» height|number(float)|false|Height of the commodity
»» weight|number(float)|false|Weight of the commodity
»» nmfc|string|false|NMFC number
»» is_stackable|boolean|false|Is this commodity can be stacked?
»» quantity|integer|false|Quantity of the commodity
»» pieces|integer|false|Total number of pieces. This field value can be _null_
»» sku|string|false|SKU number
» accessorials|[string(uuid)]|false|No description



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: customers )
</aside>

## deleteCustomerByID

> Code samples

```shell
# You can also use wget
curl -X DELETE https://platform.roserocket.com/v1/customers/{customerID} \
  -H 'Accept: application/json'

```

```http
DELETE https://platform.roserocket.com/v1/customers/{customerID} HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerID}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers/{customerID}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete 'https://platform.roserocket.com/v1/customers/{customerID}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('https://platform.roserocket.com/v1/customers/{customerID}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerID}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`DELETE /customers/{customerID}`

*Delete customer by ID*

<h3 id="deleteCustomerByID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
customerID|path|string(uuid)|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.


> Example responses

```json
{
  "customer": {
    "id": "string",
    "external_id": "string",
    "short_code": "string",
    "name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "default_billing_option": "prepaid",
    "default_dim_type": "ltl",
    "default_order_notes": "string",
    "currency": "cad",
    "is_active": false,
    "credit_limit": 0,
    "credit_balance": 0,
    "dispatch__contact_name": "string",
    "dispatch_contact_phone": "string",
    "dispatch_contact_email": "string",
    "billing_contact_name": "string",
    "billing_contact_phone": "string",
    "billing_contact_email": "string",
    "sales_contact_name": "string",
    "sales_contact_phone": "string",
    "sales_contact_email": "string",
    "management_contact_name": "string",
    "management_contact_phone": "string",
    "management_contact_email": "string",
    "other_contact_name": "string",
    "other_contact_phone": "string",
    "other_contact_email": "string"
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="deleteCustomerByID-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="deleteCustomerByID-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
customer|[Customer](#schemacustomer)|false|Customer
» id|string(uuid)|false|Auto generated customner id
» external_id|string|false|Customer external id. This field value can be _null_
» short_code|string|false|Customer's short code
» name|string|false|Organization name
» address_1|string|false|Address line 1
» address_2|string|false|Address line 2
» suite|string|false|Suite number
» city|string|false|City
» state|string|false|State / Province
» country|string|false|Country (2 letter ISO)
» postal|string|false|Postal / Zip code
» phone|string|false|Phone number
» phone_ext|string|false|Phone extension
» email|string|false|Email
» fax|string|false|Fax
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» default_billing_option|string|false|Billing Option
» default_dim_type|string|false|Dimension type
» default_order_notes|string|false|This notes will always show up as internal note everytime an order is created for this customer
» currency|string|false|Currency used when doing billing/invoicing
» is_active|boolean|false|Is customer active?
» credit_limit|number(float)|false|Credit limit for this customer
» credit_balance|number(float)|false|Credit balance for this customer
» dispatch__contact_name|string|false|Dispatch contact name
» dispatch_contact_phone|string|false|Dispatch contact phone
» dispatch_contact_email|string|false|Dispatch contact email
» billing_contact_name|string|false|Billing contact name
» billing_contact_phone|string|false|Billing contact phone
» billing_contact_email|string|false|Billing contact email
» sales_contact_name|string|false|Sales contact name
» sales_contact_phone|string|false|Sales contact phone
» sales_contact_email|string|false|Sales contact email
» management_contact_name|string|false|Management contact name
» management_contact_phone|string|false|Management contact phone
» management_contact_email|string|false|Management contact email
» other_contact_name|string|false|Other contact name
» other_contact_phone|string|false|Other contact phone
» other_contact_email|string|false|Other contact email



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: customers )
</aside>

## upsertCustomerByID

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/customers/{customerExtID}/upsert \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT https://platform.roserocket.com/v1/customers/{customerExtID}/upsert HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerExtID}/upsert',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "name": "string",
  "address_1": "string",
  "address_2": "string",
  "suite": "string",
  "city": "string",
  "state": "string",
  "country": "string",
  "postal": "string",
  "phone": "string",
  "phone_ext": "string",
  "email": "string",
  "fax": "string",
  "latitude": 0,
  "longitude": 0,
  "default_billing_option": "prepaid",
  "default_dim_type": "ltl",
  "default_order_notes": "string",
  "currency": "cad",
  "is_active": false,
  "credit_limit": 0,
  "credit_balance": 0,
  "dispatch__contact_name": "string",
  "dispatch_contact_phone": "string",
  "dispatch_contact_email": "string",
  "billing_contact_name": "string",
  "billing_contact_phone": "string",
  "billing_contact_email": "string",
  "sales_contact_name": "string",
  "sales_contact_phone": "string",
  "sales_contact_email": "string",
  "management_contact_name": "string",
  "management_contact_phone": "string",
  "management_contact_email": "string",
  "other_contact_name": "string",
  "other_contact_phone": "string",
  "other_contact_email": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers/{customerExtID}/upsert',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'https://platform.roserocket.com/v1/customers/{customerExtID}/upsert',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('https://platform.roserocket.com/v1/customers/{customerExtID}/upsert', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerExtID}/upsert");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /customers/{customerExtID}/upsert`

*Upsert customer by external ID*

> Body parameter

```json
{
  "name": "string",
  "address_1": "string",
  "address_2": "string",
  "suite": "string",
  "city": "string",
  "state": "string",
  "country": "string",
  "postal": "string",
  "phone": "string",
  "phone_ext": "string",
  "email": "string",
  "fax": "string",
  "latitude": 0,
  "longitude": 0,
  "default_billing_option": "prepaid",
  "default_dim_type": "ltl",
  "default_order_notes": "string",
  "currency": "cad",
  "is_active": false,
  "credit_limit": 0,
  "credit_balance": 0,
  "dispatch__contact_name": "string",
  "dispatch_contact_phone": "string",
  "dispatch_contact_email": "string",
  "billing_contact_name": "string",
  "billing_contact_phone": "string",
  "billing_contact_email": "string",
  "sales_contact_name": "string",
  "sales_contact_phone": "string",
  "sales_contact_email": "string",
  "management_contact_name": "string",
  "management_contact_phone": "string",
  "management_contact_email": "string",
  "other_contact_name": "string",
  "other_contact_phone": "string",
  "other_contact_email": "string"
}
```
<h3 id="upsertCustomerByID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
customerExtID|path|string|true|External ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.
body|body|[Customer](#schemacustomer)|true|Order object
» id|body|string(uuid)|false|Auto generated customner id
» external_id|body|string|false|Customer external id. This field value can be _null_
» short_code|body|string|false|Customer's short code
» name|body|string|false|Organization name
» address_1|body|string|false|Address line 1
» address_2|body|string|false|Address line 2
» suite|body|string|false|Suite number
» city|body|string|false|City
» state|body|string|false|State / Province
» country|body|string|false|Country (2 letter ISO)
» postal|body|string|false|Postal / Zip code
» phone|body|string|false|Phone number
» phone_ext|body|string|false|Phone extension
» email|body|string|false|Email
» fax|body|string|false|Fax
» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_
» default_billing_option|body|string|false|Billing Option
» default_dim_type|body|string|false|Dimension type
» default_order_notes|body|string|false|This notes will always show up as internal note everytime an order is created for this customer
» currency|body|string|false|Currency used when doing billing/invoicing
» is_active|body|boolean|false|Is customer active?
» credit_limit|body|number(float)|false|Credit limit for this customer
» credit_balance|body|number(float)|false|Credit balance for this customer
» dispatch__contact_name|body|string|false|Dispatch contact name
» dispatch_contact_phone|body|string|false|Dispatch contact phone
» dispatch_contact_email|body|string|false|Dispatch contact email
» billing_contact_name|body|string|false|Billing contact name
» billing_contact_phone|body|string|false|Billing contact phone
» billing_contact_email|body|string|false|Billing contact email
» sales_contact_name|body|string|false|Sales contact name
» sales_contact_phone|body|string|false|Sales contact phone
» sales_contact_email|body|string|false|Sales contact email
» management_contact_name|body|string|false|Management contact name
» management_contact_phone|body|string|false|Management contact phone
» management_contact_email|body|string|false|Management contact email
» other_contact_name|body|string|false|Other contact name
» other_contact_phone|body|string|false|Other contact phone
» other_contact_email|body|string|false|Other contact email


#### Enumerated Values

|Parameter|Value|
|---|---|
» default_billing_option|prepaid|
» default_billing_option|collect|
» default_billing_option|thirdparty|
» default_dim_type|ltl|
» default_dim_type|ftl|
» default_dim_type|volume|
» currency|cad|
» currency|usd|

> Example responses

```json
{
  "customer": {
    "id": "string",
    "external_id": "string",
    "short_code": "string",
    "name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "default_billing_option": "prepaid",
    "default_dim_type": "ltl",
    "default_order_notes": "string",
    "currency": "cad",
    "is_active": false,
    "credit_limit": 0,
    "credit_balance": 0,
    "dispatch__contact_name": "string",
    "dispatch_contact_phone": "string",
    "dispatch_contact_email": "string",
    "billing_contact_name": "string",
    "billing_contact_phone": "string",
    "billing_contact_email": "string",
    "sales_contact_name": "string",
    "sales_contact_phone": "string",
    "sales_contact_email": "string",
    "management_contact_name": "string",
    "management_contact_phone": "string",
    "management_contact_email": "string",
    "other_contact_name": "string",
    "other_contact_phone": "string",
    "other_contact_email": "string"
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="upsertCustomerByID-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="upsertCustomerByID-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
customer|[Customer](#schemacustomer)|false|Customer
» id|string(uuid)|false|Auto generated customner id
» external_id|string|false|Customer external id. This field value can be _null_
» short_code|string|false|Customer's short code
» name|string|false|Organization name
» address_1|string|false|Address line 1
» address_2|string|false|Address line 2
» suite|string|false|Suite number
» city|string|false|City
» state|string|false|State / Province
» country|string|false|Country (2 letter ISO)
» postal|string|false|Postal / Zip code
» phone|string|false|Phone number
» phone_ext|string|false|Phone extension
» email|string|false|Email
» fax|string|false|Fax
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» default_billing_option|string|false|Billing Option
» default_dim_type|string|false|Dimension type
» default_order_notes|string|false|This notes will always show up as internal note everytime an order is created for this customer
» currency|string|false|Currency used when doing billing/invoicing
» is_active|boolean|false|Is customer active?
» credit_limit|number(float)|false|Credit limit for this customer
» credit_balance|number(float)|false|Credit balance for this customer
» dispatch__contact_name|string|false|Dispatch contact name
» dispatch_contact_phone|string|false|Dispatch contact phone
» dispatch_contact_email|string|false|Dispatch contact email
» billing_contact_name|string|false|Billing contact name
» billing_contact_phone|string|false|Billing contact phone
» billing_contact_email|string|false|Billing contact email
» sales_contact_name|string|false|Sales contact name
» sales_contact_phone|string|false|Sales contact phone
» sales_contact_email|string|false|Sales contact email
» management_contact_name|string|false|Management contact name
» management_contact_phone|string|false|Management contact phone
» management_contact_email|string|false|Management contact email
» other_contact_name|string|false|Other contact name
» other_contact_phone|string|false|Other contact phone
» other_contact_email|string|false|Other contact email



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: customers )
</aside>

# quote

Manage quotes

## createOrderSpotQuote

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/spot_quote \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/spot_quote HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/spot_quote',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "notes": "string",
  "est_delivery_start_at": "2018-09-19T05:22:07Z",
  "est_delivery_end_at": "2018-09-19T05:22:07Z",
  "freight_charge": 0,
  "original_freight_charge": 0,
  "fuel_charge": 0,
  "original_fuel_charge": 0,
  "accessorial_charges": [
    {
      "accessorial_id": "string",
      "charge": 0,
      "original_charge": 0
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/spot_quote',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/spot_quote',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/spot_quote', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/spot_quote");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /customers/{customerID}/orders/{orderID}/spot_quote`

*Create a spot quote for a customer's order*

> Body parameter

```json
{
  "notes": "string",
  "est_delivery_start_at": "2018-09-19T05:22:07Z",
  "est_delivery_end_at": "2018-09-19T05:22:07Z",
  "freight_charge": 0,
  "original_freight_charge": 0,
  "fuel_charge": 0,
  "original_fuel_charge": 0,
  "accessorial_charges": [
    {
      "accessorial_id": "string",
      "charge": 0,
      "original_charge": 0
    }
  ]
}
```
<h3 id="createOrderSpotQuote-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.
orderID|path|string(uuid)|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.
body|body|[SpotQuote](#schemaspotquote)|true|Order object
» notes|body|string|false|Notes
» est_delivery_start_at|body|string(date-time)|false|Estimated delivery time range (start). This field value can be _null_
» est_delivery_end_at|body|string(date-time)|false|Estimated delivery time range (end). This field value can be _null_
» freight_charge|body|number(float)|false|Freight charge
» original_freight_charge|body|number(float)|false|Orginal freight charge. This field value can be _null_
» fuel_charge|body|number(float)|false|Fuel charge
» original_fuel_charge|body|number(float)|false|Orginal fuel charge. This field value can be _null_
» accessorial_charges|body|[object]|false|Accessorials charges
»» accessorial_id|body|string(uuid)|false|Accessorial id
»» charge|body|number(float)|false|Accessorial charge
»» original_charge|body|number(float)|false|Orginal accessorial charge. This field value can be _null_


> Example responses

```json
{
  "quote": {
    "id": "string",
    "order_id": "string",
    "currency": "cad",
    "customer_service_id": "string",
    "is_expired": true,
    "pickup_start_at": "2018-09-19T05:22:07Z",
    "pickup_end_at": "2018-09-19T05:22:07Z",
    "est_delivery_start_at": "2018-09-19T05:22:07Z",
    "est_delivery_end_at": "2018-09-19T05:22:07Z",
    "notes": "string",
    "error_message": "string",
    "status": "quote-success",
    "charges": {
      "freight": 0,
      "fuel": 0,
      "accessorials": 0,
      "total": 0
    }
  }
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="createOrderSpotQuote-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="createOrderSpotQuote-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
quote|[Quote](#schemaquote)|false|Quote
» id|string(uuid)|false|Auto generated quote id
» order_id|string(uuid)|false|Order id this quote is associated to
» currency|string|false|Declared value currency
» customer_service_id|string(uuid)|false|Customer's service of this quote generated from
» is_expired|boolean|false|Is this quote has expired?
» pickup_start_at|string(date-time)|false|Pickup time range (start)
» pickup_end_at|string(date-time)|false|Pickup time range (end)
» est_delivery_start_at|string(date-time)|false|Estimated delivery time range (start). This field value can be _null_
» est_delivery_end_at|string(date-time)|false|Estimated delivery time range (end). This field value can be _null_
» notes|string|false|Notes
» error_message|string|false|Error message
» status|string|false|Status
» charges|object|false|No description
»» freight|number(float)|false|Freight charge
»» fuel|number(float)|false|Fuel charge
»» accessorials|number(float)|false|Accessorials charge
»» total|number(float)|false|Total charge
»» items|[object]|false|Quote items
»»» type|string(uuid)|false|Type
»»» quote_id|string(uuid)|false|Quote id this item is associated to
»»» description|string|false|Description
»»» quantity|integer|false|Unit quantity
»»» unit_price|integer|false|Unit price
»»» total|integer|false|Total



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: orders )
</aside>

## generateOrderQuotes

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/quotes \
  -H 'Accept: application/json'

```

```http
POST https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/quotes HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/quotes',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/quotes',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/quotes',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/quotes', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/quotes");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /customers/{customerID}/orders/{orderID}/quotes`

*Generate new quotes for a customer's order*

<h3 id="generateOrderQuotes-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.
orderID|path|string(uuid)|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.


> Example responses

```json
{
  "quotes": [
    {
      "id": "string",
      "order_id": "string",
      "currency": "cad",
      "customer_service_id": "string",
      "is_expired": true,
      "pickup_start_at": "2018-09-19T05:22:07Z",
      "pickup_end_at": "2018-09-19T05:22:07Z",
      "est_delivery_start_at": "2018-09-19T05:22:07Z",
      "est_delivery_end_at": "2018-09-19T05:22:07Z",
      "notes": "string",
      "error_message": "string",
      "status": "quote-success",
      "charges": {
        "freight": 0,
        "fuel": 0,
        "accessorials": 0,
        "total": 0
      }
    }
  ],
  "offset": 0,
  "limit": 0,
  "total": 0
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="generateOrderQuotes-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="generateOrderQuotes-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
offset|integer|false|No description
limit|integer|false|No description
total|integer|false|No description
quotes|[[Quote](#schemaquote)]|false|No description
» id|string(uuid)|false|Auto generated quote id
» order_id|string(uuid)|false|Order id this quote is associated to
» currency|string|false|Declared value currency
» customer_service_id|string(uuid)|false|Customer's service of this quote generated from
» is_expired|boolean|false|Is this quote has expired?
» pickup_start_at|string(date-time)|false|Pickup time range (start)
» pickup_end_at|string(date-time)|false|Pickup time range (end)
» est_delivery_start_at|string(date-time)|false|Estimated delivery time range (start). This field value can be _null_
» est_delivery_end_at|string(date-time)|false|Estimated delivery time range (end). This field value can be _null_
» notes|string|false|Notes
» error_message|string|false|Error message
» status|string|false|Status
» charges|object|false|No description
»» freight|number(float)|false|Freight charge
»» fuel|number(float)|false|Fuel charge
»» accessorials|number(float)|false|Accessorials charge
»» total|number(float)|false|Total charge
»» items|[object]|false|Quote items
»»» type|string(uuid)|false|Type
»»» quote_id|string(uuid)|false|Quote id this item is associated to
»»» description|string|false|Description
»»» quantity|integer|false|Unit quantity
»»» unit_price|integer|false|Unit price
»»» total|integer|false|Total



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: orders )
</aside>

## getOrderQuotes

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/quotes \
  -H 'Accept: application/json'

```

```http
GET https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/quotes HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/quotes',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/quotes',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/quotes',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/quotes', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/quotes");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /customers/{customerID}/orders/{orderID}/quotes`

*Get existing quotes for a customer's order*

<h3 id="getOrderQuotes-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.
orderID|path|string(uuid)|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.


> Example responses

```json
{
  "quotes": [
    {
      "id": "string",
      "order_id": "string",
      "currency": "cad",
      "customer_service_id": "string",
      "is_expired": true,
      "pickup_start_at": "2018-09-19T05:22:07Z",
      "pickup_end_at": "2018-09-19T05:22:07Z",
      "est_delivery_start_at": "2018-09-19T05:22:07Z",
      "est_delivery_end_at": "2018-09-19T05:22:07Z",
      "notes": "string",
      "error_message": "string",
      "status": "quote-success",
      "charges": {
        "freight": 0,
        "fuel": 0,
        "accessorials": 0,
        "total": 0
      }
    }
  ],
  "offset": 0,
  "limit": 0,
  "total": 0
}
```
```json
{
  "error_code": "string",
  "error_message": "string"
}
```
<h3 id="getOrderQuotes-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)

<h3 id="getOrderQuotes-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
offset|integer|false|No description
limit|integer|false|No description
total|integer|false|No description
quotes|[[Quote](#schemaquote)]|false|No description
» id|string(uuid)|false|Auto generated quote id
» order_id|string(uuid)|false|Order id this quote is associated to
» currency|string|false|Declared value currency
» customer_service_id|string(uuid)|false|Customer's service of this quote generated from
» is_expired|boolean|false|Is this quote has expired?
» pickup_start_at|string(date-time)|false|Pickup time range (start)
» pickup_end_at|string(date-time)|false|Pickup time range (end)
» est_delivery_start_at|string(date-time)|false|Estimated delivery time range (start). This field value can be _null_
» est_delivery_end_at|string(date-time)|false|Estimated delivery time range (end). This field value can be _null_
» notes|string|false|Notes
» error_message|string|false|Error message
» status|string|false|Status
» charges|object|false|No description
»» freight|number(float)|false|Freight charge
»» fuel|number(float)|false|Fuel charge
»» accessorials|number(float)|false|Accessorials charge
»» total|number(float)|false|Total charge
»» items|[object]|false|Quote items
»»» type|string(uuid)|false|Type
»»» quote_id|string(uuid)|false|Quote id this item is associated to
»»» description|string|false|Description
»»» quantity|integer|false|Unit quantity
»»» unit_price|integer|false|Unit price
»»» total|integer|false|Total



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: orders )
</aside>

# Schemas

## Order

<a name="schemaorder"></a>

```json
{
  "id": "string",
  "sequence_id": 0,
  "external_id": "string",
  "public_id": "string",
  "customer": {
    "id": "string",
    "external_id": "string",
    "short_code": "string"
  },
  "origin": {
    "address_book_id": "string",
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  },
  "destination": {
    "address_book_id": "string",
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  },
  "billing": {
    "address_book_id": "string",
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  },
  "status": "new",
  "billing_option": "prepaid",
  "notes": "string",
  "po_num": "string",
  "tender_num": "string",
  "ref_num": "string",
  "custom_broker": "string",
  "declared_value": 0,
  "declared_value_currency": "cad",
  "pickup_start_at": "2018-09-19T05:22:07Z",
  "pickup_end_at": "2018-09-19T05:22:07Z",
  "pickup_appt_start_at": "2018-09-19T05:22:07Z",
  "pickup_appt_end_at": "2018-09-19T05:22:07Z",
  "delivery_start_at": "2018-09-19T05:22:07Z",
  "delivery_end_at": "2018-09-19T05:22:07Z",
  "delivery_appt_start_at": "2018-09-19T05:22:07Z",
  "delivery_appt_end_at": "2018-09-19T05:22:07Z",
  "dim_type": "ltl",
  "commodities": [
    {
      "id": "string",
      "measurement_unit": "inch",
      "weight_unit": "lb",
      "freight_class": "string",
      "commodity_type": "skid",
      "commodity_type_other": "string",
      "description": "string",
      "feet": 0,
      "volume": 0,
      "length": 0,
      "width": 0,
      "height": 0,
      "weight": 0,
      "nmfc": "string",
      "is_stackable": true,
      "quantity": 0,
      "pieces": 0,
      "sku": "string"
    }
  ],
  "accessorials": [
    "string"
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
id|string(uuid)|false|Auto generated system ID
sequence_id|integer|false|Auto generated sequence ID per customer
external_id|string|false|External ID for mapping the order to an external system. This field value can be _null_
public_id|string|false|Auto generated human readable ID
customer|[OrderCustomer](#schemaordercustomer)|false|Customer
» id|string(uuid)|false|Auto generated customer id
» external_id|string|false|Customer external id. This field value can be _null_
» short_code|string|false|Customer's short code
origin|[OrderAddress](#schemaorderaddress)|true|Order address
» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
» org_name|string|false|Organization name
» contact_name|string|false|Contact name
» address_1|string|false|Address line 1
» address_2|string|false|Address line 2
» suite|string|false|Suite number
» city|string|false|City
» state|string|false|State / Province
» country|string|false|Country (2 letter ISO)
» postal|string|false|Postal / Zip code
» phone|string|false|Phone number
» phone_ext|string|false|Phone extension
» email|string|false|Email
» fax|string|false|Fax
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
destination|[OrderAddress](#schemaorderaddress)|true|Order address
» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
» org_name|string|false|Organization name
» contact_name|string|false|Contact name
» address_1|string|false|Address line 1
» address_2|string|false|Address line 2
» suite|string|false|Suite number
» city|string|false|City
» state|string|false|State / Province
» country|string|false|Country (2 letter ISO)
» postal|string|false|Postal / Zip code
» phone|string|false|Phone number
» phone_ext|string|false|Phone extension
» email|string|false|Email
» fax|string|false|Fax
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
billing|[OrderAddress](#schemaorderaddress)|true|Order address
» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
» org_name|string|false|Organization name
» contact_name|string|false|Contact name
» address_1|string|false|Address line 1
» address_2|string|false|Address line 2
» suite|string|false|Suite number
» city|string|false|City
» state|string|false|State / Province
» country|string|false|Country (2 letter ISO)
» postal|string|false|Postal / Zip code
» phone|string|false|Phone number
» phone_ext|string|false|Phone extension
» email|string|false|Email
» fax|string|false|Fax
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
status|string|false|Order Status
billing_option|string|false|Billing Option
notes|string|false|Notes that will appear on BOL
po_num|string|false|Purchase order numbers (if multiple use comma separated values)
tender_num|string|false|Tender number
ref_num|string|false|Reference number
custom_broker|string|false|Custom broker information
declared_value|number(float)|false|Declared value
declared_value_currency|string|false|Declared value currency
pickup_start_at|string(date-time)|false|Pickup time range (start)
pickup_end_at|string(date-time)|false|Pickup time range (end)
pickup_appt_start_at|string(date-time)|false|Pickup appointment time range (start). This field value can be _null_
pickup_appt_end_at|string(date-time)|false|Pickup appointment time range (end). This field value can be _null_
delivery_start_at|string(date-time)|false|Expected delivery time range (start). This field value can be _null_
delivery_end_at|string(date-time)|false|Expected delivery time range (end). This field value can be _null_
delivery_appt_start_at|string(date-time)|false|Delivery appointment time range (start). This field value can be _null_
delivery_appt_end_at|string(date-time)|false|Delivery appointment time range (end). This field value can be _null_
dim_type|string|false|Dimension type
commodities|[[Commodity](#schemacommodity)]|false|Commodities items
» id|string(uuid)|false|Auto generated commodity id
» measurement_unit|string|false|Measurement unit
» weight_unit|string|false|Weight unit
» freight_class|string|false|Freight class
» commodity_type|string|false|Commodity type
» commodity_type_other|string|false|If commodity type is set to _other_, then this field must have value
» description|string|false|Description of the commodity
» feet|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
» volume|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
» length|number(float)|false|Length of the commodity
» width|number(float)|false|Width of the commodity
» height|number(float)|false|Height of the commodity
» weight|number(float)|false|Weight of the commodity
» nmfc|string|false|NMFC number
» is_stackable|boolean|false|Is this commodity can be stacked?
» quantity|integer|false|Quantity of the commodity
» pieces|integer|false|Total number of pieces. This field value can be _null_
» sku|string|false|SKU number
accessorials|[string(uuid)]|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
status|new|
status|saved|
status|cancelled|
status|quoting|
status|quoted|
status|no-quote|
status|spot-quote-requested|
status|pending-dispatch|
status|dispatched|
status|in-transit|
status|delivered|
status|archived|
status|invoice-created|
status|invoice-sent|
status|invoice-paid|
status|claim|
status|draft-quick-quote|
status|quick-quoting|
status|quick-quoted|
status|no-quick-quote|
status|spot-qq-requested|
status|pickup-request|
status|rejected|
billing_option|prepaid|
billing_option|collect|
billing_option|thirdparty|
declared_value_currency|cad|
declared_value_currency|usd|
dim_type|ltl|
dim_type|ftl|
dim_type|volume|
» measurement_unit|inch|
» measurement_unit|cm|
» weight_unit|lb|
» weight_unit|kg|
» commodity_type|skid|
» commodity_type|other|


## OrderAddress

<a name="schemaorderaddress"></a>

```json
{
  "address_book_id": "string",
  "address_book_external_id": "string",
  "org_name": "string",
  "contact_name": "string",
  "address_1": "string",
  "address_2": "string",
  "suite": "string",
  "city": "string",
  "state": "string",
  "country": "string",
  "postal": "string",
  "phone": "string",
  "phone_ext": "string",
  "email": "string",
  "fax": "string",
  "latitude": 0,
  "longitude": 0,
  "bus_hours_start_at": "2018-09-19T05:22:07Z",
  "bus_hours_end_at": "2018-09-19T05:22:07Z"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
org_name|string|false|Organization name
contact_name|string|false|Contact name
address_1|string|false|Address line 1
address_2|string|false|Address line 2
suite|string|false|Suite number
city|string|false|City
state|string|false|State / Province
country|string|false|Country (2 letter ISO)
postal|string|false|Postal / Zip code
phone|string|false|Phone number
phone_ext|string|false|Phone extension
email|string|false|Email
fax|string|false|Fax
latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_



## OrderCustomer

<a name="schemaordercustomer"></a>

```json
{
  "id": "string",
  "external_id": "string",
  "short_code": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
id|string(uuid)|false|Auto generated customer id
external_id|string|false|Customer external id. This field value can be _null_
short_code|string|false|Customer's short code



## Commodity

<a name="schemacommodity"></a>

```json
{
  "id": "string",
  "measurement_unit": "inch",
  "weight_unit": "lb",
  "freight_class": "string",
  "commodity_type": "skid",
  "commodity_type_other": "string",
  "description": "string",
  "feet": 0,
  "volume": 0,
  "length": 0,
  "width": 0,
  "height": 0,
  "weight": 0,
  "nmfc": "string",
  "is_stackable": true,
  "quantity": 0,
  "pieces": 0,
  "sku": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
id|string(uuid)|false|Auto generated commodity id
measurement_unit|string|false|Measurement unit
weight_unit|string|false|Weight unit
freight_class|string|false|Freight class
commodity_type|string|false|Commodity type
commodity_type_other|string|false|If commodity type is set to _other_, then this field must have value
description|string|false|Description of the commodity
feet|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
volume|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
length|number(float)|false|Length of the commodity
width|number(float)|false|Width of the commodity
height|number(float)|false|Height of the commodity
weight|number(float)|false|Weight of the commodity
nmfc|string|false|NMFC number
is_stackable|boolean|false|Is this commodity can be stacked?
quantity|integer|false|Quantity of the commodity
pieces|integer|false|Total number of pieces. This field value can be _null_
sku|string|false|SKU number


#### Enumerated Values

|Property|Value|
|---|---|
measurement_unit|inch|
measurement_unit|cm|
weight_unit|lb|
weight_unit|kg|
commodity_type|skid|
commodity_type|other|


## Leg

<a name="schemaleg"></a>

```json
{
  "id": "string",
  "sequence_id": 0,
  "version": 0,
  "external_id": "string",
  "public_id": "string",
  "order_id": "string",
  "manifest_id": "string",
  "origin_stop_id": "string",
  "destination_stop_id": "string",
  "origin": {
    "terminal_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0
  },
  "destination": {
    "terminal_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0
  },
  "status": "available",
  "origin_start_at": "2018-09-19T05:22:07Z",
  "origin_end_at": "2018-09-19T05:22:07Z",
  "origin_appt_start_at": "2018-09-19T05:22:07Z",
  "origin_appt_end_at": "2018-09-19T05:22:07Z",
  "destination_start_at": "2018-09-19T05:22:07Z",
  "destination_end_at": "2018-09-19T05:22:07Z",
  "destination_appt_start_at": "2018-09-19T05:22:07Z",
  "destination_appt_end_at": "2018-09-19T05:22:07Z",
  "commodities": [
    {
      "id": "string",
      "measurement_unit": "inch",
      "weight_unit": "lb",
      "freight_class": "string",
      "commodity_type": "skid",
      "commodity_type_other": "string",
      "description": "string",
      "feet": 0,
      "volume": 0,
      "length": 0,
      "width": 0,
      "height": 0,
      "weight": 0,
      "nmfc": "string",
      "is_stackable": true,
      "quantity": 0,
      "pieces": 0,
      "sku": "string"
    }
  ],
  "accessorials": [
    "string"
  ],
  "history": {
    "origin_arrived_at": "2018-09-19T05:22:07Z",
    "origin_in_at": "2018-09-19T05:22:07Z",
    "origin_pickedup_at": "2018-09-19T05:22:07Z",
    "origin_out_at": "2018-09-19T05:22:07Z",
    "destination_arrived_at": "2018-09-19T05:22:07Z",
    "destination_in_at": "2018-09-19T05:22:07Z",
    "destination_delivered_at": "2018-09-19T05:22:07Z",
    "destination_out_at": "2018-09-19T05:22:07Z"
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
id|string(uuid)|false|Auto generated system ID
sequence_id|integer|false|Auto generated sequence ID per customer
version|integer|false|Auto generated version number (incremental)
external_id|string|false|External ID for mapping the leg to an external system. This field value can be _null_
public_id|string|false|Auto generated human readable ID
order_id|string|false|Related order ID
manifest_id|string|false|Related manifest ID (assigned). This field value can be _null_
origin_stop_id|string|false|Stop ID of the origin (only if this leg has been assigned to a manifest). This field value can be _null_
destination_stop_id|string|false|Stop ID of the destination (only if this leg has been assigned to a manifest). This field value can be _null_
origin|[LegAddress](#schemalegaddress)|false|Leg address
» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
» org_name|string|false|Organization name
» contact_name|string|false|Contact name
» address_1|string|false|Address line 1
» address_2|string|false|Address line 2
» suite|string|false|Suite number
» city|string|false|City
» state|string|false|State / Province
» country|string|false|Country (2 letter ISO)
» postal|string|false|Postal / Zip code
» phone|string|false|Phone number
» phone_ext|string|false|Phone extension
» email|string|false|Email
» fax|string|false|Fax
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
destination|[LegAddress](#schemalegaddress)|false|Leg address
» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
» org_name|string|false|Organization name
» contact_name|string|false|Contact name
» address_1|string|false|Address line 1
» address_2|string|false|Address line 2
» suite|string|false|Suite number
» city|string|false|City
» state|string|false|State / Province
» country|string|false|Country (2 letter ISO)
» postal|string|false|Postal / Zip code
» phone|string|false|Phone number
» phone_ext|string|false|Phone extension
» email|string|false|Email
» fax|string|false|Fax
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
status|string|false|Leg Status
origin_start_at|string(date-time)|false|Origin ready time range (start)
origin_end_at|string(date-time)|false|Origin ready time range (end)
origin_appt_start_at|string(date-time)|false|Origin appointment time range (start). This field value can be _null_
origin_appt_end_at|string(date-time)|false|Origin appointment time range (end). This field value can be _null_
destination_start_at|string(date-time)|false|Destination expected time range (start). This field value can be _null_
destination_end_at|string(date-time)|false|Destination expected time range (end). This field value can be _null_
destination_appt_start_at|string(date-time)|false|Destination appointment time range (start). This field value can be _null_
destination_appt_end_at|string(date-time)|false|Destination appointment time range (end). This field value can be _null_
history|[LegHistory](#schemaleghistory)|false|Historical timestamps of a leg
» origin_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at origin
» origin_in_at|string(date-time)|false|The timestamp of when the driver/partner in at origin
» origin_pickedup_at|string(date-time)|false|The timestamp of when the driver/partner picked up at origin
» origin_out_at|string(date-time)|false|The timestamp of when the driver/partner out at origin
» destination_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at destination
» destination_in_at|string(date-time)|false|The timestamp of when the driver/partner in at destination
» destination_delivered_at|string(date-time)|false|The timestamp of when the driver/partner delievered up at destination
» destination_out_at|string(date-time)|false|The timestamp of when the driver/partner out at destination
commodities|[[Commodity](#schemacommodity)]|false|Commodities items
» id|string(uuid)|false|Auto generated commodity id
» measurement_unit|string|false|Measurement unit
» weight_unit|string|false|Weight unit
» freight_class|string|false|Freight class
» commodity_type|string|false|Commodity type
» commodity_type_other|string|false|If commodity type is set to _other_, then this field must have value
» description|string|false|Description of the commodity
» feet|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
» volume|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
» length|number(float)|false|Length of the commodity
» width|number(float)|false|Width of the commodity
» height|number(float)|false|Height of the commodity
» weight|number(float)|false|Weight of the commodity
» nmfc|string|false|NMFC number
» is_stackable|boolean|false|Is this commodity can be stacked?
» quantity|integer|false|Quantity of the commodity
» pieces|integer|false|Total number of pieces. This field value can be _null_
» sku|string|false|SKU number
accessorials|[string(uuid)]|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
status|available|
status|pending|
status|dispatched|
status|arrived_origin|
status|in_origin|
status|loaded|
status|departed_origin|
status|arrived_destination|
status|in_destination|
status|unloaded|
status|departed_destination|
status|cancelled|
status|problem|
» measurement_unit|inch|
» measurement_unit|cm|
» weight_unit|lb|
» weight_unit|kg|
» commodity_type|skid|
» commodity_type|other|


## LegAddress

<a name="schemalegaddress"></a>

```json
{
  "terminal_id": "string",
  "org_name": "string",
  "contact_name": "string",
  "address_1": "string",
  "address_2": "string",
  "suite": "string",
  "city": "string",
  "state": "string",
  "country": "string",
  "postal": "string",
  "phone": "string",
  "phone_ext": "string",
  "email": "string",
  "fax": "string",
  "latitude": 0,
  "longitude": 0
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
org_name|string|false|Organization name
contact_name|string|false|Contact name
address_1|string|false|Address line 1
address_2|string|false|Address line 2
suite|string|false|Suite number
city|string|false|City
state|string|false|State / Province
country|string|false|Country (2 letter ISO)
postal|string|false|Postal / Zip code
phone|string|false|Phone number
phone_ext|string|false|Phone extension
email|string|false|Email
fax|string|false|Fax
latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
longitude|number(float)|false|Coordinate (longitude). This field value can be _null_



## LegHistory

<a name="schemaleghistory"></a>

```json
{
  "origin_arrived_at": "2018-09-19T05:22:07Z",
  "origin_in_at": "2018-09-19T05:22:07Z",
  "origin_pickedup_at": "2018-09-19T05:22:07Z",
  "origin_out_at": "2018-09-19T05:22:07Z",
  "destination_arrived_at": "2018-09-19T05:22:07Z",
  "destination_in_at": "2018-09-19T05:22:07Z",
  "destination_delivered_at": "2018-09-19T05:22:07Z",
  "destination_out_at": "2018-09-19T05:22:07Z"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
origin_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at origin
origin_in_at|string(date-time)|false|The timestamp of when the driver/partner in at origin
origin_pickedup_at|string(date-time)|false|The timestamp of when the driver/partner picked up at origin
origin_out_at|string(date-time)|false|The timestamp of when the driver/partner out at origin
destination_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at destination
destination_in_at|string(date-time)|false|The timestamp of when the driver/partner in at destination
destination_delivered_at|string(date-time)|false|The timestamp of when the driver/partner delievered up at destination
destination_out_at|string(date-time)|false|The timestamp of when the driver/partner out at destination



## Stop

<a name="schemastop"></a>

```json
{
  "id": "string",
  "manifest_id": "string",
  "ordinal": 0,
  "type": "stop",
  "schedule_start_at": "2018-09-19T05:22:07Z",
  "schedule_end_at": "2018-09-19T05:22:07Z",
  "org_name": "string",
  "contact_name": "string",
  "address_1": "string",
  "address_2": "string",
  "suite": "string",
  "city": "string",
  "state": "string",
  "country": "string",
  "postal": "string",
  "phone": "string",
  "phone_ext": "string",
  "email": "string",
  "fax": "string",
  "latitude": 0,
  "longitude": 0
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
id|string(uuid)|false|Auto generated system ID
manifest_id|string|false|Related Manifest ID
ordinal|integer|false|Ordinal of the stop in the manifest
type|string|false|Stop Type
schedule_start_at|string(date-time)|false|Scheduled time range (start)
schedule_end_at|string(date-time)|false|Scheduled time range (end)
org_name|string|false|Organization name
contact_name|string|false|Contact name
address_1|string|false|Address line 1
address_2|string|false|Address line 2
suite|string|false|Suite number
city|string|false|City
state|string|false|State / Province
country|string|false|Country (2 letter ISO)
postal|string|false|Postal / Zip code
phone|string|false|Phone number
phone_ext|string|false|Phone extension
email|string|false|Email
fax|string|false|Fax
latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
longitude|number(float)|false|Coordinate (longitude). This field value can be _null_


#### Enumerated Values

|Property|Value|
|---|---|
type|stop|
type|start|
type|end|
type|terminal|


## Customer

<a name="schemacustomer"></a>

```json
{
  "id": "string",
  "external_id": "string",
  "short_code": "string",
  "name": "string",
  "address_1": "string",
  "address_2": "string",
  "suite": "string",
  "city": "string",
  "state": "string",
  "country": "string",
  "postal": "string",
  "phone": "string",
  "phone_ext": "string",
  "email": "string",
  "fax": "string",
  "latitude": 0,
  "longitude": 0,
  "default_billing_option": "prepaid",
  "default_dim_type": "ltl",
  "default_order_notes": "string",
  "currency": "cad",
  "is_active": false,
  "credit_limit": 0,
  "credit_balance": 0,
  "dispatch__contact_name": "string",
  "dispatch_contact_phone": "string",
  "dispatch_contact_email": "string",
  "billing_contact_name": "string",
  "billing_contact_phone": "string",
  "billing_contact_email": "string",
  "sales_contact_name": "string",
  "sales_contact_phone": "string",
  "sales_contact_email": "string",
  "management_contact_name": "string",
  "management_contact_phone": "string",
  "management_contact_email": "string",
  "other_contact_name": "string",
  "other_contact_phone": "string",
  "other_contact_email": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
id|string(uuid)|false|Auto generated customner id
external_id|string|false|Customer external id. This field value can be _null_
short_code|string|false|Customer's short code
name|string|false|Organization name
address_1|string|false|Address line 1
address_2|string|false|Address line 2
suite|string|false|Suite number
city|string|false|City
state|string|false|State / Province
country|string|false|Country (2 letter ISO)
postal|string|false|Postal / Zip code
phone|string|false|Phone number
phone_ext|string|false|Phone extension
email|string|false|Email
fax|string|false|Fax
latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
default_billing_option|string|false|Billing Option
default_dim_type|string|false|Dimension type
default_order_notes|string|false|This notes will always show up as internal note everytime an order is created for this customer
currency|string|false|Currency used when doing billing/invoicing
is_active|boolean|false|Is customer active?
credit_limit|number(float)|false|Credit limit for this customer
credit_balance|number(float)|false|Credit balance for this customer
dispatch__contact_name|string|false|Dispatch contact name
dispatch_contact_phone|string|false|Dispatch contact phone
dispatch_contact_email|string|false|Dispatch contact email
billing_contact_name|string|false|Billing contact name
billing_contact_phone|string|false|Billing contact phone
billing_contact_email|string|false|Billing contact email
sales_contact_name|string|false|Sales contact name
sales_contact_phone|string|false|Sales contact phone
sales_contact_email|string|false|Sales contact email
management_contact_name|string|false|Management contact name
management_contact_phone|string|false|Management contact phone
management_contact_email|string|false|Management contact email
other_contact_name|string|false|Other contact name
other_contact_phone|string|false|Other contact phone
other_contact_email|string|false|Other contact email


#### Enumerated Values

|Property|Value|
|---|---|
default_billing_option|prepaid|
default_billing_option|collect|
default_billing_option|thirdparty|
default_dim_type|ltl|
default_dim_type|ftl|
default_dim_type|volume|
currency|cad|
currency|usd|


## SpotQuote

<a name="schemaspotquote"></a>

```json
{
  "notes": "string",
  "est_delivery_start_at": "2018-09-19T05:22:07Z",
  "est_delivery_end_at": "2018-09-19T05:22:07Z",
  "freight_charge": 0,
  "original_freight_charge": 0,
  "fuel_charge": 0,
  "original_fuel_charge": 0,
  "accessorial_charges": [
    {
      "accessorial_id": "string",
      "charge": 0,
      "original_charge": 0
    }
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
notes|string|false|Notes
est_delivery_start_at|string(date-time)|false|Estimated delivery time range (start). This field value can be _null_
est_delivery_end_at|string(date-time)|false|Estimated delivery time range (end). This field value can be _null_
freight_charge|number(float)|false|Freight charge
original_freight_charge|number(float)|false|Orginal freight charge. This field value can be _null_
fuel_charge|number(float)|false|Fuel charge
original_fuel_charge|number(float)|false|Orginal fuel charge. This field value can be _null_
accessorial_charges|[object]|false|Accessorials charges
» accessorial_id|string(uuid)|false|Accessorial id
» charge|number(float)|false|Accessorial charge
» original_charge|number(float)|false|Orginal accessorial charge. This field value can be _null_



## Quote

<a name="schemaquote"></a>

```json
{
  "id": "string",
  "order_id": "string",
  "currency": "cad",
  "customer_service_id": "string",
  "is_expired": true,
  "pickup_start_at": "2018-09-19T05:22:07Z",
  "pickup_end_at": "2018-09-19T05:22:07Z",
  "est_delivery_start_at": "2018-09-19T05:22:07Z",
  "est_delivery_end_at": "2018-09-19T05:22:07Z",
  "notes": "string",
  "error_message": "string",
  "status": "quote-success",
  "charges": {
    "freight": 0,
    "fuel": 0,
    "accessorials": 0,
    "total": 0
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
id|string(uuid)|false|Auto generated quote id
order_id|string(uuid)|false|Order id this quote is associated to
currency|string|false|Declared value currency
customer_service_id|string(uuid)|false|Customer's service of this quote generated from
is_expired|boolean|false|Is this quote has expired?
pickup_start_at|string(date-time)|false|Pickup time range (start)
pickup_end_at|string(date-time)|false|Pickup time range (end)
est_delivery_start_at|string(date-time)|false|Estimated delivery time range (start). This field value can be _null_
est_delivery_end_at|string(date-time)|false|Estimated delivery time range (end). This field value can be _null_
notes|string|false|Notes
error_message|string|false|Error message
status|string|false|Status
charges|object|false|No description
» freight|number(float)|false|Freight charge
» fuel|number(float)|false|Fuel charge
» accessorials|number(float)|false|Accessorials charge
» total|number(float)|false|Total charge
» items|[object]|false|Quote items
»» type|string(uuid)|false|Type
»» quote_id|string(uuid)|false|Quote id this item is associated to
»» description|string|false|Description
»» quantity|integer|false|Unit quantity
»» unit_price|integer|false|Unit price
»» total|integer|false|Total


#### Enumerated Values

|Property|Value|
|---|---|
currency|cad|
currency|usd|
status|quote-success|
status|quote-pending|
status|quote-rejected|
status|quote-error|
status|dispatch-success|
status|dispatch-pending|
status|dispatch-rejected|
status|dispatch-error|
»» type|freight|
»» type|freight-cwt|
»» type|freight-cwt-min|
»» type|freight-spot|
»» type|freight-pallets|
»» type|freight-pallets-min|
»» type|accessorial|
»» type|fuel|
»» type|misc|


## ApiError

<a name="schemaapierror"></a>

```json
{
  "error_code": "string",
  "error_message": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
error_code|string|false|Error code
error_message|string|false|Error message



## Manifest

<a name="schemamanifest"></a>

```json
{
  "id": "string",
  "nickname": "string",
  "org_id": "string",
  "vehicle_id": "string",
  "dispathcer_user_id": "string",
  "driver_user_id": "string",
  "trailer_id": "string",
  "partner_carrier_id": "string",
  "partner_carrier_service_id": "string",
  "sequential_id": "string",
  "full_id": "string",
  "scheduled_at": "2018-09-19T05:22:07Z",
  "status": "planning",
  "dispatched_at": "2018-09-19T05:22:07Z",
  "completed_at": "2018-09-19T05:22:07Z"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
id|string(uuid)|false|Id of the manifest
nickname|string|false|The nickname for the manifest
org_id|string(uuid)|false|Id of the organization to which the manifest belongs
vehicle_id|string(uuid)|false|Id of the vehicle corresponding to the manifest
dispathcer_user_id|string(uuid)|false|Id of the dispatcher of the manifest
driver_user_id|string(uuid)|false|Id of the driver corresponding to the manifest
trailer_id|string(uuid)|false|Id of the trailer corresponding to the manifest
partner_carrier_id|string(uuid)|false|Id of the partner/carrier that corresponds to the manifest
partner_carrier_service_id|string(uuid)|false|Id of the partner/carrier service that corresponds to the manifest
sequential_id|string(uuid)|false|The manifest's sequential id
full_id|string(uuid)|false|The full id of the string
scheduled_at|string(date-time)|false|The time at which the manifest was scheduled
status|string|false|The status of the manifest
dispatched_at|string(date-time)|false|The time at which the manifest was dispatched
completed_at|string(date-time)|false|The time at which the manifest was completed


#### Enumerated Values

|Property|Value|
|---|---|
status|planning|
status|planned|
status|cancelled|
status|assigned|
status|accepted|
status|rejected|
status|problem|
status|completed|
status|bill-created|
status|bill-sent|
status|bill-paid|


## ManifestEvent

<a name="schemamanifestevent"></a>

```json
{
  "id": "string",
  "created_at": "2018-09-19T05:22:07Z",
  "updated_at": "2018-09-19T05:22:07Z",
  "user_id": "2018-09-19T05:22:07Z",
  "manifest_id": "string",
  "data": {
    "author": "string",
    "text": "string",
    "type": "notes"
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
id|string(uuid)|false|The id of the manifest event
created_at|string(date-time)|false|The time of the event's creation
updated_at|string(date-time)|false|The time the event was last updated
user_id|string(date-time)|false|The id of the user who created the event
manifest_id|string(uuid)|false|The id of the manifest for which the event belongs
data|object|false|No description
» author|string|false|The name of the user who authored the event
» text|string|false|The contents of the message
» type|string|false|The type of manifest message


#### Enumerated Values

|Property|Value|
|---|---|
» type|notes|


## BulkOrderCreateResponse

<a name="schemabulkordercreateresponse"></a>

```json
{
  "job_id": "string",
  "message": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
job_id|string(uuid)|false|The id of the bulk create job
message|string|false|Information about the status of the bulk job.



## BulkOrderEmailResults

<a name="schemabulkorderemailresults"></a>

```json
{
  "results": [
    {
      "order": {
        "id": "string",
        "sequence_id": 0,
        "external_id": "string",
        "public_id": "string",
        "customer": {
          "id": "string",
          "external_id": "string",
          "short_code": "string"
        },
        "origin": {
          "address_book_id": "string",
          "address_book_external_id": "string",
          "org_name": "string",
          "contact_name": "string",
          "address_1": "string",
          "address_2": "string",
          "suite": "string",
          "city": "string",
          "state": "string",
          "country": "string",
          "postal": "string",
          "phone": "string",
          "phone_ext": "string",
          "email": "string",
          "fax": "string",
          "latitude": 0,
          "longitude": 0,
          "bus_hours_start_at": "2018-09-19T05:22:07Z",
          "bus_hours_end_at": "2018-09-19T05:22:07Z"
        },
        "destination": {
          "address_book_id": "string",
          "address_book_external_id": "string",
          "org_name": "string",
          "contact_name": "string",
          "address_1": "string",
          "address_2": "string",
          "suite": "string",
          "city": "string",
          "state": "string",
          "country": "string",
          "postal": "string",
          "phone": "string",
          "phone_ext": "string",
          "email": "string",
          "fax": "string",
          "latitude": 0,
          "longitude": 0,
          "bus_hours_start_at": "2018-09-19T05:22:07Z",
          "bus_hours_end_at": "2018-09-19T05:22:07Z"
        },
        "billing": {
          "address_book_id": "string",
          "address_book_external_id": "string",
          "org_name": "string",
          "contact_name": "string",
          "address_1": "string",
          "address_2": "string",
          "suite": "string",
          "city": "string",
          "state": "string",
          "country": "string",
          "postal": "string",
          "phone": "string",
          "phone_ext": "string",
          "email": "string",
          "fax": "string",
          "latitude": 0,
          "longitude": 0,
          "bus_hours_start_at": "2018-09-19T05:22:07Z",
          "bus_hours_end_at": "2018-09-19T05:22:07Z"
        },
        "status": "new",
        "billing_option": "prepaid",
        "notes": "string",
        "po_num": "string",
        "tender_num": "string",
        "ref_num": "string",
        "custom_broker": "string",
        "declared_value": 0,
        "declared_value_currency": "cad",
        "pickup_start_at": "2018-09-19T05:22:07Z",
        "pickup_end_at": "2018-09-19T05:22:07Z",
        "pickup_appt_start_at": "2018-09-19T05:22:07Z",
        "pickup_appt_end_at": "2018-09-19T05:22:07Z",
        "delivery_start_at": "2018-09-19T05:22:07Z",
        "delivery_end_at": "2018-09-19T05:22:07Z",
        "delivery_appt_start_at": "2018-09-19T05:22:07Z",
        "delivery_appt_end_at": "2018-09-19T05:22:07Z",
        "dim_type": "ltl",
        "commodities": [
          {
            "id": "string",
            "measurement_unit": "inch",
            "weight_unit": "lb",
            "freight_class": "string",
            "commodity_type": "skid",
            "commodity_type_other": "string",
            "description": "string",
            "feet": 0,
            "volume": 0,
            "length": 0,
            "width": 0,
            "height": 0,
            "weight": 0,
            "nmfc": "string",
            "is_stackable": true,
            "quantity": 0,
            "pieces": 0,
            "sku": "string"
          }
        ],
        "accessorials": [
          "string"
        ]
      },
      "status": "Imported"
    }
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
results|[object]|false|The results of the bulk create job.
» order|[Order](#schemaorder)|false|Customer's order
»» id|string(uuid)|false|Auto generated system ID
»» sequence_id|integer|false|Auto generated sequence ID per customer
»» external_id|string|false|External ID for mapping the order to an external system. This field value can be _null_
»» public_id|string|false|Auto generated human readable ID
»» customer|[OrderCustomer](#schemaordercustomer)|false|Customer
»»» id|string(uuid)|false|Auto generated customer id
»»» external_id|string|false|Customer external id. This field value can be _null_
»»» short_code|string|false|Customer's short code
»» origin|[OrderAddress](#schemaorderaddress)|true|Order address
»»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»»» org_name|string|false|Organization name
»»» contact_name|string|false|Contact name
»»» address_1|string|false|Address line 1
»»» address_2|string|false|Address line 2
»»» suite|string|false|Suite number
»»» city|string|false|City
»»» state|string|false|State / Province
»»» country|string|false|Country (2 letter ISO)
»»» postal|string|false|Postal / Zip code
»»» phone|string|false|Phone number
»»» phone_ext|string|false|Phone extension
»»» email|string|false|Email
»»» fax|string|false|Fax
»»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
»» destination|[OrderAddress](#schemaorderaddress)|true|Order address
»»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»»» org_name|string|false|Organization name
»»» contact_name|string|false|Contact name
»»» address_1|string|false|Address line 1
»»» address_2|string|false|Address line 2
»»» suite|string|false|Suite number
»»» city|string|false|City
»»» state|string|false|State / Province
»»» country|string|false|Country (2 letter ISO)
»»» postal|string|false|Postal / Zip code
»»» phone|string|false|Phone number
»»» phone_ext|string|false|Phone extension
»»» email|string|false|Email
»»» fax|string|false|Fax
»»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
»» billing|[OrderAddress](#schemaorderaddress)|true|Order address
»»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»»» org_name|string|false|Organization name
»»» contact_name|string|false|Contact name
»»» address_1|string|false|Address line 1
»»» address_2|string|false|Address line 2
»»» suite|string|false|Suite number
»»» city|string|false|City
»»» state|string|false|State / Province
»»» country|string|false|Country (2 letter ISO)
»»» postal|string|false|Postal / Zip code
»»» phone|string|false|Phone number
»»» phone_ext|string|false|Phone extension
»»» email|string|false|Email
»»» fax|string|false|Fax
»»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
»» status|string|false|Order Status
»» billing_option|string|false|Billing Option
»» notes|string|false|Notes that will appear on BOL
»» po_num|string|false|Purchase order numbers (if multiple use comma separated values)
»» tender_num|string|false|Tender number
»» ref_num|string|false|Reference number
»» custom_broker|string|false|Custom broker information
»» declared_value|number(float)|false|Declared value
»» declared_value_currency|string|false|Declared value currency
»» pickup_start_at|string(date-time)|false|Pickup time range (start)
»» pickup_end_at|string(date-time)|false|Pickup time range (end)
»» pickup_appt_start_at|string(date-time)|false|Pickup appointment time range (start). This field value can be _null_
»» pickup_appt_end_at|string(date-time)|false|Pickup appointment time range (end). This field value can be _null_
»» delivery_start_at|string(date-time)|false|Expected delivery time range (start). This field value can be _null_
»» delivery_end_at|string(date-time)|false|Expected delivery time range (end). This field value can be _null_
»» delivery_appt_start_at|string(date-time)|false|Delivery appointment time range (start). This field value can be _null_
»» delivery_appt_end_at|string(date-time)|false|Delivery appointment time range (end). This field value can be _null_
»» dim_type|string|false|Dimension type
»» commodities|[[Commodity](#schemacommodity)]|false|Commodities items
»»» id|string(uuid)|false|Auto generated commodity id
»»» measurement_unit|string|false|Measurement unit
»»» weight_unit|string|false|Weight unit
»»» freight_class|string|false|Freight class
»»» commodity_type|string|false|Commodity type
»»» commodity_type_other|string|false|If commodity type is set to _other_, then this field must have value
»»» description|string|false|Description of the commodity
»»» feet|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»»» volume|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»»» length|number(float)|false|Length of the commodity
»»» width|number(float)|false|Width of the commodity
»»» height|number(float)|false|Height of the commodity
»»» weight|number(float)|false|Weight of the commodity
»»» nmfc|string|false|NMFC number
»»» is_stackable|boolean|false|Is this commodity can be stacked?
»»» quantity|integer|false|Quantity of the commodity
»»» pieces|integer|false|Total number of pieces. This field value can be _null_
»»» sku|string|false|SKU number
»» accessorials|[string(uuid)]|false|No description
» status|string|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
»» status|new|
»» status|saved|
»» status|cancelled|
»» status|quoting|
»» status|quoted|
»» status|no-quote|
»» status|spot-quote-requested|
»» status|pending-dispatch|
»» status|dispatched|
»» status|in-transit|
»» status|delivered|
»» status|archived|
»» status|invoice-created|
»» status|invoice-sent|
»» status|invoice-paid|
»» status|claim|
»» status|draft-quick-quote|
»» status|quick-quoting|
»» status|quick-quoted|
»» status|no-quick-quote|
»» status|spot-qq-requested|
»» status|pickup-request|
»» status|rejected|
»» billing_option|prepaid|
»» billing_option|collect|
»» billing_option|thirdparty|
»» declared_value_currency|cad|
»» declared_value_currency|usd|
»» dim_type|ltl|
»» dim_type|ftl|
»» dim_type|volume|
»»» measurement_unit|inch|
»»» measurement_unit|cm|
»»» weight_unit|lb|
»»» weight_unit|kg|
»»» commodity_type|skid|
»»» commodity_type|other|
» status|Imported|
» status|Failed|


## LegFileRequest

<a name="schemalegfilerequest"></a>

```json
{
  "type": "other",
  "url": "string",
  "description": "string",
  "latitude": 0,
  "longitude": 0,
  "metadata": {}
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
type|string|false|The type of leg file
url|string|false|The url location for the leg file
description|string|false|A description of the leg file
latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
metadata|object|false|Metadata object for the leg file


#### Enumerated Values

|Property|Value|
|---|---|
type|other|
type|comm-invoice|
type|pod|
type|pop|
type|pod-sig|
type|pop-sig|
type|carrier-invoice|
type|smc|
type|bol|


## LegFile

<a name="schemalegfile"></a>

```json
{
  "id": "string",
  "created_at": "2018-09-19T05:22:07Z",
  "updated_at": "2018-09-19T05:22:07Z",
  "org_id": "string",
  "leg_id": "string",
  "uploaded_by": "string",
  "uploaded_at": "string",
  "type": "other",
  "url": "string",
  "description": "string",
  "latitude": 0,
  "longitude": 0,
  "metadata": {},
  "task_id": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
id|string(uuid)|false|The uuid for the leg file
created_at|string(date-time)|false|The timestamp for the creation of the leg file
updated_at|string(date-time)|false|The timestamp for the last update of the leg file
org_id|string(uuid)|false|The uuid for the organization of the leg file
leg_id|string(uuid)|false|The uuid of the leg corresponding to the leg file
uploaded_by|string(uuid)|false|The uuid of the user who uploaded the leg file
uploaded_at|string(uuid)|false|The uuid
type|string|false|The type of leg file
url|string|false|The url location for the leg file
description|string|false|A description of the leg file
latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
metadata|object|false|Metadata object for the leg file
task_id|string(uuid)|false|The task id of the leg that corresponds to the leg file


#### Enumerated Values

|Property|Value|
|---|---|
type|other|
type|comm-invoice|
type|pod|
type|pop|
type|pod-sig|
type|pop-sig|
type|carrier-invoice|
type|smc|
type|bol|


## OrderFileRequest

<a name="schemaorderfilerequest"></a>

```json
{
  "type": "other",
  "url": "string",
  "description": "string",
  "latitude": 0,
  "longitude": 0,
  "metadata": {}
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
type|string|false|The type of order file
url|string|false|The url location for the order file
description|string|false|A description of the order file
latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
metadata|object|false|Metadata object for the order file


#### Enumerated Values

|Property|Value|
|---|---|
type|other|
type|comm-invoice|
type|pod|
type|pop|
type|pod-sig|
type|pop-sig|
type|carrier-invoice|
type|smc|
type|bol|


## OrderFile

<a name="schemaorderfile"></a>

```json
{
  "id": "string",
  "created_at": "2018-09-19T05:22:07Z",
  "updated_at": "2018-09-19T05:22:07Z",
  "org_id": "string",
  "leg_id": "string",
  "uploaded_by": "string",
  "uploaded_at": "string",
  "type": "other",
  "url": "string",
  "description": "string",
  "latitude": 0,
  "longitude": 0,
  "metadata": {}
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
id|string(uuid)|false|The uuid for the order file
created_at|string(date-time)|false|The timestamp for the creation of the order file
updated_at|string(date-time)|false|The timestamp for the last update of the order file
org_id|string(uuid)|false|The uuid for the organization of the order file
leg_id|string(uuid)|false|The uuid of the order corresponding to the order file
uploaded_by|string(uuid)|false|The uuid of the user who uploaded the order file
uploaded_at|string(uuid)|false|The uuid
type|string|false|The type of order file
url|string|false|The url location for the order file
description|string|false|A description of the order file
latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
metadata|object|false|Metadata object for the order file


#### Enumerated Values

|Property|Value|
|---|---|
type|other|
type|comm-invoice|
type|pod|
type|pop|
type|pod-sig|
type|pop-sig|
type|carrier-invoice|
type|smc|
type|bol|


## OrderAndLegsResponse

<a name="schemaorderandlegsresponse"></a>

```json
{
  "order": {
    "id": "string",
    "sequence_id": 0,
    "external_id": "string",
    "public_id": "string",
    "customer": {
      "id": "string",
      "external_id": "string",
      "short_code": "string"
    },
    "origin": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "destination": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "billing": {
      "address_book_id": "string",
      "address_book_external_id": "string",
      "org_name": "string",
      "contact_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "state": "string",
      "country": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "email": "string",
      "fax": "string",
      "latitude": 0,
      "longitude": 0,
      "bus_hours_start_at": "2018-09-19T05:22:07Z",
      "bus_hours_end_at": "2018-09-19T05:22:07Z"
    },
    "status": "new",
    "billing_option": "prepaid",
    "notes": "string",
    "po_num": "string",
    "tender_num": "string",
    "ref_num": "string",
    "custom_broker": "string",
    "declared_value": 0,
    "declared_value_currency": "cad",
    "pickup_start_at": "2018-09-19T05:22:07Z",
    "pickup_end_at": "2018-09-19T05:22:07Z",
    "pickup_appt_start_at": "2018-09-19T05:22:07Z",
    "pickup_appt_end_at": "2018-09-19T05:22:07Z",
    "delivery_start_at": "2018-09-19T05:22:07Z",
    "delivery_end_at": "2018-09-19T05:22:07Z",
    "delivery_appt_start_at": "2018-09-19T05:22:07Z",
    "delivery_appt_end_at": "2018-09-19T05:22:07Z",
    "dim_type": "ltl",
    "commodities": [
      {
        "id": "string",
        "measurement_unit": "inch",
        "weight_unit": "lb",
        "freight_class": "string",
        "commodity_type": "skid",
        "commodity_type_other": "string",
        "description": "string",
        "feet": 0,
        "volume": 0,
        "length": 0,
        "width": 0,
        "height": 0,
        "weight": 0,
        "nmfc": "string",
        "is_stackable": true,
        "quantity": 0,
        "pieces": 0,
        "sku": "string"
      }
    ],
    "accessorials": [
      "string"
    ]
  },
  "legs": [
    {
      "id": "string",
      "sequence_id": 0,
      "version": 0,
      "external_id": "string",
      "public_id": "string",
      "order_id": "string",
      "manifest_id": "string",
      "origin_stop_id": "string",
      "destination_stop_id": "string",
      "origin": {
        "terminal_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0
      },
      "destination": {
        "terminal_id": "string",
        "org_name": "string",
        "contact_name": "string",
        "address_1": "string",
        "address_2": "string",
        "suite": "string",
        "city": "string",
        "state": "string",
        "country": "string",
        "postal": "string",
        "phone": "string",
        "phone_ext": "string",
        "email": "string",
        "fax": "string",
        "latitude": 0,
        "longitude": 0
      },
      "status": "available",
      "origin_start_at": "2018-09-19T05:22:07Z",
      "origin_end_at": "2018-09-19T05:22:07Z",
      "origin_appt_start_at": "2018-09-19T05:22:07Z",
      "origin_appt_end_at": "2018-09-19T05:22:07Z",
      "destination_start_at": "2018-09-19T05:22:07Z",
      "destination_end_at": "2018-09-19T05:22:07Z",
      "destination_appt_start_at": "2018-09-19T05:22:07Z",
      "destination_appt_end_at": "2018-09-19T05:22:07Z",
      "commodities": [
        {
          "id": "string",
          "measurement_unit": "inch",
          "weight_unit": "lb",
          "freight_class": "string",
          "commodity_type": "skid",
          "commodity_type_other": "string",
          "description": "string",
          "feet": 0,
          "volume": 0,
          "length": 0,
          "width": 0,
          "height": 0,
          "weight": 0,
          "nmfc": "string",
          "is_stackable": true,
          "quantity": 0,
          "pieces": 0,
          "sku": "string"
        }
      ],
      "accessorials": [
        "string"
      ],
      "history": {
        "origin_arrived_at": "2018-09-19T05:22:07Z",
        "origin_in_at": "2018-09-19T05:22:07Z",
        "origin_pickedup_at": "2018-09-19T05:22:07Z",
        "origin_out_at": "2018-09-19T05:22:07Z",
        "destination_arrived_at": "2018-09-19T05:22:07Z",
        "destination_in_at": "2018-09-19T05:22:07Z",
        "destination_delivered_at": "2018-09-19T05:22:07Z",
        "destination_out_at": "2018-09-19T05:22:07Z"
      }
    }
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
order|[Order](#schemaorder)|false|Customer's order
» id|string(uuid)|false|Auto generated system ID
» sequence_id|integer|false|Auto generated sequence ID per customer
» external_id|string|false|External ID for mapping the order to an external system. This field value can be _null_
» public_id|string|false|Auto generated human readable ID
» customer|[OrderCustomer](#schemaordercustomer)|false|Customer
»» id|string(uuid)|false|Auto generated customer id
»» external_id|string|false|Customer external id. This field value can be _null_
»» short_code|string|false|Customer's short code
» origin|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
» destination|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
» billing|[OrderAddress](#schemaorderaddress)|true|Order address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
»» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
»» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_
» status|string|false|Order Status
» billing_option|string|false|Billing Option
» notes|string|false|Notes that will appear on BOL
» po_num|string|false|Purchase order numbers (if multiple use comma separated values)
» tender_num|string|false|Tender number
» ref_num|string|false|Reference number
» custom_broker|string|false|Custom broker information
» declared_value|number(float)|false|Declared value
» declared_value_currency|string|false|Declared value currency
» pickup_start_at|string(date-time)|false|Pickup time range (start)
» pickup_end_at|string(date-time)|false|Pickup time range (end)
» pickup_appt_start_at|string(date-time)|false|Pickup appointment time range (start). This field value can be _null_
» pickup_appt_end_at|string(date-time)|false|Pickup appointment time range (end). This field value can be _null_
» delivery_start_at|string(date-time)|false|Expected delivery time range (start). This field value can be _null_
» delivery_end_at|string(date-time)|false|Expected delivery time range (end). This field value can be _null_
» delivery_appt_start_at|string(date-time)|false|Delivery appointment time range (start). This field value can be _null_
» delivery_appt_end_at|string(date-time)|false|Delivery appointment time range (end). This field value can be _null_
» dim_type|string|false|Dimension type
» commodities|[[Commodity](#schemacommodity)]|false|Commodities items
»» id|string(uuid)|false|Auto generated commodity id
»» measurement_unit|string|false|Measurement unit
»» weight_unit|string|false|Weight unit
»» freight_class|string|false|Freight class
»» commodity_type|string|false|Commodity type
»» commodity_type_other|string|false|If commodity type is set to _other_, then this field must have value
»» description|string|false|Description of the commodity
»» feet|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»» volume|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»» length|number(float)|false|Length of the commodity
»» width|number(float)|false|Width of the commodity
»» height|number(float)|false|Height of the commodity
»» weight|number(float)|false|Weight of the commodity
»» nmfc|string|false|NMFC number
»» is_stackable|boolean|false|Is this commodity can be stacked?
»» quantity|integer|false|Quantity of the commodity
»» pieces|integer|false|Total number of pieces. This field value can be _null_
»» sku|string|false|SKU number
» accessorials|[string(uuid)]|false|No description
legs|[[Leg](#schemaleg)]|false|No description
» id|string(uuid)|false|Auto generated system ID
» sequence_id|integer|false|Auto generated sequence ID per customer
» version|integer|false|Auto generated version number (incremental)
» external_id|string|false|External ID for mapping the leg to an external system. This field value can be _null_
» public_id|string|false|Auto generated human readable ID
» order_id|string|false|Related order ID
» manifest_id|string|false|Related manifest ID (assigned). This field value can be _null_
» origin_stop_id|string|false|Stop ID of the origin (only if this leg has been assigned to a manifest). This field value can be _null_
» destination_stop_id|string|false|Stop ID of the destination (only if this leg has been assigned to a manifest). This field value can be _null_
» origin|[LegAddress](#schemalegaddress)|false|Leg address
»» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» destination|[LegAddress](#schemalegaddress)|false|Leg address
»» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
»» org_name|string|false|Organization name
»» contact_name|string|false|Contact name
»» address_1|string|false|Address line 1
»» address_2|string|false|Address line 2
»» suite|string|false|Suite number
»» city|string|false|City
»» state|string|false|State / Province
»» country|string|false|Country (2 letter ISO)
»» postal|string|false|Postal / Zip code
»» phone|string|false|Phone number
»» phone_ext|string|false|Phone extension
»» email|string|false|Email
»» fax|string|false|Fax
»» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
»» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» status|string|false|Leg Status
» origin_start_at|string(date-time)|false|Origin ready time range (start)
» origin_end_at|string(date-time)|false|Origin ready time range (end)
» origin_appt_start_at|string(date-time)|false|Origin appointment time range (start). This field value can be _null_
» origin_appt_end_at|string(date-time)|false|Origin appointment time range (end). This field value can be _null_
» destination_start_at|string(date-time)|false|Destination expected time range (start). This field value can be _null_
» destination_end_at|string(date-time)|false|Destination expected time range (end). This field value can be _null_
» destination_appt_start_at|string(date-time)|false|Destination appointment time range (start). This field value can be _null_
» destination_appt_end_at|string(date-time)|false|Destination appointment time range (end). This field value can be _null_
» history|[LegHistory](#schemaleghistory)|false|Historical timestamps of a leg
»» origin_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at origin
»» origin_in_at|string(date-time)|false|The timestamp of when the driver/partner in at origin
»» origin_pickedup_at|string(date-time)|false|The timestamp of when the driver/partner picked up at origin
»» origin_out_at|string(date-time)|false|The timestamp of when the driver/partner out at origin
»» destination_arrived_at|string(date-time)|false|The timestamp of when the driver/partner arrived at destination
»» destination_in_at|string(date-time)|false|The timestamp of when the driver/partner in at destination
»» destination_delivered_at|string(date-time)|false|The timestamp of when the driver/partner delievered up at destination
»» destination_out_at|string(date-time)|false|The timestamp of when the driver/partner out at destination
» commodities|[[Commodity](#schemacommodity)]|false|Commodities items
»» id|string(uuid)|false|Auto generated commodity id
»» measurement_unit|string|false|Measurement unit
»» weight_unit|string|false|Weight unit
»» freight_class|string|false|Freight class
»» commodity_type|string|false|Commodity type
»» commodity_type_other|string|false|If commodity type is set to _other_, then this field must have value
»» description|string|false|Description of the commodity
»» feet|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
»» volume|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
»» length|number(float)|false|Length of the commodity
»» width|number(float)|false|Width of the commodity
»» height|number(float)|false|Height of the commodity
»» weight|number(float)|false|Weight of the commodity
»» nmfc|string|false|NMFC number
»» is_stackable|boolean|false|Is this commodity can be stacked?
»» quantity|integer|false|Quantity of the commodity
»» pieces|integer|false|Total number of pieces. This field value can be _null_
»» sku|string|false|SKU number
» accessorials|[string(uuid)]|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
» status|new|
» status|saved|
» status|cancelled|
» status|quoting|
» status|quoted|
» status|no-quote|
» status|spot-quote-requested|
» status|pending-dispatch|
» status|dispatched|
» status|in-transit|
» status|delivered|
» status|archived|
» status|invoice-created|
» status|invoice-sent|
» status|invoice-paid|
» status|claim|
» status|draft-quick-quote|
» status|quick-quoting|
» status|quick-quoted|
» status|no-quick-quote|
» status|spot-qq-requested|
» status|pickup-request|
» status|rejected|
» billing_option|prepaid|
» billing_option|collect|
» billing_option|thirdparty|
» declared_value_currency|cad|
» declared_value_currency|usd|
» dim_type|ltl|
» dim_type|ftl|
» dim_type|volume|
»» measurement_unit|inch|
»» measurement_unit|cm|
»» weight_unit|lb|
»» weight_unit|kg|
»» commodity_type|skid|
»» commodity_type|other|
» status|available|
» status|pending|
» status|dispatched|
» status|arrived_origin|
» status|in_origin|
» status|loaded|
» status|departed_origin|
» status|arrived_destination|
» status|in_destination|
» status|unloaded|
» status|departed_destination|
» status|cancelled|
» status|problem|
»» measurement_unit|inch|
»» measurement_unit|cm|
»» weight_unit|lb|
»» weight_unit|kg|
»» commodity_type|skid|
»» commodity_type|other|


## OrderAddressReviseRequest

<a name="schemaorderaddressreviserequest"></a>

```json
{
  "address": {
    "address_book_id": "string",
    "address_book_external_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0,
    "bus_hours_start_at": "2018-09-19T05:22:07Z",
    "bus_hours_end_at": "2018-09-19T05:22:07Z"
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
address|[OrderAddress](#schemaorderaddress)|false|Order address
» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.
» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.
» org_name|string|false|Organization name
» contact_name|string|false|Contact name
» address_1|string|false|Address line 1
» address_2|string|false|Address line 2
» suite|string|false|Suite number
» city|string|false|City
» state|string|false|State / Province
» country|string|false|Country (2 letter ISO)
» postal|string|false|Postal / Zip code
» phone|string|false|Phone number
» phone_ext|string|false|Phone extension
» email|string|false|Email
» fax|string|false|Fax
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_
» bus_hours_start_at|string(date-time)|false|Business hours range (start). This field value can be _null_
» bus_hours_end_at|string(date-time)|false|Business hours range (end). This field value can be _null_



## CommodityReviseRequest

<a name="schemacommodityreviserequest"></a>

```json
{
  "commodities": [
    {
      "id": "string",
      "measurement_unit": "inch",
      "weight_unit": "lb",
      "freight_class": "string",
      "commodity_type": "skid",
      "commodity_type_other": "string",
      "description": "string",
      "feet": 0,
      "volume": 0,
      "length": 0,
      "width": 0,
      "height": 0,
      "weight": 0,
      "nmfc": "string",
      "is_stackable": true,
      "quantity": 0,
      "pieces": 0,
      "sku": "string"
    }
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
commodities|[[Commodity](#schemacommodity)]|false|No description
» id|string(uuid)|false|Auto generated commodity id
» measurement_unit|string|false|Measurement unit
» weight_unit|string|false|Weight unit
» freight_class|string|false|Freight class
» commodity_type|string|false|Commodity type
» commodity_type_other|string|false|If commodity type is set to _other_, then this field must have value
» description|string|false|Description of the commodity
» feet|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_
» volume|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_
» length|number(float)|false|Length of the commodity
» width|number(float)|false|Width of the commodity
» height|number(float)|false|Height of the commodity
» weight|number(float)|false|Weight of the commodity
» nmfc|string|false|NMFC number
» is_stackable|boolean|false|Is this commodity can be stacked?
» quantity|integer|false|Quantity of the commodity
» pieces|integer|false|Total number of pieces. This field value can be _null_
» sku|string|false|SKU number


#### Enumerated Values

|Property|Value|
|---|---|
» measurement_unit|inch|
» measurement_unit|cm|
» weight_unit|lb|
» weight_unit|kg|
» commodity_type|skid|
» commodity_type|other|


## LegAddressReviseRequest

<a name="schemalegaddressreviserequest"></a>

```json
{
  "address": {
    "terminal_id": "string",
    "org_name": "string",
    "contact_name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "email": "string",
    "fax": "string",
    "latitude": 0,
    "longitude": 0
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
address|[LegAddress](#schemalegaddress)|false|Leg address
» terminal_id|string(uuid)|false|Related terminal ID. This field value can be _null_
» org_name|string|false|Organization name
» contact_name|string|false|Contact name
» address_1|string|false|Address line 1
» address_2|string|false|Address line 2
» suite|string|false|Suite number
» city|string|false|City
» state|string|false|State / Province
» country|string|false|Country (2 letter ISO)
» postal|string|false|Postal / Zip code
» phone|string|false|Phone number
» phone_ext|string|false|Phone extension
» email|string|false|Email
» fax|string|false|Fax
» latitude|number(float)|false|Coordinate (latitude). This field value can be _null_
» longitude|number(float)|false|Coordinate (longitude). This field value can be _null_





