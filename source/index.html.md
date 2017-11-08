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
external_id|query|array[string]|false|External ID's to filter by
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
        "bus_hours_start_at": "2017-11-07T20:11:26Z",
        "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
        "bus_hours_start_at": "2017-11-07T20:11:26Z",
        "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
        "bus_hours_start_at": "2017-11-07T20:11:26Z",
        "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
      "pickup_start_at": "2017-11-07T20:11:26Z",
      "pickup_end_at": "2017-11-07T20:11:26Z",
      "pickup_appt_start_at": "2017-11-07T20:11:26Z",
      "pickup_appt_end_at": "2017-11-07T20:11:26Z",
      "delivery_start_at": "2017-11-07T20:11:26Z",
      "delivery_end_at": "2017-11-07T20:11:26Z",
      "delivery_appt_start_at": "2017-11-07T20:11:26Z",
      "delivery_appt_end_at": "2017-11-07T20:11:26Z",
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
» origin|[OrderAddress](#schemaorderaddress)|true|Address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_
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
» destination|[OrderAddress](#schemaorderaddress)|true|Address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_
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
» billing|[OrderAddress](#schemaorderaddress)|true|Address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_
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
» commodities|[[OrderCommodity](#schemaordercommodity)]|false|Commodities items
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
curl -X POST https://platform.roserocket.com/v1/orders/customers/{customerID}/orders \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST https://platform.roserocket.com/v1/orders/customers/{customerID}/orders HTTP/1.1
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
  url: 'https://platform.roserocket.com/v1/orders/customers/{customerID}/orders',
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
    "bus_hours_start_at": "2017-11-07T20:11:26Z",
    "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
    "bus_hours_start_at": "2017-11-07T20:11:26Z",
    "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
    "bus_hours_start_at": "2017-11-07T20:11:26Z",
    "bus_hours_end_at": "2017-11-07T20:11:26Z"
  },
  "billing_option": "prepaid",
  "notes": "string",
  "po_num": "string",
  "tender_num": "string",
  "ref_num": "string",
  "custom_broker": "string",
  "declared_value": 0,
  "declared_value_currency": "cad",
  "pickup_start_at": "2017-11-07T20:11:26Z",
  "pickup_end_at": "2017-11-07T20:11:26Z",
  "pickup_appt_start_at": "2017-11-07T20:11:26Z",
  "pickup_appt_end_at": "2017-11-07T20:11:26Z",
  "delivery_start_at": "2017-11-07T20:11:26Z",
  "delivery_end_at": "2017-11-07T20:11:26Z",
  "delivery_appt_start_at": "2017-11-07T20:11:26Z",
  "delivery_appt_end_at": "2017-11-07T20:11:26Z",
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

fetch('https://platform.roserocket.com/v1/orders/customers/{customerID}/orders',
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

result = RestClient.post 'https://platform.roserocket.com/v1/orders/customers/{customerID}/orders',
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

r = requests.post('https://platform.roserocket.com/v1/orders/customers/{customerID}/orders', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/orders/customers/{customerID}/orders");
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

`POST /orders/customers/{customerID}/orders`

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
    "bus_hours_start_at": "2017-11-07T20:11:26Z",
    "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
    "bus_hours_start_at": "2017-11-07T20:11:26Z",
    "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
    "bus_hours_start_at": "2017-11-07T20:11:26Z",
    "bus_hours_end_at": "2017-11-07T20:11:26Z"
  },
  "billing_option": "prepaid",
  "notes": "string",
  "po_num": "string",
  "tender_num": "string",
  "ref_num": "string",
  "custom_broker": "string",
  "declared_value": 0,
  "declared_value_currency": "cad",
  "pickup_start_at": "2017-11-07T20:11:26Z",
  "pickup_end_at": "2017-11-07T20:11:26Z",
  "pickup_appt_start_at": "2017-11-07T20:11:26Z",
  "pickup_appt_end_at": "2017-11-07T20:11:26Z",
  "delivery_start_at": "2017-11-07T20:11:26Z",
  "delivery_end_at": "2017-11-07T20:11:26Z",
  "delivery_appt_start_at": "2017-11-07T20:11:26Z",
  "delivery_appt_end_at": "2017-11-07T20:11:26Z",
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
customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__.
body|body|[Order](#schemaorder)|true|Order object
» id|body|string(uuid)|false|Auto generated system ID
» sequence_id|body|integer|false|Auto generated sequence ID per customer
» external_id|body|string|false|External ID for mapping the order to an external system. This field value can be _null_
» public_id|body|string|false|Auto generated human readable ID
» customer|body|[OrderCustomer](#schemaordercustomer)|false|Customer
»» id|body|string(uuid)|false|Auto generated customer id
»» external_id|body|string|false|Customer external id. This field value can be _null_
»» short_code|body|string|false|Customer's short code
» origin|body|[OrderAddress](#schemaorderaddress)|true|Address
»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_
»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_
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
» destination|body|[OrderAddress](#schemaorderaddress)|true|Address
»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_
»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_
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
» billing|body|[OrderAddress](#schemaorderaddress)|true|Address
»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_
»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_
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
» commodities|body|[[OrderCommodity](#schemaordercommodity)]|false|Commodities items
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
      "bus_hours_start_at": "2017-11-07T20:11:26Z",
      "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
      "bus_hours_start_at": "2017-11-07T20:11:26Z",
      "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
      "bus_hours_start_at": "2017-11-07T20:11:26Z",
      "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
    "pickup_start_at": "2017-11-07T20:11:26Z",
    "pickup_end_at": "2017-11-07T20:11:26Z",
    "pickup_appt_start_at": "2017-11-07T20:11:26Z",
    "pickup_appt_end_at": "2017-11-07T20:11:26Z",
    "delivery_start_at": "2017-11-07T20:11:26Z",
    "delivery_end_at": "2017-11-07T20:11:26Z",
    "delivery_appt_start_at": "2017-11-07T20:11:26Z",
    "delivery_appt_end_at": "2017-11-07T20:11:26Z",
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
» origin|[OrderAddress](#schemaorderaddress)|true|Address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_
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
» destination|[OrderAddress](#schemaorderaddress)|true|Address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_
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
» billing|[OrderAddress](#schemaorderaddress)|true|Address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_
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
» commodities|[[OrderCommodity](#schemaordercommodity)]|false|Commodities items
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

## getOrderByID

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID} \
  -H 'Accept: application/json'

```

```http
GET https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID} HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID}',
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

fetch('https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID}',
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

result = RestClient.get 'https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID}");
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

`GET /orders/customers/{customerID}/orders/{orderID}`

*Get customer's order by ID*

<h3 id="getOrderByID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__.
orderID|path|string(uuid)|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__. So for example if the order's external ID is __order123__ then the value of customerID should be __ext:order1234__.


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
      "bus_hours_start_at": "2017-11-07T20:11:26Z",
      "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
      "bus_hours_start_at": "2017-11-07T20:11:26Z",
      "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
      "bus_hours_start_at": "2017-11-07T20:11:26Z",
      "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
    "pickup_start_at": "2017-11-07T20:11:26Z",
    "pickup_end_at": "2017-11-07T20:11:26Z",
    "pickup_appt_start_at": "2017-11-07T20:11:26Z",
    "pickup_appt_end_at": "2017-11-07T20:11:26Z",
    "delivery_start_at": "2017-11-07T20:11:26Z",
    "delivery_end_at": "2017-11-07T20:11:26Z",
    "delivery_appt_start_at": "2017-11-07T20:11:26Z",
    "delivery_appt_end_at": "2017-11-07T20:11:26Z",
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
» origin|[OrderAddress](#schemaorderaddress)|true|Address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_
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
» destination|[OrderAddress](#schemaorderaddress)|true|Address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_
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
» billing|[OrderAddress](#schemaorderaddress)|true|Address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_
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
» commodities|[[OrderCommodity](#schemaordercommodity)]|false|Commodities items
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
curl -X PUT https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID} HTTP/1.1
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
  url: 'https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID}',
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
    "bus_hours_start_at": "2017-11-07T20:11:26Z",
    "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
    "bus_hours_start_at": "2017-11-07T20:11:26Z",
    "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
    "bus_hours_start_at": "2017-11-07T20:11:26Z",
    "bus_hours_end_at": "2017-11-07T20:11:26Z"
  },
  "billing_option": "prepaid",
  "notes": "string",
  "po_num": "string",
  "tender_num": "string",
  "ref_num": "string",
  "custom_broker": "string",
  "declared_value": 0,
  "declared_value_currency": "cad",
  "pickup_start_at": "2017-11-07T20:11:26Z",
  "pickup_end_at": "2017-11-07T20:11:26Z",
  "pickup_appt_start_at": "2017-11-07T20:11:26Z",
  "pickup_appt_end_at": "2017-11-07T20:11:26Z",
  "delivery_start_at": "2017-11-07T20:11:26Z",
  "delivery_end_at": "2017-11-07T20:11:26Z",
  "delivery_appt_start_at": "2017-11-07T20:11:26Z",
  "delivery_appt_end_at": "2017-11-07T20:11:26Z",
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

fetch('https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID}',
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

result = RestClient.put 'https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID}',
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

r = requests.put('https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID}");
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

`PUT /orders/customers/{customerID}/orders/{orderID}`

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
    "bus_hours_start_at": "2017-11-07T20:11:26Z",
    "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
    "bus_hours_start_at": "2017-11-07T20:11:26Z",
    "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
    "bus_hours_start_at": "2017-11-07T20:11:26Z",
    "bus_hours_end_at": "2017-11-07T20:11:26Z"
  },
  "billing_option": "prepaid",
  "notes": "string",
  "po_num": "string",
  "tender_num": "string",
  "ref_num": "string",
  "custom_broker": "string",
  "declared_value": 0,
  "declared_value_currency": "cad",
  "pickup_start_at": "2017-11-07T20:11:26Z",
  "pickup_end_at": "2017-11-07T20:11:26Z",
  "pickup_appt_start_at": "2017-11-07T20:11:26Z",
  "pickup_appt_end_at": "2017-11-07T20:11:26Z",
  "delivery_start_at": "2017-11-07T20:11:26Z",
  "delivery_end_at": "2017-11-07T20:11:26Z",
  "delivery_appt_start_at": "2017-11-07T20:11:26Z",
  "delivery_appt_end_at": "2017-11-07T20:11:26Z",
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
customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__.
orderID|path|string(uuid)|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__. So for example if the order's external ID is __order123__ then the value of customerID should be __ext:order1234__.
body|body|[Order](#schemaorder)|true|Order object
» id|body|string(uuid)|false|Auto generated system ID
» sequence_id|body|integer|false|Auto generated sequence ID per customer
» external_id|body|string|false|External ID for mapping the order to an external system. This field value can be _null_
» public_id|body|string|false|Auto generated human readable ID
» customer|body|[OrderCustomer](#schemaordercustomer)|false|Customer
»» id|body|string(uuid)|false|Auto generated customer id
»» external_id|body|string|false|Customer external id. This field value can be _null_
»» short_code|body|string|false|Customer's short code
» origin|body|[OrderAddress](#schemaorderaddress)|true|Address
»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_
»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_
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
» destination|body|[OrderAddress](#schemaorderaddress)|true|Address
»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_
»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_
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
» billing|body|[OrderAddress](#schemaorderaddress)|true|Address
»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_
»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_
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
» commodities|body|[[OrderCommodity](#schemaordercommodity)]|false|Commodities items
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
      "bus_hours_start_at": "2017-11-07T20:11:26Z",
      "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
      "bus_hours_start_at": "2017-11-07T20:11:26Z",
      "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
      "bus_hours_start_at": "2017-11-07T20:11:26Z",
      "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
    "pickup_start_at": "2017-11-07T20:11:26Z",
    "pickup_end_at": "2017-11-07T20:11:26Z",
    "pickup_appt_start_at": "2017-11-07T20:11:26Z",
    "pickup_appt_end_at": "2017-11-07T20:11:26Z",
    "delivery_start_at": "2017-11-07T20:11:26Z",
    "delivery_end_at": "2017-11-07T20:11:26Z",
    "delivery_appt_start_at": "2017-11-07T20:11:26Z",
    "delivery_appt_end_at": "2017-11-07T20:11:26Z",
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
» origin|[OrderAddress](#schemaorderaddress)|true|Address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_
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
» destination|[OrderAddress](#schemaorderaddress)|true|Address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_
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
» billing|[OrderAddress](#schemaorderaddress)|true|Address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_
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
» commodities|[[OrderCommodity](#schemaordercommodity)]|false|Commodities items
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
curl -X DELETE https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID} \
  -H 'Accept: application/json'

```

```http
DELETE https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID} HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID}',
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

fetch('https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID}',
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

result = RestClient.delete 'https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID}");
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

`DELETE /orders/customers/{customerID}/orders/{orderID}`

*Delete customer's order by ID*

<h3 id="deleteOrderByID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__.
orderID|path|string(uuid)|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__. So for example if the order's external ID is __order123__ then the value of customerID should be __ext:order1234__.


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
      "bus_hours_start_at": "2017-11-07T20:11:26Z",
      "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
      "bus_hours_start_at": "2017-11-07T20:11:26Z",
      "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
      "bus_hours_start_at": "2017-11-07T20:11:26Z",
      "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
    "pickup_start_at": "2017-11-07T20:11:26Z",
    "pickup_end_at": "2017-11-07T20:11:26Z",
    "pickup_appt_start_at": "2017-11-07T20:11:26Z",
    "pickup_appt_end_at": "2017-11-07T20:11:26Z",
    "delivery_start_at": "2017-11-07T20:11:26Z",
    "delivery_end_at": "2017-11-07T20:11:26Z",
    "delivery_appt_start_at": "2017-11-07T20:11:26Z",
    "delivery_appt_end_at": "2017-11-07T20:11:26Z",
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
» origin|[OrderAddress](#schemaorderaddress)|true|Address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_
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
» destination|[OrderAddress](#schemaorderaddress)|true|Address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_
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
» billing|[OrderAddress](#schemaorderaddress)|true|Address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_
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
» commodities|[[OrderCommodity](#schemaordercommodity)]|false|Commodities items
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
external_id|query|array[string]|false|External ID's to filter by
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
oauth2 ( Scopes: orders )
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
oauth2 ( Scopes: orders )
</aside>

## getCustomerByID

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/orders/customers/{customerID} \
  -H 'Accept: application/json'

```

```http
GET https://platform.roserocket.com/v1/orders/customers/{customerID} HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/orders/customers/{customerID}',
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

fetch('https://platform.roserocket.com/v1/orders/customers/{customerID}',
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

result = RestClient.get 'https://platform.roserocket.com/v1/orders/customers/{customerID}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://platform.roserocket.com/v1/orders/customers/{customerID}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/orders/customers/{customerID}");
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

`GET /orders/customers/{customerID}`

*Get customer by ID*

<h3 id="getCustomerByID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__.


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
oauth2 ( Scopes: orders )
</aside>

## updateCustomerByID

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/orders/customers/{customerID} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT https://platform.roserocket.com/v1/orders/customers/{customerID} HTTP/1.1
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
  url: 'https://platform.roserocket.com/v1/orders/customers/{customerID}',
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

fetch('https://platform.roserocket.com/v1/orders/customers/{customerID}',
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

result = RestClient.put 'https://platform.roserocket.com/v1/orders/customers/{customerID}',
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

r = requests.put('https://platform.roserocket.com/v1/orders/customers/{customerID}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/orders/customers/{customerID}");
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

`PUT /orders/customers/{customerID}`

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
customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__.
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
      "bus_hours_start_at": "2017-11-07T20:11:26Z",
      "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
      "bus_hours_start_at": "2017-11-07T20:11:26Z",
      "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
      "bus_hours_start_at": "2017-11-07T20:11:26Z",
      "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
    "pickup_start_at": "2017-11-07T20:11:26Z",
    "pickup_end_at": "2017-11-07T20:11:26Z",
    "pickup_appt_start_at": "2017-11-07T20:11:26Z",
    "pickup_appt_end_at": "2017-11-07T20:11:26Z",
    "delivery_start_at": "2017-11-07T20:11:26Z",
    "delivery_end_at": "2017-11-07T20:11:26Z",
    "delivery_appt_start_at": "2017-11-07T20:11:26Z",
    "delivery_appt_end_at": "2017-11-07T20:11:26Z",
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
» origin|[OrderAddress](#schemaorderaddress)|true|Address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_
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
» destination|[OrderAddress](#schemaorderaddress)|true|Address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_
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
» billing|[OrderAddress](#schemaorderaddress)|true|Address
»» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_
»» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_
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
» commodities|[[OrderCommodity](#schemaordercommodity)]|false|Commodities items
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

## deleteCustomerByID

> Code samples

```shell
# You can also use wget
curl -X DELETE https://platform.roserocket.com/v1/orders/customers/{customerID} \
  -H 'Accept: application/json'

```

```http
DELETE https://platform.roserocket.com/v1/orders/customers/{customerID} HTTP/1.1
Host: platform.roserocket.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/orders/customers/{customerID}',
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

fetch('https://platform.roserocket.com/v1/orders/customers/{customerID}',
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

result = RestClient.delete 'https://platform.roserocket.com/v1/orders/customers/{customerID}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('https://platform.roserocket.com/v1/orders/customers/{customerID}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/orders/customers/{customerID}");
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

`DELETE /orders/customers/{customerID}`

*Delete customer by ID*

<h3 id="deleteCustomerByID-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
customerID|path|string(uuid)|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__.


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
oauth2 ( Scopes: orders )
</aside>

## upsertCustomerByID

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/orders/customers/{customerExtID}/upsert \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT https://platform.roserocket.com/v1/orders/customers/{customerExtID}/upsert HTTP/1.1
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
  url: 'https://platform.roserocket.com/v1/orders/customers/{customerExtID}/upsert',
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

fetch('https://platform.roserocket.com/v1/orders/customers/{customerExtID}/upsert',
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

result = RestClient.put 'https://platform.roserocket.com/v1/orders/customers/{customerExtID}/upsert',
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

r = requests.put('https://platform.roserocket.com/v1/orders/customers/{customerExtID}/upsert', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/orders/customers/{customerExtID}/upsert");
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

`PUT /orders/customers/{customerExtID}/upsert`

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
customerExtID|path|string|true|External ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__.
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
oauth2 ( Scopes: orders )
</aside>

# quote

Manage quotes

## createOrderSpotQuote

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID}/spot_quote \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID}/spot_quote HTTP/1.1
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
  url: 'https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID}/spot_quote',
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
  "est_delivery_start_at": "2017-11-07T20:11:26Z",
  "est_delivery_end_at": "2017-11-07T20:11:26Z",
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

fetch('https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID}/spot_quote',
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

result = RestClient.post 'https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID}/spot_quote',
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

r = requests.post('https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID}/spot_quote', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://platform.roserocket.com/v1/orders/customers/{customerID}/orders/{orderID}/spot_quote");
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

`POST /orders/customers/{customerID}/orders/{orderID}/spot_quote`

*Create a spot quote for a customer's order*

> Body parameter

```json
{
  "notes": "string",
  "est_delivery_start_at": "2017-11-07T20:11:26Z",
  "est_delivery_end_at": "2017-11-07T20:11:26Z",
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
customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__.
orderID|path|string(uuid)|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__. So for example if the order's external ID is __order123__ then the value of customerID should be __ext:order1234__.
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
    "pickup_start_at": "2017-11-07T20:11:26Z",
    "pickup_end_at": "2017-11-07T20:11:26Z",
    "est_delivery_start_at": "2017-11-07T20:11:26Z",
    "est_delivery_end_at": "2017-11-07T20:11:26Z",
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
    "bus_hours_start_at": "2017-11-07T20:11:26Z",
    "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
    "bus_hours_start_at": "2017-11-07T20:11:26Z",
    "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
    "bus_hours_start_at": "2017-11-07T20:11:26Z",
    "bus_hours_end_at": "2017-11-07T20:11:26Z"
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
  "pickup_start_at": "2017-11-07T20:11:26Z",
  "pickup_end_at": "2017-11-07T20:11:26Z",
  "pickup_appt_start_at": "2017-11-07T20:11:26Z",
  "pickup_appt_end_at": "2017-11-07T20:11:26Z",
  "delivery_start_at": "2017-11-07T20:11:26Z",
  "delivery_end_at": "2017-11-07T20:11:26Z",
  "delivery_appt_start_at": "2017-11-07T20:11:26Z",
  "delivery_appt_end_at": "2017-11-07T20:11:26Z",
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
origin|[OrderAddress](#schemaorderaddress)|true|Address
» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_
» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_
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
destination|[OrderAddress](#schemaorderaddress)|true|Address
» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_
» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_
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
billing|[OrderAddress](#schemaorderaddress)|true|Address
» address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_
» address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_
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
commodities|[[OrderCommodity](#schemaordercommodity)]|false|Commodities items
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
  "bus_hours_start_at": "2017-11-07T20:11:26Z",
  "bus_hours_end_at": "2017-11-07T20:11:26Z"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
address_book_id|string(uuid)|false|Auto generated address book id. This field value can be _null_
address_book_external_id|string(uuid)|false|Address book external id. This field value can be _null_
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



## OrderCommodity

<a name="schemaordercommodity"></a>

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
  "est_delivery_start_at": "2017-11-07T20:11:26Z",
  "est_delivery_end_at": "2017-11-07T20:11:26Z",
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
  "pickup_start_at": "2017-11-07T20:11:26Z",
  "pickup_end_at": "2017-11-07T20:11:26Z",
  "est_delivery_start_at": "2017-11-07T20:11:26Z",
  "est_delivery_end_at": "2017-11-07T20:11:26Z",
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





