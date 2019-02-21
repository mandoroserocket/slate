---
title: Rose Rocket Platform REST API
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<h1 id="rose-rocket-platform-rest-api">Rose Rocket Platform REST API v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

The Platform REST API lets you integrate with Rose Rocket applications using simple HTTP methods, in JSON formats, making this an ideal API for developing mobile applications or external clients.

Base URLs:

* <a href="https://platform.roserocket.com/v1">https://platform.roserocket.com/v1</a>

<a href="http://swagger.io/terms/">Terms of service</a>
Email: <a href="mailto:platform@roserocket.com">Support</a> 

# Authentication

- oAuth2 authentication. 

    - Flow: password

    - Token URL = [https://auth.roserocket.com/oauth2/token](https://auth.roserocket.com/oauth2/token)

|Scope|Scope Description|
|---|---|
|orders|manage orders|
|customers|manage customers|
|legs|manage legs|
|manifests|manage manifests|

* API Key (jwt)
    - Parameter Name: **Authorization**, in: header. 

<h1 id="rose-rocket-platform-rest-api-order">order</h1>

Manage orders

## searchOrders

<a id="opIdsearchOrders"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/orders \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://platform.roserocket.com/v1/orders HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://platform.roserocket.com/v1/orders',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://platform.roserocket.com/v1/orders", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /orders`

*Search orders*

<h3 id="searchorders-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|created_start_at|query|string(date-time)|false|Date range (start)|
|created_end_at|query|string(date-time)|false|Date range (end)|
|search_term|query|string|false|Search term|
|external_id|query|string|false|External ID to filter by|
|in_external_ids|query|array[string]|false|External ID's to filter by|
|offset|query|integer|false|Pagination offset|
|limit|query|integer|false|Pagination limit|

> Example responses

> 200 Response

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
        "bus_hours_start_at": "2019-02-21T15:32:17Z",
        "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
        "bus_hours_start_at": "2019-02-21T15:32:17Z",
        "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
        "bus_hours_start_at": "2019-02-21T15:32:17Z",
        "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
      "pickup_start_at": "2019-02-21T15:32:17Z",
      "pickup_end_at": "2019-02-21T15:32:17Z",
      "pickup_appt_start_at": "2019-02-21T15:32:17Z",
      "pickup_appt_end_at": "2019-02-21T15:32:17Z",
      "delivery_start_at": "2019-02-21T15:32:17Z",
      "delivery_end_at": "2019-02-21T15:32:17Z",
      "delivery_appt_start_at": "2019-02-21T15:32:17Z",
      "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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

<h3 id="searchorders-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="searchorders-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» orders|[[Order](#schemaorder)]|false|none|[Customer's order]|
|»» id|string(uuid)|false|read-only|Auto generated system ID|
|»» sequence_id|integer|false|read-only|Auto generated sequence ID per customer|
|»» external_id|string|false|none|External ID for mapping the order to an external system. This field value can be _null_|
|»» public_id|string|false|read-only|Auto generated human readable ID|
|»» customer|[OrderCustomer](#schemaordercustomer)|false|none|Customer|
|»»» id|string(uuid)|false|read-only|Auto generated customer id|
|»»» external_id|string|false|read-only|Customer external id. This field value can be _null_|
|»»» short_code|string|false|read-only|Customer's short code|
|»» origin|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|»»» address_book_id|string(uuid)|false|read-only|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.|
|»»» address_book_external_id|string(uuid)|false|none|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.|
|»»» org_name|string|false|none|Organization name|
|»»» contact_name|string|false|none|Contact name|
|»»» address_1|string|false|none|Address line 1|
|»»» address_2|string|false|none|Address line 2|
|»»» suite|string|false|none|Suite number|
|»»» city|string|false|none|City|
|»»» state|string|false|none|State / Province|
|»»» country|string|false|none|Country (2 letter ISO)|
|»»» postal|string|false|none|Postal / Zip code|
|»»» phone|string|false|none|Phone number|
|»»» phone_ext|string|false|none|Phone extension|
|»»» email|string|false|none|Email|
|»»» fax|string|false|none|Fax|
|»»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»»» bus_hours_start_at|string(date-time)|false|none|Business hours range (start). This field value can be _null_|
|»»» bus_hours_end_at|string(date-time)|false|none|Business hours range (end). This field value can be _null_|
|»» destination|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|»» billing|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|»» status|string|false|read-only|Order Status|
|»» billing_option|string|false|none|Billing Option|
|»» notes|string|false|none|Notes that will appear on BOL|
|»» po_num|string|false|none|Purchase order numbers (if multiple use comma separated values)|
|»» tender_num|string|false|none|Tender number|
|»» ref_num|string|false|none|Reference number|
|»» custom_broker|string|false|none|Custom broker information|
|»» declared_value|number(float)|false|none|Declared value|
|»» declared_value_currency|string|false|none|Declared value currency|
|»» pickup_start_at|string(date-time)|false|none|Pickup time range (start)|
|»» pickup_end_at|string(date-time)|false|none|Pickup time range (end)|
|»» pickup_appt_start_at|string(date-time)|false|none|Pickup appointment time range (start). This field value can be _null_|
|»» pickup_appt_end_at|string(date-time)|false|none|Pickup appointment time range (end). This field value can be _null_|
|»» delivery_start_at|string(date-time)|false|none|Expected delivery time range (start). This field value can be _null_|
|»» delivery_end_at|string(date-time)|false|none|Expected delivery time range (end). This field value can be _null_|
|»» delivery_appt_start_at|string(date-time)|false|none|Delivery appointment time range (start). This field value can be _null_|
|»» delivery_appt_end_at|string(date-time)|false|none|Delivery appointment time range (end). This field value can be _null_|
|»» dim_type|string|false|none|Dimension type|
|»» commodities|[[Commodity](#schemacommodity)]|false|none|Commodities items|
|»»» id|string(uuid)|false|read-only|Auto generated commodity id|
|»»» measurement_unit|string|false|none|Measurement unit|
|»»» weight_unit|string|false|none|Weight unit|
|»»» freight_class|string|false|none|Freight class|
|»»» commodity_type|string|false|none|Commodity type|
|»»» commodity_type_other|string|false|none|If commodity type is set to _other_, then this field must have value|
|»»» description|string|false|none|Description of the commodity|
|»»» feet|number(float)|false|none|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_|
|»»» volume|number(float)|false|none|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_|
|»»» length|number(float)|false|none|Length of the commodity|
|»»» width|number(float)|false|none|Width of the commodity|
|»»» height|number(float)|false|none|Height of the commodity|
|»»» weight|number(float)|false|none|Weight of the commodity|
|»»» nmfc|string|false|none|NMFC number|
|»»» is_stackable|boolean|false|none|Is this commodity can be stacked?|
|»»» quantity|integer|false|none|Quantity of the commodity|
|»»» pieces|integer|false|none|Total number of pieces. This field value can be _null_|
|»»» sku|string|false|none|SKU number|
|»» accessorials|[string]|false|none|none|
|» offset|integer|false|none|none|
|» limit|integer|false|none|none|
|» total|integer|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|new|
|status|saved|
|status|cancelled|
|status|quoting|
|status|quoted|
|status|no-quote|
|status|spot-quote-requested|
|status|pending-dispatch|
|status|dispatched|
|status|in-transit|
|status|delivered|
|status|archived|
|status|invoice-created|
|status|invoice-sent|
|status|invoice-paid|
|status|claim|
|status|draft-quick-quote|
|status|quick-quoting|
|status|quick-quoted|
|status|no-quick-quote|
|status|spot-qq-requested|
|status|pickup-request|
|status|rejected|
|billing_option|prepaid|
|billing_option|collect|
|billing_option|thirdparty|
|declared_value_currency|cad|
|declared_value_currency|usd|
|dim_type|ltl|
|dim_type|ftl|
|dim_type|volume|
|measurement_unit|inch|
|measurement_unit|cm|
|weight_unit|lb|
|weight_unit|kg|
|commodity_type|skid|
|commodity_type|other|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: orders )
</aside>

## createOrder

<a id="opIdcreateOrder"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/customers/{customerID}/orders \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');
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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
  },
  "billing_option": "prepaid",
  "notes": "string",
  "po_num": "string",
  "tender_num": "string",
  "ref_num": "string",
  "custom_broker": "string",
  "declared_value": 0,
  "declared_value_currency": "cad",
  "pickup_start_at": "2019-02-21T15:32:17Z",
  "pickup_end_at": "2019-02-21T15:32:17Z",
  "pickup_appt_start_at": "2019-02-21T15:32:17Z",
  "pickup_appt_end_at": "2019-02-21T15:32:17Z",
  "delivery_start_at": "2019-02-21T15:32:17Z",
  "delivery_end_at": "2019-02-21T15:32:17Z",
  "delivery_appt_start_at": "2019-02-21T15:32:17Z",
  "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
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
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/customers/{customerID}/orders", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
  },
  "billing_option": "prepaid",
  "notes": "string",
  "po_num": "string",
  "tender_num": "string",
  "ref_num": "string",
  "custom_broker": "string",
  "declared_value": 0,
  "declared_value_currency": "cad",
  "pickup_start_at": "2019-02-21T15:32:17Z",
  "pickup_end_at": "2019-02-21T15:32:17Z",
  "pickup_appt_start_at": "2019-02-21T15:32:17Z",
  "pickup_appt_end_at": "2019-02-21T15:32:17Z",
  "delivery_start_at": "2019-02-21T15:32:17Z",
  "delivery_end_at": "2019-02-21T15:32:17Z",
  "delivery_appt_start_at": "2019-02-21T15:32:17Z",
  "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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

<h3 id="createorder-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|[Order](#schemaorder)|true|Order object|

> Example responses

> 200 Response

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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "pickup_start_at": "2019-02-21T15:32:17Z",
    "pickup_end_at": "2019-02-21T15:32:17Z",
    "pickup_appt_start_at": "2019-02-21T15:32:17Z",
    "pickup_appt_end_at": "2019-02-21T15:32:17Z",
    "delivery_start_at": "2019-02-21T15:32:17Z",
    "delivery_end_at": "2019-02-21T15:32:17Z",
    "delivery_appt_start_at": "2019-02-21T15:32:17Z",
    "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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

<h3 id="createorder-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="createorder-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» customer|[Order](#schemaorder)|false|none|Customer's order|
|»» id|string(uuid)|false|read-only|Auto generated system ID|
|»» sequence_id|integer|false|read-only|Auto generated sequence ID per customer|
|»» external_id|string|false|none|External ID for mapping the order to an external system. This field value can be _null_|
|»» public_id|string|false|read-only|Auto generated human readable ID|
|»» customer|[OrderCustomer](#schemaordercustomer)|false|none|Customer|
|»»» id|string(uuid)|false|read-only|Auto generated customer id|
|»»» external_id|string|false|read-only|Customer external id. This field value can be _null_|
|»»» short_code|string|false|read-only|Customer's short code|
|»» origin|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|»»» address_book_id|string(uuid)|false|read-only|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.|
|»»» address_book_external_id|string(uuid)|false|none|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.|
|»»» org_name|string|false|none|Organization name|
|»»» contact_name|string|false|none|Contact name|
|»»» address_1|string|false|none|Address line 1|
|»»» address_2|string|false|none|Address line 2|
|»»» suite|string|false|none|Suite number|
|»»» city|string|false|none|City|
|»»» state|string|false|none|State / Province|
|»»» country|string|false|none|Country (2 letter ISO)|
|»»» postal|string|false|none|Postal / Zip code|
|»»» phone|string|false|none|Phone number|
|»»» phone_ext|string|false|none|Phone extension|
|»»» email|string|false|none|Email|
|»»» fax|string|false|none|Fax|
|»»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»»» bus_hours_start_at|string(date-time)|false|none|Business hours range (start). This field value can be _null_|
|»»» bus_hours_end_at|string(date-time)|false|none|Business hours range (end). This field value can be _null_|
|»» destination|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|»» billing|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|»» status|string|false|read-only|Order Status|
|»» billing_option|string|false|none|Billing Option|
|»» notes|string|false|none|Notes that will appear on BOL|
|»» po_num|string|false|none|Purchase order numbers (if multiple use comma separated values)|
|»» tender_num|string|false|none|Tender number|
|»» ref_num|string|false|none|Reference number|
|»» custom_broker|string|false|none|Custom broker information|
|»» declared_value|number(float)|false|none|Declared value|
|»» declared_value_currency|string|false|none|Declared value currency|
|»» pickup_start_at|string(date-time)|false|none|Pickup time range (start)|
|»» pickup_end_at|string(date-time)|false|none|Pickup time range (end)|
|»» pickup_appt_start_at|string(date-time)|false|none|Pickup appointment time range (start). This field value can be _null_|
|»» pickup_appt_end_at|string(date-time)|false|none|Pickup appointment time range (end). This field value can be _null_|
|»» delivery_start_at|string(date-time)|false|none|Expected delivery time range (start). This field value can be _null_|
|»» delivery_end_at|string(date-time)|false|none|Expected delivery time range (end). This field value can be _null_|
|»» delivery_appt_start_at|string(date-time)|false|none|Delivery appointment time range (start). This field value can be _null_|
|»» delivery_appt_end_at|string(date-time)|false|none|Delivery appointment time range (end). This field value can be _null_|
|»» dim_type|string|false|none|Dimension type|
|»» commodities|[[Commodity](#schemacommodity)]|false|none|Commodities items|
|»»» id|string(uuid)|false|read-only|Auto generated commodity id|
|»»» measurement_unit|string|false|none|Measurement unit|
|»»» weight_unit|string|false|none|Weight unit|
|»»» freight_class|string|false|none|Freight class|
|»»» commodity_type|string|false|none|Commodity type|
|»»» commodity_type_other|string|false|none|If commodity type is set to _other_, then this field must have value|
|»»» description|string|false|none|Description of the commodity|
|»»» feet|number(float)|false|none|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_|
|»»» volume|number(float)|false|none|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_|
|»»» length|number(float)|false|none|Length of the commodity|
|»»» width|number(float)|false|none|Width of the commodity|
|»»» height|number(float)|false|none|Height of the commodity|
|»»» weight|number(float)|false|none|Weight of the commodity|
|»»» nmfc|string|false|none|NMFC number|
|»»» is_stackable|boolean|false|none|Is this commodity can be stacked?|
|»»» quantity|integer|false|none|Quantity of the commodity|
|»»» pieces|integer|false|none|Total number of pieces. This field value can be _null_|
|»»» sku|string|false|none|SKU number|
|»» accessorials|[string]|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|new|
|status|saved|
|status|cancelled|
|status|quoting|
|status|quoted|
|status|no-quote|
|status|spot-quote-requested|
|status|pending-dispatch|
|status|dispatched|
|status|in-transit|
|status|delivered|
|status|archived|
|status|invoice-created|
|status|invoice-sent|
|status|invoice-paid|
|status|claim|
|status|draft-quick-quote|
|status|quick-quoting|
|status|quick-quoted|
|status|no-quick-quote|
|status|spot-qq-requested|
|status|pickup-request|
|status|rejected|
|billing_option|prepaid|
|billing_option|collect|
|billing_option|thirdparty|
|declared_value_currency|cad|
|declared_value_currency|usd|
|dim_type|ltl|
|dim_type|ftl|
|dim_type|volume|
|measurement_unit|inch|
|measurement_unit|cm|
|weight_unit|lb|
|weight_unit|kg|
|commodity_type|skid|
|commodity_type|other|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: orders )
</aside>

## bulkCreateOrder

<a id="opIdbulkCreateOrder"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/customers/{customerID}/orders/bulk_create \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');
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
        "bus_hours_start_at": "2019-02-21T15:32:17Z",
        "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
        "bus_hours_start_at": "2019-02-21T15:32:17Z",
        "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
        "bus_hours_start_at": "2019-02-21T15:32:17Z",
        "bus_hours_end_at": "2019-02-21T15:32:17Z"
      },
      "billing_option": "prepaid",
      "notes": "string",
      "po_num": "string",
      "tender_num": "string",
      "ref_num": "string",
      "custom_broker": "string",
      "declared_value": 0,
      "declared_value_currency": "cad",
      "pickup_start_at": "2019-02-21T15:32:17Z",
      "pickup_end_at": "2019-02-21T15:32:17Z",
      "pickup_appt_start_at": "2019-02-21T15:32:17Z",
      "pickup_appt_end_at": "2019-02-21T15:32:17Z",
      "delivery_start_at": "2019-02-21T15:32:17Z",
      "delivery_end_at": "2019-02-21T15:32:17Z",
      "delivery_appt_start_at": "2019-02-21T15:32:17Z",
      "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
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
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/customers/{customerID}/orders/bulk_create", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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
        "bus_hours_start_at": "2019-02-21T15:32:17Z",
        "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
        "bus_hours_start_at": "2019-02-21T15:32:17Z",
        "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
        "bus_hours_start_at": "2019-02-21T15:32:17Z",
        "bus_hours_end_at": "2019-02-21T15:32:17Z"
      },
      "billing_option": "prepaid",
      "notes": "string",
      "po_num": "string",
      "tender_num": "string",
      "ref_num": "string",
      "custom_broker": "string",
      "declared_value": 0,
      "declared_value_currency": "cad",
      "pickup_start_at": "2019-02-21T15:32:17Z",
      "pickup_end_at": "2019-02-21T15:32:17Z",
      "pickup_appt_start_at": "2019-02-21T15:32:17Z",
      "pickup_appt_end_at": "2019-02-21T15:32:17Z",
      "delivery_start_at": "2019-02-21T15:32:17Z",
      "delivery_end_at": "2019-02-21T15:32:17Z",
      "delivery_appt_start_at": "2019-02-21T15:32:17Z",
      "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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

<h3 id="bulkcreateorder-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|[bulkCreateOrderBody](#schemabulkcreateorderbody)|true|Bulk create request object|
|» orders|body|[[Order](#schemaorder)]|false|[Customer's order]|
|»» id|body|string(uuid)|false|Auto generated system ID|
|»» sequence_id|body|integer|false|Auto generated sequence ID per customer|
|»» external_id|body|string|false|External ID for mapping the order to an external system. This field value can be _null_|
|»» public_id|body|string|false|Auto generated human readable ID|
|»» customer|body|[OrderCustomer](#schemaordercustomer)|false|Customer|
|»»» id|body|string(uuid)|false|Auto generated customer id|
|»»» external_id|body|string|false|Customer external id. This field value can be _null_|
|»»» short_code|body|string|false|Customer's short code|
|»» origin|body|[OrderAddress](#schemaorderaddress)|true|Order address|
|»»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.|
|»»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.|
|»»» org_name|body|string|false|Organization name|
|»»» contact_name|body|string|false|Contact name|
|»»» address_1|body|string|false|Address line 1|
|»»» address_2|body|string|false|Address line 2|
|»»» suite|body|string|false|Suite number|
|»»» city|body|string|false|City|
|»»» state|body|string|false|State / Province|
|»»» country|body|string|false|Country (2 letter ISO)|
|»»» postal|body|string|false|Postal / Zip code|
|»»» phone|body|string|false|Phone number|
|»»» phone_ext|body|string|false|Phone extension|
|»»» email|body|string|false|Email|
|»»» fax|body|string|false|Fax|
|»»» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_|
|»»» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_|
|»»» bus_hours_start_at|body|string(date-time)|false|Business hours range (start). This field value can be _null_|
|»»» bus_hours_end_at|body|string(date-time)|false|Business hours range (end). This field value can be _null_|
|»» destination|body|[OrderAddress](#schemaorderaddress)|true|Order address|
|»» billing|body|[OrderAddress](#schemaorderaddress)|true|Order address|
|»» status|body|string|false|Order Status|
|»» billing_option|body|string|false|Billing Option|
|»» notes|body|string|false|Notes that will appear on BOL|
|»» po_num|body|string|false|Purchase order numbers (if multiple use comma separated values)|
|»» tender_num|body|string|false|Tender number|
|»» ref_num|body|string|false|Reference number|
|»» custom_broker|body|string|false|Custom broker information|
|»» declared_value|body|number(float)|false|Declared value|
|»» declared_value_currency|body|string|false|Declared value currency|
|»» pickup_start_at|body|string(date-time)|false|Pickup time range (start)|
|»» pickup_end_at|body|string(date-time)|false|Pickup time range (end)|
|»» pickup_appt_start_at|body|string(date-time)|false|Pickup appointment time range (start). This field value can be _null_|
|»» pickup_appt_end_at|body|string(date-time)|false|Pickup appointment time range (end). This field value can be _null_|
|»» delivery_start_at|body|string(date-time)|false|Expected delivery time range (start). This field value can be _null_|
|»» delivery_end_at|body|string(date-time)|false|Expected delivery time range (end). This field value can be _null_|
|»» delivery_appt_start_at|body|string(date-time)|false|Delivery appointment time range (start). This field value can be _null_|
|»» delivery_appt_end_at|body|string(date-time)|false|Delivery appointment time range (end). This field value can be _null_|
|»» dim_type|body|string|false|Dimension type|
|»» commodities|body|[[Commodity](#schemacommodity)]|false|Commodities items|
|»»» id|body|string(uuid)|false|Auto generated commodity id|
|»»» measurement_unit|body|string|false|Measurement unit|
|»»» weight_unit|body|string|false|Weight unit|
|»»» freight_class|body|string|false|Freight class|
|»»» commodity_type|body|string|false|Commodity type|
|»»» commodity_type_other|body|string|false|If commodity type is set to _other_, then this field must have value|
|»»» description|body|string|false|Description of the commodity|
|»»» feet|body|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_|
|»»» volume|body|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_|
|»»» length|body|number(float)|false|Length of the commodity|
|»»» width|body|number(float)|false|Width of the commodity|
|»»» height|body|number(float)|false|Height of the commodity|
|»»» weight|body|number(float)|false|Weight of the commodity|
|»»» nmfc|body|string|false|NMFC number|
|»»» is_stackable|body|boolean|false|Is this commodity can be stacked?|
|»»» quantity|body|integer|false|Quantity of the commodity|
|»»» pieces|body|integer|false|Total number of pieces. This field value can be _null_|
|»»» sku|body|string|false|SKU number|
|»» accessorials|body|[string]|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»» status|new|
|»» status|saved|
|»» status|cancelled|
|»» status|quoting|
|»» status|quoted|
|»» status|no-quote|
|»» status|spot-quote-requested|
|»» status|pending-dispatch|
|»» status|dispatched|
|»» status|in-transit|
|»» status|delivered|
|»» status|archived|
|»» status|invoice-created|
|»» status|invoice-sent|
|»» status|invoice-paid|
|»» status|claim|
|»» status|draft-quick-quote|
|»» status|quick-quoting|
|»» status|quick-quoted|
|»» status|no-quick-quote|
|»» status|spot-qq-requested|
|»» status|pickup-request|
|»» status|rejected|
|»» billing_option|prepaid|
|»» billing_option|collect|
|»» billing_option|thirdparty|
|»» declared_value_currency|cad|
|»» declared_value_currency|usd|
|»» dim_type|ltl|
|»» dim_type|ftl|
|»» dim_type|volume|
|»»» measurement_unit|inch|
|»»» measurement_unit|cm|
|»»» weight_unit|lb|
|»»» weight_unit|kg|
|»»» commodity_type|skid|
|»»» commodity_type|other|

> Example responses

> 200 Response

```json
{
  "job_id": "string",
  "message": "string"
}
```

<h3 id="bulkcreateorder-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[BulkOrderCreateResponse](#schemabulkordercreateresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: orders )
</aside>

## bulkCreateOrderCustomerAgnostic

<a id="opIdbulkCreateOrderCustomerAgnostic"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/orders/bulk_create \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');
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
          "bus_hours_start_at": "2019-02-21T15:32:17Z",
          "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
          "bus_hours_start_at": "2019-02-21T15:32:17Z",
          "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
          "bus_hours_start_at": "2019-02-21T15:32:17Z",
          "bus_hours_end_at": "2019-02-21T15:32:17Z"
        },
        "billing_option": "prepaid",
        "notes": "string",
        "po_num": "string",
        "tender_num": "string",
        "ref_num": "string",
        "custom_broker": "string",
        "declared_value": 0,
        "declared_value_currency": "cad",
        "pickup_start_at": "2019-02-21T15:32:17Z",
        "pickup_end_at": "2019-02-21T15:32:17Z",
        "pickup_appt_start_at": "2019-02-21T15:32:17Z",
        "pickup_appt_end_at": "2019-02-21T15:32:17Z",
        "delivery_start_at": "2019-02-21T15:32:17Z",
        "delivery_end_at": "2019-02-21T15:32:17Z",
        "delivery_appt_start_at": "2019-02-21T15:32:17Z",
        "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
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
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/orders/bulk_create", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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
          "bus_hours_start_at": "2019-02-21T15:32:17Z",
          "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
          "bus_hours_start_at": "2019-02-21T15:32:17Z",
          "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
          "bus_hours_start_at": "2019-02-21T15:32:17Z",
          "bus_hours_end_at": "2019-02-21T15:32:17Z"
        },
        "billing_option": "prepaid",
        "notes": "string",
        "po_num": "string",
        "tender_num": "string",
        "ref_num": "string",
        "custom_broker": "string",
        "declared_value": 0,
        "declared_value_currency": "cad",
        "pickup_start_at": "2019-02-21T15:32:17Z",
        "pickup_end_at": "2019-02-21T15:32:17Z",
        "pickup_appt_start_at": "2019-02-21T15:32:17Z",
        "pickup_appt_end_at": "2019-02-21T15:32:17Z",
        "delivery_start_at": "2019-02-21T15:32:17Z",
        "delivery_end_at": "2019-02-21T15:32:17Z",
        "delivery_appt_start_at": "2019-02-21T15:32:17Z",
        "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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

<h3 id="bulkcreateordercustomeragnostic-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[bulkCreateOrderCustomerAgnosticBody](#schemabulkcreateordercustomeragnosticbody)|true|Bulk create request object|
|» orders|body|[object]|false|none|
|»» order|body|[Order](#schemaorder)|false|Customer's order|
|»»» id|body|string(uuid)|false|Auto generated system ID|
|»»» sequence_id|body|integer|false|Auto generated sequence ID per customer|
|»»» external_id|body|string|false|External ID for mapping the order to an external system. This field value can be _null_|
|»»» public_id|body|string|false|Auto generated human readable ID|
|»»» customer|body|[OrderCustomer](#schemaordercustomer)|false|Customer|
|»»»» id|body|string(uuid)|false|Auto generated customer id|
|»»»» external_id|body|string|false|Customer external id. This field value can be _null_|
|»»»» short_code|body|string|false|Customer's short code|
|»»» origin|body|[OrderAddress](#schemaorderaddress)|true|Order address|
|»»»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.|
|»»»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.|
|»»»» org_name|body|string|false|Organization name|
|»»»» contact_name|body|string|false|Contact name|
|»»»» address_1|body|string|false|Address line 1|
|»»»» address_2|body|string|false|Address line 2|
|»»»» suite|body|string|false|Suite number|
|»»»» city|body|string|false|City|
|»»»» state|body|string|false|State / Province|
|»»»» country|body|string|false|Country (2 letter ISO)|
|»»»» postal|body|string|false|Postal / Zip code|
|»»»» phone|body|string|false|Phone number|
|»»»» phone_ext|body|string|false|Phone extension|
|»»»» email|body|string|false|Email|
|»»»» fax|body|string|false|Fax|
|»»»» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_|
|»»»» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_|
|»»»» bus_hours_start_at|body|string(date-time)|false|Business hours range (start). This field value can be _null_|
|»»»» bus_hours_end_at|body|string(date-time)|false|Business hours range (end). This field value can be _null_|
|»»» destination|body|[OrderAddress](#schemaorderaddress)|true|Order address|
|»»» billing|body|[OrderAddress](#schemaorderaddress)|true|Order address|
|»»» status|body|string|false|Order Status|
|»»» billing_option|body|string|false|Billing Option|
|»»» notes|body|string|false|Notes that will appear on BOL|
|»»» po_num|body|string|false|Purchase order numbers (if multiple use comma separated values)|
|»»» tender_num|body|string|false|Tender number|
|»»» ref_num|body|string|false|Reference number|
|»»» custom_broker|body|string|false|Custom broker information|
|»»» declared_value|body|number(float)|false|Declared value|
|»»» declared_value_currency|body|string|false|Declared value currency|
|»»» pickup_start_at|body|string(date-time)|false|Pickup time range (start)|
|»»» pickup_end_at|body|string(date-time)|false|Pickup time range (end)|
|»»» pickup_appt_start_at|body|string(date-time)|false|Pickup appointment time range (start). This field value can be _null_|
|»»» pickup_appt_end_at|body|string(date-time)|false|Pickup appointment time range (end). This field value can be _null_|
|»»» delivery_start_at|body|string(date-time)|false|Expected delivery time range (start). This field value can be _null_|
|»»» delivery_end_at|body|string(date-time)|false|Expected delivery time range (end). This field value can be _null_|
|»»» delivery_appt_start_at|body|string(date-time)|false|Delivery appointment time range (start). This field value can be _null_|
|»»» delivery_appt_end_at|body|string(date-time)|false|Delivery appointment time range (end). This field value can be _null_|
|»»» dim_type|body|string|false|Dimension type|
|»»» commodities|body|[[Commodity](#schemacommodity)]|false|Commodities items|
|»»»» id|body|string(uuid)|false|Auto generated commodity id|
|»»»» measurement_unit|body|string|false|Measurement unit|
|»»»» weight_unit|body|string|false|Weight unit|
|»»»» freight_class|body|string|false|Freight class|
|»»»» commodity_type|body|string|false|Commodity type|
|»»»» commodity_type_other|body|string|false|If commodity type is set to _other_, then this field must have value|
|»»»» description|body|string|false|Description of the commodity|
|»»»» feet|body|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_|
|»»»» volume|body|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_|
|»»»» length|body|number(float)|false|Length of the commodity|
|»»»» width|body|number(float)|false|Width of the commodity|
|»»»» height|body|number(float)|false|Height of the commodity|
|»»»» weight|body|number(float)|false|Weight of the commodity|
|»»»» nmfc|body|string|false|NMFC number|
|»»»» is_stackable|body|boolean|false|Is this commodity can be stacked?|
|»»»» quantity|body|integer|false|Quantity of the commodity|
|»»»» pieces|body|integer|false|Total number of pieces. This field value can be _null_|
|»»»» sku|body|string|false|SKU number|
|»»» accessorials|body|[string]|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»»» status|new|
|»»» status|saved|
|»»» status|cancelled|
|»»» status|quoting|
|»»» status|quoted|
|»»» status|no-quote|
|»»» status|spot-quote-requested|
|»»» status|pending-dispatch|
|»»» status|dispatched|
|»»» status|in-transit|
|»»» status|delivered|
|»»» status|archived|
|»»» status|invoice-created|
|»»» status|invoice-sent|
|»»» status|invoice-paid|
|»»» status|claim|
|»»» status|draft-quick-quote|
|»»» status|quick-quoting|
|»»» status|quick-quoted|
|»»» status|no-quick-quote|
|»»» status|spot-qq-requested|
|»»» status|pickup-request|
|»»» status|rejected|
|»»» billing_option|prepaid|
|»»» billing_option|collect|
|»»» billing_option|thirdparty|
|»»» declared_value_currency|cad|
|»»» declared_value_currency|usd|
|»»» dim_type|ltl|
|»»» dim_type|ftl|
|»»» dim_type|volume|
|»»»» measurement_unit|inch|
|»»»» measurement_unit|cm|
|»»»» weight_unit|lb|
|»»»» weight_unit|kg|
|»»»» commodity_type|skid|
|»»»» commodity_type|other|

> Example responses

> 200 Response

```json
{
  "job_id": "string",
  "message": "string"
}
```

<h3 id="bulkcreateordercustomeragnostic-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[BulkOrderCreateResponse](#schemabulkordercreateresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: orders )
</aside>

## bulkCreateBookedOrder

<a id="opIdbulkCreateBookedOrder"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/customers/{customerID}/bulk_create_booked_order \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');
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
        "bus_hours_start_at": "2019-02-21T15:32:17Z",
        "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
        "bus_hours_start_at": "2019-02-21T15:32:17Z",
        "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
        "bus_hours_start_at": "2019-02-21T15:32:17Z",
        "bus_hours_end_at": "2019-02-21T15:32:17Z"
      },
      "billing_option": "prepaid",
      "notes": "string",
      "po_num": "string",
      "tender_num": "string",
      "ref_num": "string",
      "custom_broker": "string",
      "declared_value": 0,
      "declared_value_currency": "cad",
      "pickup_start_at": "2019-02-21T15:32:17Z",
      "pickup_end_at": "2019-02-21T15:32:17Z",
      "pickup_appt_start_at": "2019-02-21T15:32:17Z",
      "pickup_appt_end_at": "2019-02-21T15:32:17Z",
      "delivery_start_at": "2019-02-21T15:32:17Z",
      "delivery_end_at": "2019-02-21T15:32:17Z",
      "delivery_appt_start_at": "2019-02-21T15:32:17Z",
      "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
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
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/customers/{customerID}/bulk_create_booked_order", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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
        "bus_hours_start_at": "2019-02-21T15:32:17Z",
        "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
        "bus_hours_start_at": "2019-02-21T15:32:17Z",
        "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
        "bus_hours_start_at": "2019-02-21T15:32:17Z",
        "bus_hours_end_at": "2019-02-21T15:32:17Z"
      },
      "billing_option": "prepaid",
      "notes": "string",
      "po_num": "string",
      "tender_num": "string",
      "ref_num": "string",
      "custom_broker": "string",
      "declared_value": 0,
      "declared_value_currency": "cad",
      "pickup_start_at": "2019-02-21T15:32:17Z",
      "pickup_end_at": "2019-02-21T15:32:17Z",
      "pickup_appt_start_at": "2019-02-21T15:32:17Z",
      "pickup_appt_end_at": "2019-02-21T15:32:17Z",
      "delivery_start_at": "2019-02-21T15:32:17Z",
      "delivery_end_at": "2019-02-21T15:32:17Z",
      "delivery_appt_start_at": "2019-02-21T15:32:17Z",
      "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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

<h3 id="bulkcreatebookedorder-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|[bulkCreateOrderBody](#schemabulkcreateorderbody)|true|Bulk create request object|
|» orders|body|[[Order](#schemaorder)]|false|[Customer's order]|
|»» id|body|string(uuid)|false|Auto generated system ID|
|»» sequence_id|body|integer|false|Auto generated sequence ID per customer|
|»» external_id|body|string|false|External ID for mapping the order to an external system. This field value can be _null_|
|»» public_id|body|string|false|Auto generated human readable ID|
|»» customer|body|[OrderCustomer](#schemaordercustomer)|false|Customer|
|»»» id|body|string(uuid)|false|Auto generated customer id|
|»»» external_id|body|string|false|Customer external id. This field value can be _null_|
|»»» short_code|body|string|false|Customer's short code|
|»» origin|body|[OrderAddress](#schemaorderaddress)|true|Order address|
|»»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.|
|»»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.|
|»»» org_name|body|string|false|Organization name|
|»»» contact_name|body|string|false|Contact name|
|»»» address_1|body|string|false|Address line 1|
|»»» address_2|body|string|false|Address line 2|
|»»» suite|body|string|false|Suite number|
|»»» city|body|string|false|City|
|»»» state|body|string|false|State / Province|
|»»» country|body|string|false|Country (2 letter ISO)|
|»»» postal|body|string|false|Postal / Zip code|
|»»» phone|body|string|false|Phone number|
|»»» phone_ext|body|string|false|Phone extension|
|»»» email|body|string|false|Email|
|»»» fax|body|string|false|Fax|
|»»» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_|
|»»» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_|
|»»» bus_hours_start_at|body|string(date-time)|false|Business hours range (start). This field value can be _null_|
|»»» bus_hours_end_at|body|string(date-time)|false|Business hours range (end). This field value can be _null_|
|»» destination|body|[OrderAddress](#schemaorderaddress)|true|Order address|
|»» billing|body|[OrderAddress](#schemaorderaddress)|true|Order address|
|»» status|body|string|false|Order Status|
|»» billing_option|body|string|false|Billing Option|
|»» notes|body|string|false|Notes that will appear on BOL|
|»» po_num|body|string|false|Purchase order numbers (if multiple use comma separated values)|
|»» tender_num|body|string|false|Tender number|
|»» ref_num|body|string|false|Reference number|
|»» custom_broker|body|string|false|Custom broker information|
|»» declared_value|body|number(float)|false|Declared value|
|»» declared_value_currency|body|string|false|Declared value currency|
|»» pickup_start_at|body|string(date-time)|false|Pickup time range (start)|
|»» pickup_end_at|body|string(date-time)|false|Pickup time range (end)|
|»» pickup_appt_start_at|body|string(date-time)|false|Pickup appointment time range (start). This field value can be _null_|
|»» pickup_appt_end_at|body|string(date-time)|false|Pickup appointment time range (end). This field value can be _null_|
|»» delivery_start_at|body|string(date-time)|false|Expected delivery time range (start). This field value can be _null_|
|»» delivery_end_at|body|string(date-time)|false|Expected delivery time range (end). This field value can be _null_|
|»» delivery_appt_start_at|body|string(date-time)|false|Delivery appointment time range (start). This field value can be _null_|
|»» delivery_appt_end_at|body|string(date-time)|false|Delivery appointment time range (end). This field value can be _null_|
|»» dim_type|body|string|false|Dimension type|
|»» commodities|body|[[Commodity](#schemacommodity)]|false|Commodities items|
|»»» id|body|string(uuid)|false|Auto generated commodity id|
|»»» measurement_unit|body|string|false|Measurement unit|
|»»» weight_unit|body|string|false|Weight unit|
|»»» freight_class|body|string|false|Freight class|
|»»» commodity_type|body|string|false|Commodity type|
|»»» commodity_type_other|body|string|false|If commodity type is set to _other_, then this field must have value|
|»»» description|body|string|false|Description of the commodity|
|»»» feet|body|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_|
|»»» volume|body|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_|
|»»» length|body|number(float)|false|Length of the commodity|
|»»» width|body|number(float)|false|Width of the commodity|
|»»» height|body|number(float)|false|Height of the commodity|
|»»» weight|body|number(float)|false|Weight of the commodity|
|»»» nmfc|body|string|false|NMFC number|
|»»» is_stackable|body|boolean|false|Is this commodity can be stacked?|
|»»» quantity|body|integer|false|Quantity of the commodity|
|»»» pieces|body|integer|false|Total number of pieces. This field value can be _null_|
|»»» sku|body|string|false|SKU number|
|»» accessorials|body|[string]|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»» status|new|
|»» status|saved|
|»» status|cancelled|
|»» status|quoting|
|»» status|quoted|
|»» status|no-quote|
|»» status|spot-quote-requested|
|»» status|pending-dispatch|
|»» status|dispatched|
|»» status|in-transit|
|»» status|delivered|
|»» status|archived|
|»» status|invoice-created|
|»» status|invoice-sent|
|»» status|invoice-paid|
|»» status|claim|
|»» status|draft-quick-quote|
|»» status|quick-quoting|
|»» status|quick-quoted|
|»» status|no-quick-quote|
|»» status|spot-qq-requested|
|»» status|pickup-request|
|»» status|rejected|
|»» billing_option|prepaid|
|»» billing_option|collect|
|»» billing_option|thirdparty|
|»» declared_value_currency|cad|
|»» declared_value_currency|usd|
|»» dim_type|ltl|
|»» dim_type|ftl|
|»» dim_type|volume|
|»»» measurement_unit|inch|
|»»» measurement_unit|cm|
|»»» weight_unit|lb|
|»»» weight_unit|kg|
|»»» commodity_type|skid|
|»»» commodity_type|other|

> Example responses

> 200 Response

```json
{
  "job_id": "string",
  "message": "string"
}
```

<h3 id="bulkcreatebookedorder-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[BulkOrderCreateResponse](#schemabulkordercreateresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: orders )
</aside>

## bulkCreateBookedOrderCustomerAgnostic

<a id="opIdbulkCreateBookedOrderCustomerAgnostic"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/orders/bulk_create_booked_order \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');
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
          "bus_hours_start_at": "2019-02-21T15:32:17Z",
          "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
          "bus_hours_start_at": "2019-02-21T15:32:17Z",
          "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
          "bus_hours_start_at": "2019-02-21T15:32:17Z",
          "bus_hours_end_at": "2019-02-21T15:32:17Z"
        },
        "billing_option": "prepaid",
        "notes": "string",
        "po_num": "string",
        "tender_num": "string",
        "ref_num": "string",
        "custom_broker": "string",
        "declared_value": 0,
        "declared_value_currency": "cad",
        "pickup_start_at": "2019-02-21T15:32:17Z",
        "pickup_end_at": "2019-02-21T15:32:17Z",
        "pickup_appt_start_at": "2019-02-21T15:32:17Z",
        "pickup_appt_end_at": "2019-02-21T15:32:17Z",
        "delivery_start_at": "2019-02-21T15:32:17Z",
        "delivery_end_at": "2019-02-21T15:32:17Z",
        "delivery_appt_start_at": "2019-02-21T15:32:17Z",
        "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
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
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/orders/bulk_create_booked_order", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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
          "bus_hours_start_at": "2019-02-21T15:32:17Z",
          "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
          "bus_hours_start_at": "2019-02-21T15:32:17Z",
          "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
          "bus_hours_start_at": "2019-02-21T15:32:17Z",
          "bus_hours_end_at": "2019-02-21T15:32:17Z"
        },
        "billing_option": "prepaid",
        "notes": "string",
        "po_num": "string",
        "tender_num": "string",
        "ref_num": "string",
        "custom_broker": "string",
        "declared_value": 0,
        "declared_value_currency": "cad",
        "pickup_start_at": "2019-02-21T15:32:17Z",
        "pickup_end_at": "2019-02-21T15:32:17Z",
        "pickup_appt_start_at": "2019-02-21T15:32:17Z",
        "pickup_appt_end_at": "2019-02-21T15:32:17Z",
        "delivery_start_at": "2019-02-21T15:32:17Z",
        "delivery_end_at": "2019-02-21T15:32:17Z",
        "delivery_appt_start_at": "2019-02-21T15:32:17Z",
        "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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

<h3 id="bulkcreatebookedordercustomeragnostic-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[bulkCreateOrderCustomerAgnosticBody](#schemabulkcreateordercustomeragnosticbody)|true|Bulk create request object|
|» orders|body|[object]|false|none|
|»» order|body|[Order](#schemaorder)|false|Customer's order|
|»»» id|body|string(uuid)|false|Auto generated system ID|
|»»» sequence_id|body|integer|false|Auto generated sequence ID per customer|
|»»» external_id|body|string|false|External ID for mapping the order to an external system. This field value can be _null_|
|»»» public_id|body|string|false|Auto generated human readable ID|
|»»» customer|body|[OrderCustomer](#schemaordercustomer)|false|Customer|
|»»»» id|body|string(uuid)|false|Auto generated customer id|
|»»»» external_id|body|string|false|Customer external id. This field value can be _null_|
|»»»» short_code|body|string|false|Customer's short code|
|»»» origin|body|[OrderAddress](#schemaorderaddress)|true|Order address|
|»»»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.|
|»»»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.|
|»»»» org_name|body|string|false|Organization name|
|»»»» contact_name|body|string|false|Contact name|
|»»»» address_1|body|string|false|Address line 1|
|»»»» address_2|body|string|false|Address line 2|
|»»»» suite|body|string|false|Suite number|
|»»»» city|body|string|false|City|
|»»»» state|body|string|false|State / Province|
|»»»» country|body|string|false|Country (2 letter ISO)|
|»»»» postal|body|string|false|Postal / Zip code|
|»»»» phone|body|string|false|Phone number|
|»»»» phone_ext|body|string|false|Phone extension|
|»»»» email|body|string|false|Email|
|»»»» fax|body|string|false|Fax|
|»»»» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_|
|»»»» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_|
|»»»» bus_hours_start_at|body|string(date-time)|false|Business hours range (start). This field value can be _null_|
|»»»» bus_hours_end_at|body|string(date-time)|false|Business hours range (end). This field value can be _null_|
|»»» destination|body|[OrderAddress](#schemaorderaddress)|true|Order address|
|»»» billing|body|[OrderAddress](#schemaorderaddress)|true|Order address|
|»»» status|body|string|false|Order Status|
|»»» billing_option|body|string|false|Billing Option|
|»»» notes|body|string|false|Notes that will appear on BOL|
|»»» po_num|body|string|false|Purchase order numbers (if multiple use comma separated values)|
|»»» tender_num|body|string|false|Tender number|
|»»» ref_num|body|string|false|Reference number|
|»»» custom_broker|body|string|false|Custom broker information|
|»»» declared_value|body|number(float)|false|Declared value|
|»»» declared_value_currency|body|string|false|Declared value currency|
|»»» pickup_start_at|body|string(date-time)|false|Pickup time range (start)|
|»»» pickup_end_at|body|string(date-time)|false|Pickup time range (end)|
|»»» pickup_appt_start_at|body|string(date-time)|false|Pickup appointment time range (start). This field value can be _null_|
|»»» pickup_appt_end_at|body|string(date-time)|false|Pickup appointment time range (end). This field value can be _null_|
|»»» delivery_start_at|body|string(date-time)|false|Expected delivery time range (start). This field value can be _null_|
|»»» delivery_end_at|body|string(date-time)|false|Expected delivery time range (end). This field value can be _null_|
|»»» delivery_appt_start_at|body|string(date-time)|false|Delivery appointment time range (start). This field value can be _null_|
|»»» delivery_appt_end_at|body|string(date-time)|false|Delivery appointment time range (end). This field value can be _null_|
|»»» dim_type|body|string|false|Dimension type|
|»»» commodities|body|[[Commodity](#schemacommodity)]|false|Commodities items|
|»»»» id|body|string(uuid)|false|Auto generated commodity id|
|»»»» measurement_unit|body|string|false|Measurement unit|
|»»»» weight_unit|body|string|false|Weight unit|
|»»»» freight_class|body|string|false|Freight class|
|»»»» commodity_type|body|string|false|Commodity type|
|»»»» commodity_type_other|body|string|false|If commodity type is set to _other_, then this field must have value|
|»»»» description|body|string|false|Description of the commodity|
|»»»» feet|body|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_|
|»»»» volume|body|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_|
|»»»» length|body|number(float)|false|Length of the commodity|
|»»»» width|body|number(float)|false|Width of the commodity|
|»»»» height|body|number(float)|false|Height of the commodity|
|»»»» weight|body|number(float)|false|Weight of the commodity|
|»»»» nmfc|body|string|false|NMFC number|
|»»»» is_stackable|body|boolean|false|Is this commodity can be stacked?|
|»»»» quantity|body|integer|false|Quantity of the commodity|
|»»»» pieces|body|integer|false|Total number of pieces. This field value can be _null_|
|»»»» sku|body|string|false|SKU number|
|»»» accessorials|body|[string]|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»»» status|new|
|»»» status|saved|
|»»» status|cancelled|
|»»» status|quoting|
|»»» status|quoted|
|»»» status|no-quote|
|»»» status|spot-quote-requested|
|»»» status|pending-dispatch|
|»»» status|dispatched|
|»»» status|in-transit|
|»»» status|delivered|
|»»» status|archived|
|»»» status|invoice-created|
|»»» status|invoice-sent|
|»»» status|invoice-paid|
|»»» status|claim|
|»»» status|draft-quick-quote|
|»»» status|quick-quoting|
|»»» status|quick-quoted|
|»»» status|no-quick-quote|
|»»» status|spot-qq-requested|
|»»» status|pickup-request|
|»»» status|rejected|
|»»» billing_option|prepaid|
|»»» billing_option|collect|
|»»» billing_option|thirdparty|
|»»» declared_value_currency|cad|
|»»» declared_value_currency|usd|
|»»» dim_type|ltl|
|»»» dim_type|ftl|
|»»» dim_type|volume|
|»»»» measurement_unit|inch|
|»»»» measurement_unit|cm|
|»»»» weight_unit|lb|
|»»»» weight_unit|kg|
|»»»» commodity_type|skid|
|»»»» commodity_type|other|

> Example responses

> 200 Response

```json
{
  "job_id": "string",
  "message": "string"
}
```

<h3 id="bulkcreatebookedordercustomeragnostic-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[BulkOrderCreateResponse](#schemabulkordercreateresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: orders )
</aside>

## bulkUpsertBookedOrderCustomerAgnostic

<a id="opIdbulkUpsertBookedOrderCustomerAgnostic"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/orders/bulk_upsert_booked_order \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');
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
          "bus_hours_start_at": "2019-02-21T15:32:17Z",
          "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
          "bus_hours_start_at": "2019-02-21T15:32:17Z",
          "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
          "bus_hours_start_at": "2019-02-21T15:32:17Z",
          "bus_hours_end_at": "2019-02-21T15:32:17Z"
        },
        "billing_option": "prepaid",
        "notes": "string",
        "po_num": "string",
        "tender_num": "string",
        "ref_num": "string",
        "custom_broker": "string",
        "declared_value": 0,
        "declared_value_currency": "cad",
        "pickup_start_at": "2019-02-21T15:32:17Z",
        "pickup_end_at": "2019-02-21T15:32:17Z",
        "pickup_appt_start_at": "2019-02-21T15:32:17Z",
        "pickup_appt_end_at": "2019-02-21T15:32:17Z",
        "delivery_start_at": "2019-02-21T15:32:17Z",
        "delivery_end_at": "2019-02-21T15:32:17Z",
        "delivery_appt_start_at": "2019-02-21T15:32:17Z",
        "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
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
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/orders/bulk_upsert_booked_order", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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
          "bus_hours_start_at": "2019-02-21T15:32:17Z",
          "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
          "bus_hours_start_at": "2019-02-21T15:32:17Z",
          "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
          "bus_hours_start_at": "2019-02-21T15:32:17Z",
          "bus_hours_end_at": "2019-02-21T15:32:17Z"
        },
        "billing_option": "prepaid",
        "notes": "string",
        "po_num": "string",
        "tender_num": "string",
        "ref_num": "string",
        "custom_broker": "string",
        "declared_value": 0,
        "declared_value_currency": "cad",
        "pickup_start_at": "2019-02-21T15:32:17Z",
        "pickup_end_at": "2019-02-21T15:32:17Z",
        "pickup_appt_start_at": "2019-02-21T15:32:17Z",
        "pickup_appt_end_at": "2019-02-21T15:32:17Z",
        "delivery_start_at": "2019-02-21T15:32:17Z",
        "delivery_end_at": "2019-02-21T15:32:17Z",
        "delivery_appt_start_at": "2019-02-21T15:32:17Z",
        "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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

<h3 id="bulkupsertbookedordercustomeragnostic-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|Bulk upsert request object|
|» orders|body|[object]|false|none|
|»» order|body|[Order](#schemaorder)|false|Customer's order|
|»»» id|body|string(uuid)|false|Auto generated system ID|
|»»» sequence_id|body|integer|false|Auto generated sequence ID per customer|
|»»» external_id|body|string|false|External ID for mapping the order to an external system. This field value can be _null_|
|»»» public_id|body|string|false|Auto generated human readable ID|
|»»» customer|body|[OrderCustomer](#schemaordercustomer)|false|Customer|
|»»»» id|body|string(uuid)|false|Auto generated customer id|
|»»»» external_id|body|string|false|Customer external id. This field value can be _null_|
|»»»» short_code|body|string|false|Customer's short code|
|»»» origin|body|[OrderAddress](#schemaorderaddress)|true|Order address|
|»»»» address_book_id|body|string(uuid)|false|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.|
|»»»» address_book_external_id|body|string(uuid)|false|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.|
|»»»» org_name|body|string|false|Organization name|
|»»»» contact_name|body|string|false|Contact name|
|»»»» address_1|body|string|false|Address line 1|
|»»»» address_2|body|string|false|Address line 2|
|»»»» suite|body|string|false|Suite number|
|»»»» city|body|string|false|City|
|»»»» state|body|string|false|State / Province|
|»»»» country|body|string|false|Country (2 letter ISO)|
|»»»» postal|body|string|false|Postal / Zip code|
|»»»» phone|body|string|false|Phone number|
|»»»» phone_ext|body|string|false|Phone extension|
|»»»» email|body|string|false|Email|
|»»»» fax|body|string|false|Fax|
|»»»» latitude|body|number(float)|false|Coordinate (latitude). This field value can be _null_|
|»»»» longitude|body|number(float)|false|Coordinate (longitude). This field value can be _null_|
|»»»» bus_hours_start_at|body|string(date-time)|false|Business hours range (start). This field value can be _null_|
|»»»» bus_hours_end_at|body|string(date-time)|false|Business hours range (end). This field value can be _null_|
|»»» destination|body|[OrderAddress](#schemaorderaddress)|true|Order address|
|»»» billing|body|[OrderAddress](#schemaorderaddress)|true|Order address|
|»»» status|body|string|false|Order Status|
|»»» billing_option|body|string|false|Billing Option|
|»»» notes|body|string|false|Notes that will appear on BOL|
|»»» po_num|body|string|false|Purchase order numbers (if multiple use comma separated values)|
|»»» tender_num|body|string|false|Tender number|
|»»» ref_num|body|string|false|Reference number|
|»»» custom_broker|body|string|false|Custom broker information|
|»»» declared_value|body|number(float)|false|Declared value|
|»»» declared_value_currency|body|string|false|Declared value currency|
|»»» pickup_start_at|body|string(date-time)|false|Pickup time range (start)|
|»»» pickup_end_at|body|string(date-time)|false|Pickup time range (end)|
|»»» pickup_appt_start_at|body|string(date-time)|false|Pickup appointment time range (start). This field value can be _null_|
|»»» pickup_appt_end_at|body|string(date-time)|false|Pickup appointment time range (end). This field value can be _null_|
|»»» delivery_start_at|body|string(date-time)|false|Expected delivery time range (start). This field value can be _null_|
|»»» delivery_end_at|body|string(date-time)|false|Expected delivery time range (end). This field value can be _null_|
|»»» delivery_appt_start_at|body|string(date-time)|false|Delivery appointment time range (start). This field value can be _null_|
|»»» delivery_appt_end_at|body|string(date-time)|false|Delivery appointment time range (end). This field value can be _null_|
|»»» dim_type|body|string|false|Dimension type|
|»»» commodities|body|[[Commodity](#schemacommodity)]|false|Commodities items|
|»»»» id|body|string(uuid)|false|Auto generated commodity id|
|»»»» measurement_unit|body|string|false|Measurement unit|
|»»»» weight_unit|body|string|false|Weight unit|
|»»»» freight_class|body|string|false|Freight class|
|»»»» commodity_type|body|string|false|Commodity type|
|»»»» commodity_type_other|body|string|false|If commodity type is set to _other_, then this field must have value|
|»»»» description|body|string|false|Description of the commodity|
|»»»» feet|body|number(float)|false|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_|
|»»»» volume|body|number(float)|false|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_|
|»»»» length|body|number(float)|false|Length of the commodity|
|»»»» width|body|number(float)|false|Width of the commodity|
|»»»» height|body|number(float)|false|Height of the commodity|
|»»»» weight|body|number(float)|false|Weight of the commodity|
|»»»» nmfc|body|string|false|NMFC number|
|»»»» is_stackable|body|boolean|false|Is this commodity can be stacked?|
|»»»» quantity|body|integer|false|Quantity of the commodity|
|»»»» pieces|body|integer|false|Total number of pieces. This field value can be _null_|
|»»»» sku|body|string|false|SKU number|
|»»» accessorials|body|[string]|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»»» status|new|
|»»» status|saved|
|»»» status|cancelled|
|»»» status|quoting|
|»»» status|quoted|
|»»» status|no-quote|
|»»» status|spot-quote-requested|
|»»» status|pending-dispatch|
|»»» status|dispatched|
|»»» status|in-transit|
|»»» status|delivered|
|»»» status|archived|
|»»» status|invoice-created|
|»»» status|invoice-sent|
|»»» status|invoice-paid|
|»»» status|claim|
|»»» status|draft-quick-quote|
|»»» status|quick-quoting|
|»»» status|quick-quoted|
|»»» status|no-quick-quote|
|»»» status|spot-qq-requested|
|»»» status|pickup-request|
|»»» status|rejected|
|»»» billing_option|prepaid|
|»»» billing_option|collect|
|»»» billing_option|thirdparty|
|»»» declared_value_currency|cad|
|»»» declared_value_currency|usd|
|»»» dim_type|ltl|
|»»» dim_type|ftl|
|»»» dim_type|volume|
|»»»» measurement_unit|inch|
|»»»» measurement_unit|cm|
|»»»» weight_unit|lb|
|»»»» weight_unit|kg|
|»»»» commodity_type|skid|
|»»»» commodity_type|other|

> Example responses

> 200 Response

```json
{
  "job_id": "string",
  "message": "string"
}
```

<h3 id="bulkupsertbookedordercustomeragnostic-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[BulkOrderCreateResponse](#schemabulkordercreateresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: orders )
</aside>

## reviseOrderOriginByID

<a id="opIdreviseOrderOriginByID"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_origin \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');
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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
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
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_origin", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
  }
}
```

<h3 id="reviseorderoriginbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.|
|orderID|path|string(uuid)|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|[OrderAddressReviseRequest](#schemaorderaddressreviserequest)|true|Revise order address request object|

> Example responses

> 200 Response

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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "pickup_start_at": "2019-02-21T15:32:17Z",
    "pickup_end_at": "2019-02-21T15:32:17Z",
    "pickup_appt_start_at": "2019-02-21T15:32:17Z",
    "pickup_appt_end_at": "2019-02-21T15:32:17Z",
    "delivery_start_at": "2019-02-21T15:32:17Z",
    "delivery_end_at": "2019-02-21T15:32:17Z",
    "delivery_appt_start_at": "2019-02-21T15:32:17Z",
    "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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
      "origin_start_at": "2019-02-21T15:32:17Z",
      "origin_end_at": "2019-02-21T15:32:17Z",
      "origin_appt_start_at": "2019-02-21T15:32:17Z",
      "origin_appt_end_at": "2019-02-21T15:32:17Z",
      "destination_start_at": "2019-02-21T15:32:17Z",
      "destination_end_at": "2019-02-21T15:32:17Z",
      "destination_appt_start_at": "2019-02-21T15:32:17Z",
      "destination_appt_end_at": "2019-02-21T15:32:17Z",
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
        "origin_arrived_at": "2019-02-21T15:32:17Z",
        "origin_in_at": "2019-02-21T15:32:17Z",
        "origin_pickedup_at": "2019-02-21T15:32:17Z",
        "origin_out_at": "2019-02-21T15:32:17Z",
        "destination_arrived_at": "2019-02-21T15:32:17Z",
        "destination_in_at": "2019-02-21T15:32:17Z",
        "destination_delivered_at": "2019-02-21T15:32:17Z",
        "destination_out_at": "2019-02-21T15:32:17Z"
      }
    }
  ]
}
```

<h3 id="reviseorderoriginbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[OrderAndLegsResponse](#schemaorderandlegsresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: orders )
</aside>

## reviseOrderDestinationByID

<a id="opIdreviseOrderDestinationByID"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_destination \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');
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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
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
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_destination", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
  }
}
```

<h3 id="reviseorderdestinationbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.|
|orderID|path|string(uuid)|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|[OrderAddressReviseRequest](#schemaorderaddressreviserequest)|true|Revise order address request object|

> Example responses

> 200 Response

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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "pickup_start_at": "2019-02-21T15:32:17Z",
    "pickup_end_at": "2019-02-21T15:32:17Z",
    "pickup_appt_start_at": "2019-02-21T15:32:17Z",
    "pickup_appt_end_at": "2019-02-21T15:32:17Z",
    "delivery_start_at": "2019-02-21T15:32:17Z",
    "delivery_end_at": "2019-02-21T15:32:17Z",
    "delivery_appt_start_at": "2019-02-21T15:32:17Z",
    "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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
      "origin_start_at": "2019-02-21T15:32:17Z",
      "origin_end_at": "2019-02-21T15:32:17Z",
      "origin_appt_start_at": "2019-02-21T15:32:17Z",
      "origin_appt_end_at": "2019-02-21T15:32:17Z",
      "destination_start_at": "2019-02-21T15:32:17Z",
      "destination_end_at": "2019-02-21T15:32:17Z",
      "destination_appt_start_at": "2019-02-21T15:32:17Z",
      "destination_appt_end_at": "2019-02-21T15:32:17Z",
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
        "origin_arrived_at": "2019-02-21T15:32:17Z",
        "origin_in_at": "2019-02-21T15:32:17Z",
        "origin_pickedup_at": "2019-02-21T15:32:17Z",
        "origin_out_at": "2019-02-21T15:32:17Z",
        "destination_arrived_at": "2019-02-21T15:32:17Z",
        "destination_in_at": "2019-02-21T15:32:17Z",
        "destination_delivered_at": "2019-02-21T15:32:17Z",
        "destination_out_at": "2019-02-21T15:32:17Z"
      }
    }
  ]
}
```

<h3 id="reviseorderdestinationbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[OrderAndLegsResponse](#schemaorderandlegsresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: orders )
</aside>

## reviseOrderCommoditiesByID

<a id="opIdreviseOrderCommoditiesByID"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_commodities \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');
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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
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
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/revise_commodities", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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

<h3 id="reviseordercommoditiesbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.|
|orderID|path|string(uuid)|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|[CommodityReviseRequest](#schemacommodityreviserequest)|true|Revise order commodities request object|

> Example responses

> 200 Response

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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "pickup_start_at": "2019-02-21T15:32:17Z",
    "pickup_end_at": "2019-02-21T15:32:17Z",
    "pickup_appt_start_at": "2019-02-21T15:32:17Z",
    "pickup_appt_end_at": "2019-02-21T15:32:17Z",
    "delivery_start_at": "2019-02-21T15:32:17Z",
    "delivery_end_at": "2019-02-21T15:32:17Z",
    "delivery_appt_start_at": "2019-02-21T15:32:17Z",
    "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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
      "origin_start_at": "2019-02-21T15:32:17Z",
      "origin_end_at": "2019-02-21T15:32:17Z",
      "origin_appt_start_at": "2019-02-21T15:32:17Z",
      "origin_appt_end_at": "2019-02-21T15:32:17Z",
      "destination_start_at": "2019-02-21T15:32:17Z",
      "destination_end_at": "2019-02-21T15:32:17Z",
      "destination_appt_start_at": "2019-02-21T15:32:17Z",
      "destination_appt_end_at": "2019-02-21T15:32:17Z",
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
        "origin_arrived_at": "2019-02-21T15:32:17Z",
        "origin_in_at": "2019-02-21T15:32:17Z",
        "origin_pickedup_at": "2019-02-21T15:32:17Z",
        "origin_out_at": "2019-02-21T15:32:17Z",
        "destination_arrived_at": "2019-02-21T15:32:17Z",
        "destination_in_at": "2019-02-21T15:32:17Z",
        "destination_delivered_at": "2019-02-21T15:32:17Z",
        "destination_out_at": "2019-02-21T15:32:17Z"
      }
    }
  ]
}
```

<h3 id="reviseordercommoditiesbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[OrderAndLegsResponse](#schemaorderandlegsresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: orders )
</aside>

## getOrderInternalEventByOrderID

<a id="opIdgetOrderInternalEventByOrderID"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/events/internal_notes \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/events/internal_notes HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/events/internal_notes',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/events/internal_notes',
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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/events/internal_notes',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/events/internal_notes', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/events/internal_notes");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/events/internal_notes", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /customers/{customerID}/orders/{orderID}/events/internal_notes`

*Get an internal event by orderID*

<h3 id="getorderinternaleventbyorderid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.|
|orderID|path|string(uuid)|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|

> Example responses

> 200 Response

```json
{
  "order_audit_history": [
    {
      "id": "string",
      "created_at": "2019-02-21T15:32:17Z",
      "updated_at": "2019-02-21T15:32:17Z",
      "user_id": "string",
      "order_id": "string",
      "data": {}
    }
  ]
}
```

<h3 id="getorderinternaleventbyorderid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="getorderinternaleventbyorderid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» order_audit_history|[[OrderAuditEvent](#schemaorderauditevent)]|false|none|[An order audit event]|
|»» id|string(uuid)|false|none|none|
|»» created_at|string(date-time)|false|none|The timestamp for the creation of the order file|
|»» updated_at|string(date-time)|false|none|The timestamp for the last update of the order file|
|»» user_id|string(uuid)|false|none|none|
|»» order_id|string(uuid)|false|none|none|
|»» data|object|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: orders )
</aside>

## getOrderByID

<a id="opIdgetOrderByID"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID} HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /customers/{customerID}/orders/{orderID}`

*Get customer's order by ID*

<h3 id="getorderbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.|
|orderID|path|string(uuid)|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|

> Example responses

> 200 Response

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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "pickup_start_at": "2019-02-21T15:32:17Z",
    "pickup_end_at": "2019-02-21T15:32:17Z",
    "pickup_appt_start_at": "2019-02-21T15:32:17Z",
    "pickup_appt_end_at": "2019-02-21T15:32:17Z",
    "delivery_start_at": "2019-02-21T15:32:17Z",
    "delivery_end_at": "2019-02-21T15:32:17Z",
    "delivery_appt_start_at": "2019-02-21T15:32:17Z",
    "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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

<h3 id="getorderbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="getorderbyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» order|[Order](#schemaorder)|false|none|Customer's order|
|»» id|string(uuid)|false|read-only|Auto generated system ID|
|»» sequence_id|integer|false|read-only|Auto generated sequence ID per customer|
|»» external_id|string|false|none|External ID for mapping the order to an external system. This field value can be _null_|
|»» public_id|string|false|read-only|Auto generated human readable ID|
|»» customer|[OrderCustomer](#schemaordercustomer)|false|none|Customer|
|»»» id|string(uuid)|false|read-only|Auto generated customer id|
|»»» external_id|string|false|read-only|Customer external id. This field value can be _null_|
|»»» short_code|string|false|read-only|Customer's short code|
|»» origin|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|»»» address_book_id|string(uuid)|false|read-only|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.|
|»»» address_book_external_id|string(uuid)|false|none|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.|
|»»» org_name|string|false|none|Organization name|
|»»» contact_name|string|false|none|Contact name|
|»»» address_1|string|false|none|Address line 1|
|»»» address_2|string|false|none|Address line 2|
|»»» suite|string|false|none|Suite number|
|»»» city|string|false|none|City|
|»»» state|string|false|none|State / Province|
|»»» country|string|false|none|Country (2 letter ISO)|
|»»» postal|string|false|none|Postal / Zip code|
|»»» phone|string|false|none|Phone number|
|»»» phone_ext|string|false|none|Phone extension|
|»»» email|string|false|none|Email|
|»»» fax|string|false|none|Fax|
|»»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»»» bus_hours_start_at|string(date-time)|false|none|Business hours range (start). This field value can be _null_|
|»»» bus_hours_end_at|string(date-time)|false|none|Business hours range (end). This field value can be _null_|
|»» destination|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|»» billing|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|»» status|string|false|read-only|Order Status|
|»» billing_option|string|false|none|Billing Option|
|»» notes|string|false|none|Notes that will appear on BOL|
|»» po_num|string|false|none|Purchase order numbers (if multiple use comma separated values)|
|»» tender_num|string|false|none|Tender number|
|»» ref_num|string|false|none|Reference number|
|»» custom_broker|string|false|none|Custom broker information|
|»» declared_value|number(float)|false|none|Declared value|
|»» declared_value_currency|string|false|none|Declared value currency|
|»» pickup_start_at|string(date-time)|false|none|Pickup time range (start)|
|»» pickup_end_at|string(date-time)|false|none|Pickup time range (end)|
|»» pickup_appt_start_at|string(date-time)|false|none|Pickup appointment time range (start). This field value can be _null_|
|»» pickup_appt_end_at|string(date-time)|false|none|Pickup appointment time range (end). This field value can be _null_|
|»» delivery_start_at|string(date-time)|false|none|Expected delivery time range (start). This field value can be _null_|
|»» delivery_end_at|string(date-time)|false|none|Expected delivery time range (end). This field value can be _null_|
|»» delivery_appt_start_at|string(date-time)|false|none|Delivery appointment time range (start). This field value can be _null_|
|»» delivery_appt_end_at|string(date-time)|false|none|Delivery appointment time range (end). This field value can be _null_|
|»» dim_type|string|false|none|Dimension type|
|»» commodities|[[Commodity](#schemacommodity)]|false|none|Commodities items|
|»»» id|string(uuid)|false|read-only|Auto generated commodity id|
|»»» measurement_unit|string|false|none|Measurement unit|
|»»» weight_unit|string|false|none|Weight unit|
|»»» freight_class|string|false|none|Freight class|
|»»» commodity_type|string|false|none|Commodity type|
|»»» commodity_type_other|string|false|none|If commodity type is set to _other_, then this field must have value|
|»»» description|string|false|none|Description of the commodity|
|»»» feet|number(float)|false|none|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_|
|»»» volume|number(float)|false|none|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_|
|»»» length|number(float)|false|none|Length of the commodity|
|»»» width|number(float)|false|none|Width of the commodity|
|»»» height|number(float)|false|none|Height of the commodity|
|»»» weight|number(float)|false|none|Weight of the commodity|
|»»» nmfc|string|false|none|NMFC number|
|»»» is_stackable|boolean|false|none|Is this commodity can be stacked?|
|»»» quantity|integer|false|none|Quantity of the commodity|
|»»» pieces|integer|false|none|Total number of pieces. This field value can be _null_|
|»»» sku|string|false|none|SKU number|
|»» accessorials|[string]|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|new|
|status|saved|
|status|cancelled|
|status|quoting|
|status|quoted|
|status|no-quote|
|status|spot-quote-requested|
|status|pending-dispatch|
|status|dispatched|
|status|in-transit|
|status|delivered|
|status|archived|
|status|invoice-created|
|status|invoice-sent|
|status|invoice-paid|
|status|claim|
|status|draft-quick-quote|
|status|quick-quoting|
|status|quick-quoted|
|status|no-quick-quote|
|status|spot-qq-requested|
|status|pickup-request|
|status|rejected|
|billing_option|prepaid|
|billing_option|collect|
|billing_option|thirdparty|
|declared_value_currency|cad|
|declared_value_currency|usd|
|dim_type|ltl|
|dim_type|ftl|
|dim_type|volume|
|measurement_unit|inch|
|measurement_unit|cm|
|weight_unit|lb|
|weight_unit|kg|
|commodity_type|skid|
|commodity_type|other|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: orders )
</aside>

## updateOrderByID

<a id="opIdupdateOrderByID"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');
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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
  },
  "billing_option": "prepaid",
  "notes": "string",
  "po_num": "string",
  "tender_num": "string",
  "ref_num": "string",
  "custom_broker": "string",
  "declared_value": 0,
  "declared_value_currency": "cad",
  "pickup_start_at": "2019-02-21T15:32:17Z",
  "pickup_end_at": "2019-02-21T15:32:17Z",
  "pickup_appt_start_at": "2019-02-21T15:32:17Z",
  "pickup_appt_end_at": "2019-02-21T15:32:17Z",
  "delivery_start_at": "2019-02-21T15:32:17Z",
  "delivery_end_at": "2019-02-21T15:32:17Z",
  "delivery_appt_start_at": "2019-02-21T15:32:17Z",
  "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
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
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
  },
  "billing_option": "prepaid",
  "notes": "string",
  "po_num": "string",
  "tender_num": "string",
  "ref_num": "string",
  "custom_broker": "string",
  "declared_value": 0,
  "declared_value_currency": "cad",
  "pickup_start_at": "2019-02-21T15:32:17Z",
  "pickup_end_at": "2019-02-21T15:32:17Z",
  "pickup_appt_start_at": "2019-02-21T15:32:17Z",
  "pickup_appt_end_at": "2019-02-21T15:32:17Z",
  "delivery_start_at": "2019-02-21T15:32:17Z",
  "delivery_end_at": "2019-02-21T15:32:17Z",
  "delivery_appt_start_at": "2019-02-21T15:32:17Z",
  "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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

<h3 id="updateorderbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.|
|orderID|path|string(uuid)|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|[Order](#schemaorder)|true|Order object|

> Example responses

> 200 Response

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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "pickup_start_at": "2019-02-21T15:32:17Z",
    "pickup_end_at": "2019-02-21T15:32:17Z",
    "pickup_appt_start_at": "2019-02-21T15:32:17Z",
    "pickup_appt_end_at": "2019-02-21T15:32:17Z",
    "delivery_start_at": "2019-02-21T15:32:17Z",
    "delivery_end_at": "2019-02-21T15:32:17Z",
    "delivery_appt_start_at": "2019-02-21T15:32:17Z",
    "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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

<h3 id="updateorderbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="updateorderbyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» order|[Order](#schemaorder)|false|none|Customer's order|
|»» id|string(uuid)|false|read-only|Auto generated system ID|
|»» sequence_id|integer|false|read-only|Auto generated sequence ID per customer|
|»» external_id|string|false|none|External ID for mapping the order to an external system. This field value can be _null_|
|»» public_id|string|false|read-only|Auto generated human readable ID|
|»» customer|[OrderCustomer](#schemaordercustomer)|false|none|Customer|
|»»» id|string(uuid)|false|read-only|Auto generated customer id|
|»»» external_id|string|false|read-only|Customer external id. This field value can be _null_|
|»»» short_code|string|false|read-only|Customer's short code|
|»» origin|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|»»» address_book_id|string(uuid)|false|read-only|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.|
|»»» address_book_external_id|string(uuid)|false|none|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.|
|»»» org_name|string|false|none|Organization name|
|»»» contact_name|string|false|none|Contact name|
|»»» address_1|string|false|none|Address line 1|
|»»» address_2|string|false|none|Address line 2|
|»»» suite|string|false|none|Suite number|
|»»» city|string|false|none|City|
|»»» state|string|false|none|State / Province|
|»»» country|string|false|none|Country (2 letter ISO)|
|»»» postal|string|false|none|Postal / Zip code|
|»»» phone|string|false|none|Phone number|
|»»» phone_ext|string|false|none|Phone extension|
|»»» email|string|false|none|Email|
|»»» fax|string|false|none|Fax|
|»»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»»» bus_hours_start_at|string(date-time)|false|none|Business hours range (start). This field value can be _null_|
|»»» bus_hours_end_at|string(date-time)|false|none|Business hours range (end). This field value can be _null_|
|»» destination|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|»» billing|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|»» status|string|false|read-only|Order Status|
|»» billing_option|string|false|none|Billing Option|
|»» notes|string|false|none|Notes that will appear on BOL|
|»» po_num|string|false|none|Purchase order numbers (if multiple use comma separated values)|
|»» tender_num|string|false|none|Tender number|
|»» ref_num|string|false|none|Reference number|
|»» custom_broker|string|false|none|Custom broker information|
|»» declared_value|number(float)|false|none|Declared value|
|»» declared_value_currency|string|false|none|Declared value currency|
|»» pickup_start_at|string(date-time)|false|none|Pickup time range (start)|
|»» pickup_end_at|string(date-time)|false|none|Pickup time range (end)|
|»» pickup_appt_start_at|string(date-time)|false|none|Pickup appointment time range (start). This field value can be _null_|
|»» pickup_appt_end_at|string(date-time)|false|none|Pickup appointment time range (end). This field value can be _null_|
|»» delivery_start_at|string(date-time)|false|none|Expected delivery time range (start). This field value can be _null_|
|»» delivery_end_at|string(date-time)|false|none|Expected delivery time range (end). This field value can be _null_|
|»» delivery_appt_start_at|string(date-time)|false|none|Delivery appointment time range (start). This field value can be _null_|
|»» delivery_appt_end_at|string(date-time)|false|none|Delivery appointment time range (end). This field value can be _null_|
|»» dim_type|string|false|none|Dimension type|
|»» commodities|[[Commodity](#schemacommodity)]|false|none|Commodities items|
|»»» id|string(uuid)|false|read-only|Auto generated commodity id|
|»»» measurement_unit|string|false|none|Measurement unit|
|»»» weight_unit|string|false|none|Weight unit|
|»»» freight_class|string|false|none|Freight class|
|»»» commodity_type|string|false|none|Commodity type|
|»»» commodity_type_other|string|false|none|If commodity type is set to _other_, then this field must have value|
|»»» description|string|false|none|Description of the commodity|
|»»» feet|number(float)|false|none|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_|
|»»» volume|number(float)|false|none|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_|
|»»» length|number(float)|false|none|Length of the commodity|
|»»» width|number(float)|false|none|Width of the commodity|
|»»» height|number(float)|false|none|Height of the commodity|
|»»» weight|number(float)|false|none|Weight of the commodity|
|»»» nmfc|string|false|none|NMFC number|
|»»» is_stackable|boolean|false|none|Is this commodity can be stacked?|
|»»» quantity|integer|false|none|Quantity of the commodity|
|»»» pieces|integer|false|none|Total number of pieces. This field value can be _null_|
|»»» sku|string|false|none|SKU number|
|»» accessorials|[string]|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|new|
|status|saved|
|status|cancelled|
|status|quoting|
|status|quoted|
|status|no-quote|
|status|spot-quote-requested|
|status|pending-dispatch|
|status|dispatched|
|status|in-transit|
|status|delivered|
|status|archived|
|status|invoice-created|
|status|invoice-sent|
|status|invoice-paid|
|status|claim|
|status|draft-quick-quote|
|status|quick-quoting|
|status|quick-quoted|
|status|no-quick-quote|
|status|spot-qq-requested|
|status|pickup-request|
|status|rejected|
|billing_option|prepaid|
|billing_option|collect|
|billing_option|thirdparty|
|declared_value_currency|cad|
|declared_value_currency|usd|
|dim_type|ltl|
|dim_type|ftl|
|dim_type|volume|
|measurement_unit|inch|
|measurement_unit|cm|
|weight_unit|lb|
|weight_unit|kg|
|commodity_type|skid|
|commodity_type|other|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: orders )
</aside>

## deleteOrderByID

<a id="opIddeleteOrderByID"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID} HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /customers/{customerID}/orders/{orderID}`

*Delete customer's order by ID*

<h3 id="deleteorderbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.|
|orderID|path|string(uuid)|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|

> Example responses

> 200 Response

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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "pickup_start_at": "2019-02-21T15:32:17Z",
    "pickup_end_at": "2019-02-21T15:32:17Z",
    "pickup_appt_start_at": "2019-02-21T15:32:17Z",
    "pickup_appt_end_at": "2019-02-21T15:32:17Z",
    "delivery_start_at": "2019-02-21T15:32:17Z",
    "delivery_end_at": "2019-02-21T15:32:17Z",
    "delivery_appt_start_at": "2019-02-21T15:32:17Z",
    "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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

<h3 id="deleteorderbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="deleteorderbyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» order|[Order](#schemaorder)|false|none|Customer's order|
|»» id|string(uuid)|false|read-only|Auto generated system ID|
|»» sequence_id|integer|false|read-only|Auto generated sequence ID per customer|
|»» external_id|string|false|none|External ID for mapping the order to an external system. This field value can be _null_|
|»» public_id|string|false|read-only|Auto generated human readable ID|
|»» customer|[OrderCustomer](#schemaordercustomer)|false|none|Customer|
|»»» id|string(uuid)|false|read-only|Auto generated customer id|
|»»» external_id|string|false|read-only|Customer external id. This field value can be _null_|
|»»» short_code|string|false|read-only|Customer's short code|
|»» origin|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|»»» address_book_id|string(uuid)|false|read-only|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.|
|»»» address_book_external_id|string(uuid)|false|none|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.|
|»»» org_name|string|false|none|Organization name|
|»»» contact_name|string|false|none|Contact name|
|»»» address_1|string|false|none|Address line 1|
|»»» address_2|string|false|none|Address line 2|
|»»» suite|string|false|none|Suite number|
|»»» city|string|false|none|City|
|»»» state|string|false|none|State / Province|
|»»» country|string|false|none|Country (2 letter ISO)|
|»»» postal|string|false|none|Postal / Zip code|
|»»» phone|string|false|none|Phone number|
|»»» phone_ext|string|false|none|Phone extension|
|»»» email|string|false|none|Email|
|»»» fax|string|false|none|Fax|
|»»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»»» bus_hours_start_at|string(date-time)|false|none|Business hours range (start). This field value can be _null_|
|»»» bus_hours_end_at|string(date-time)|false|none|Business hours range (end). This field value can be _null_|
|»» destination|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|»» billing|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|»» status|string|false|read-only|Order Status|
|»» billing_option|string|false|none|Billing Option|
|»» notes|string|false|none|Notes that will appear on BOL|
|»» po_num|string|false|none|Purchase order numbers (if multiple use comma separated values)|
|»» tender_num|string|false|none|Tender number|
|»» ref_num|string|false|none|Reference number|
|»» custom_broker|string|false|none|Custom broker information|
|»» declared_value|number(float)|false|none|Declared value|
|»» declared_value_currency|string|false|none|Declared value currency|
|»» pickup_start_at|string(date-time)|false|none|Pickup time range (start)|
|»» pickup_end_at|string(date-time)|false|none|Pickup time range (end)|
|»» pickup_appt_start_at|string(date-time)|false|none|Pickup appointment time range (start). This field value can be _null_|
|»» pickup_appt_end_at|string(date-time)|false|none|Pickup appointment time range (end). This field value can be _null_|
|»» delivery_start_at|string(date-time)|false|none|Expected delivery time range (start). This field value can be _null_|
|»» delivery_end_at|string(date-time)|false|none|Expected delivery time range (end). This field value can be _null_|
|»» delivery_appt_start_at|string(date-time)|false|none|Delivery appointment time range (start). This field value can be _null_|
|»» delivery_appt_end_at|string(date-time)|false|none|Delivery appointment time range (end). This field value can be _null_|
|»» dim_type|string|false|none|Dimension type|
|»» commodities|[[Commodity](#schemacommodity)]|false|none|Commodities items|
|»»» id|string(uuid)|false|read-only|Auto generated commodity id|
|»»» measurement_unit|string|false|none|Measurement unit|
|»»» weight_unit|string|false|none|Weight unit|
|»»» freight_class|string|false|none|Freight class|
|»»» commodity_type|string|false|none|Commodity type|
|»»» commodity_type_other|string|false|none|If commodity type is set to _other_, then this field must have value|
|»»» description|string|false|none|Description of the commodity|
|»»» feet|number(float)|false|none|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_|
|»»» volume|number(float)|false|none|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_|
|»»» length|number(float)|false|none|Length of the commodity|
|»»» width|number(float)|false|none|Width of the commodity|
|»»» height|number(float)|false|none|Height of the commodity|
|»»» weight|number(float)|false|none|Weight of the commodity|
|»»» nmfc|string|false|none|NMFC number|
|»»» is_stackable|boolean|false|none|Is this commodity can be stacked?|
|»»» quantity|integer|false|none|Quantity of the commodity|
|»»» pieces|integer|false|none|Total number of pieces. This field value can be _null_|
|»»» sku|string|false|none|SKU number|
|»» accessorials|[string]|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|new|
|status|saved|
|status|cancelled|
|status|quoting|
|status|quoted|
|status|no-quote|
|status|spot-quote-requested|
|status|pending-dispatch|
|status|dispatched|
|status|in-transit|
|status|delivered|
|status|archived|
|status|invoice-created|
|status|invoice-sent|
|status|invoice-paid|
|status|claim|
|status|draft-quick-quote|
|status|quick-quoting|
|status|quick-quoted|
|status|no-quick-quote|
|status|spot-qq-requested|
|status|pickup-request|
|status|rejected|
|billing_option|prepaid|
|billing_option|collect|
|billing_option|thirdparty|
|declared_value_currency|cad|
|declared_value_currency|usd|
|dim_type|ltl|
|dim_type|ftl|
|dim_type|volume|
|measurement_unit|inch|
|measurement_unit|cm|
|weight_unit|lb|
|weight_unit|kg|
|commodity_type|skid|
|commodity_type|other|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: orders )
</aside>

## createBookedOrder

<a id="opIdcreateBookedOrder"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/customers/{customerID}/create_booked_order \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');
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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
  },
  "billing_option": "prepaid",
  "notes": "string",
  "po_num": "string",
  "tender_num": "string",
  "ref_num": "string",
  "custom_broker": "string",
  "declared_value": 0,
  "declared_value_currency": "cad",
  "pickup_start_at": "2019-02-21T15:32:17Z",
  "pickup_end_at": "2019-02-21T15:32:17Z",
  "pickup_appt_start_at": "2019-02-21T15:32:17Z",
  "pickup_appt_end_at": "2019-02-21T15:32:17Z",
  "delivery_start_at": "2019-02-21T15:32:17Z",
  "delivery_end_at": "2019-02-21T15:32:17Z",
  "delivery_appt_start_at": "2019-02-21T15:32:17Z",
  "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
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
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/customers/{customerID}/create_booked_order", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
  },
  "billing_option": "prepaid",
  "notes": "string",
  "po_num": "string",
  "tender_num": "string",
  "ref_num": "string",
  "custom_broker": "string",
  "declared_value": 0,
  "declared_value_currency": "cad",
  "pickup_start_at": "2019-02-21T15:32:17Z",
  "pickup_end_at": "2019-02-21T15:32:17Z",
  "pickup_appt_start_at": "2019-02-21T15:32:17Z",
  "pickup_appt_end_at": "2019-02-21T15:32:17Z",
  "delivery_start_at": "2019-02-21T15:32:17Z",
  "delivery_end_at": "2019-02-21T15:32:17Z",
  "delivery_appt_start_at": "2019-02-21T15:32:17Z",
  "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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

<h3 id="createbookedorder-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|customerID|path|string(uuid)|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|[Order](#schemaorder)|true|Order object|

> Example responses

> 200 Response

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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "pickup_start_at": "2019-02-21T15:32:17Z",
    "pickup_end_at": "2019-02-21T15:32:17Z",
    "pickup_appt_start_at": "2019-02-21T15:32:17Z",
    "pickup_appt_end_at": "2019-02-21T15:32:17Z",
    "delivery_start_at": "2019-02-21T15:32:17Z",
    "delivery_end_at": "2019-02-21T15:32:17Z",
    "delivery_appt_start_at": "2019-02-21T15:32:17Z",
    "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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
      "origin_start_at": "2019-02-21T15:32:17Z",
      "origin_end_at": "2019-02-21T15:32:17Z",
      "origin_appt_start_at": "2019-02-21T15:32:17Z",
      "origin_appt_end_at": "2019-02-21T15:32:17Z",
      "destination_start_at": "2019-02-21T15:32:17Z",
      "destination_end_at": "2019-02-21T15:32:17Z",
      "destination_appt_start_at": "2019-02-21T15:32:17Z",
      "destination_appt_end_at": "2019-02-21T15:32:17Z",
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
        "origin_arrived_at": "2019-02-21T15:32:17Z",
        "origin_in_at": "2019-02-21T15:32:17Z",
        "origin_pickedup_at": "2019-02-21T15:32:17Z",
        "origin_out_at": "2019-02-21T15:32:17Z",
        "destination_arrived_at": "2019-02-21T15:32:17Z",
        "destination_in_at": "2019-02-21T15:32:17Z",
        "destination_delivered_at": "2019-02-21T15:32:17Z",
        "destination_out_at": "2019-02-21T15:32:17Z"
      }
    }
  ]
}
```

<h3 id="createbookedorder-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="createbookedorder-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» order|[Order](#schemaorder)|false|none|Customer's order|
|»» id|string(uuid)|false|read-only|Auto generated system ID|
|»» sequence_id|integer|false|read-only|Auto generated sequence ID per customer|
|»» external_id|string|false|none|External ID for mapping the order to an external system. This field value can be _null_|
|»» public_id|string|false|read-only|Auto generated human readable ID|
|»» customer|[OrderCustomer](#schemaordercustomer)|false|none|Customer|
|»»» id|string(uuid)|false|read-only|Auto generated customer id|
|»»» external_id|string|false|read-only|Customer external id. This field value can be _null_|
|»»» short_code|string|false|read-only|Customer's short code|
|»» origin|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|»»» address_book_id|string(uuid)|false|read-only|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.|
|»»» address_book_external_id|string(uuid)|false|none|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.|
|»»» org_name|string|false|none|Organization name|
|»»» contact_name|string|false|none|Contact name|
|»»» address_1|string|false|none|Address line 1|
|»»» address_2|string|false|none|Address line 2|
|»»» suite|string|false|none|Suite number|
|»»» city|string|false|none|City|
|»»» state|string|false|none|State / Province|
|»»» country|string|false|none|Country (2 letter ISO)|
|»»» postal|string|false|none|Postal / Zip code|
|»»» phone|string|false|none|Phone number|
|»»» phone_ext|string|false|none|Phone extension|
|»»» email|string|false|none|Email|
|»»» fax|string|false|none|Fax|
|»»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»»» bus_hours_start_at|string(date-time)|false|none|Business hours range (start). This field value can be _null_|
|»»» bus_hours_end_at|string(date-time)|false|none|Business hours range (end). This field value can be _null_|
|»» destination|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|»» billing|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|»» status|string|false|read-only|Order Status|
|»» billing_option|string|false|none|Billing Option|
|»» notes|string|false|none|Notes that will appear on BOL|
|»» po_num|string|false|none|Purchase order numbers (if multiple use comma separated values)|
|»» tender_num|string|false|none|Tender number|
|»» ref_num|string|false|none|Reference number|
|»» custom_broker|string|false|none|Custom broker information|
|»» declared_value|number(float)|false|none|Declared value|
|»» declared_value_currency|string|false|none|Declared value currency|
|»» pickup_start_at|string(date-time)|false|none|Pickup time range (start)|
|»» pickup_end_at|string(date-time)|false|none|Pickup time range (end)|
|»» pickup_appt_start_at|string(date-time)|false|none|Pickup appointment time range (start). This field value can be _null_|
|»» pickup_appt_end_at|string(date-time)|false|none|Pickup appointment time range (end). This field value can be _null_|
|»» delivery_start_at|string(date-time)|false|none|Expected delivery time range (start). This field value can be _null_|
|»» delivery_end_at|string(date-time)|false|none|Expected delivery time range (end). This field value can be _null_|
|»» delivery_appt_start_at|string(date-time)|false|none|Delivery appointment time range (start). This field value can be _null_|
|»» delivery_appt_end_at|string(date-time)|false|none|Delivery appointment time range (end). This field value can be _null_|
|»» dim_type|string|false|none|Dimension type|
|»» commodities|[[Commodity](#schemacommodity)]|false|none|Commodities items|
|»»» id|string(uuid)|false|read-only|Auto generated commodity id|
|»»» measurement_unit|string|false|none|Measurement unit|
|»»» weight_unit|string|false|none|Weight unit|
|»»» freight_class|string|false|none|Freight class|
|»»» commodity_type|string|false|none|Commodity type|
|»»» commodity_type_other|string|false|none|If commodity type is set to _other_, then this field must have value|
|»»» description|string|false|none|Description of the commodity|
|»»» feet|number(float)|false|none|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_|
|»»» volume|number(float)|false|none|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_|
|»»» length|number(float)|false|none|Length of the commodity|
|»»» width|number(float)|false|none|Width of the commodity|
|»»» height|number(float)|false|none|Height of the commodity|
|»»» weight|number(float)|false|none|Weight of the commodity|
|»»» nmfc|string|false|none|NMFC number|
|»»» is_stackable|boolean|false|none|Is this commodity can be stacked?|
|»»» quantity|integer|false|none|Quantity of the commodity|
|»»» pieces|integer|false|none|Total number of pieces. This field value can be _null_|
|»»» sku|string|false|none|SKU number|
|»» accessorials|[string]|false|none|none|
|» legs|[[Leg](#schemaleg)]|false|none|[Leg]|
|»» id|string(uuid)|false|read-only|Auto generated system ID|
|»» sequence_id|integer|false|read-only|Auto generated sequence ID per customer|
|»» version|integer|false|read-only|Auto generated version number (incremental)|
|»» external_id|string|false|none|External ID for mapping the leg to an external system. This field value can be _null_|
|»» public_id|string|false|read-only|Auto generated human readable ID|
|»» order_id|string|false|read-only|Related order ID|
|»» manifest_id|string|false|none|Related manifest ID (assigned). This field value can be _null_|
|»» origin_stop_id|string|false|read-only|Stop ID of the origin (only if this leg has been assigned to a manifest). This field value can be _null_|
|»» destination_stop_id|string|false|read-only|Stop ID of the destination (only if this leg has been assigned to a manifest). This field value can be _null_|
|»» origin|[LegAddress](#schemalegaddress)|false|none|Leg address|
|»»» terminal_id|string(uuid)|false|none|Related terminal ID. This field value can be _null_|
|»»» org_name|string|false|none|Organization name|
|»»» contact_name|string|false|none|Contact name|
|»»» address_1|string|false|none|Address line 1|
|»»» address_2|string|false|none|Address line 2|
|»»» suite|string|false|none|Suite number|
|»»» city|string|false|none|City|
|»»» state|string|false|none|State / Province|
|»»» country|string|false|none|Country (2 letter ISO)|
|»»» postal|string|false|none|Postal / Zip code|
|»»» phone|string|false|none|Phone number|
|»»» phone_ext|string|false|none|Phone extension|
|»»» email|string|false|none|Email|
|»»» fax|string|false|none|Fax|
|»»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» destination|[LegAddress](#schemalegaddress)|false|none|Leg address|
|»» status|string|false|read-only|Leg Status|
|»» origin_start_at|string(date-time)|false|none|Origin ready time range (start)|
|»» origin_end_at|string(date-time)|false|none|Origin ready time range (end)|
|»» origin_appt_start_at|string(date-time)|false|none|Origin appointment time range (start). This field value can be _null_|
|»» origin_appt_end_at|string(date-time)|false|none|Origin appointment time range (end). This field value can be _null_|
|»» destination_start_at|string(date-time)|false|none|Destination expected time range (start). This field value can be _null_|
|»» destination_end_at|string(date-time)|false|none|Destination expected time range (end). This field value can be _null_|
|»» destination_appt_start_at|string(date-time)|false|none|Destination appointment time range (start). This field value can be _null_|
|»» destination_appt_end_at|string(date-time)|false|none|Destination appointment time range (end). This field value can be _null_|
|»» commodities|[[Commodity](#schemacommodity)]|false|none|Commodities items|
|»» accessorials|[string]|false|none|none|
|»» history|[LegHistory](#schemaleghistory)|false|read-only|Historical timestamps of a leg|
|»»» origin_arrived_at|string(date-time)|false|none|The timestamp of when the driver/partner arrived at origin|
|»»» origin_in_at|string(date-time)|false|none|The timestamp of when the driver/partner in at origin|
|»»» origin_pickedup_at|string(date-time)|false|none|The timestamp of when the driver/partner picked up at origin|
|»»» origin_out_at|string(date-time)|false|none|The timestamp of when the driver/partner out at origin|
|»»» destination_arrived_at|string(date-time)|false|none|The timestamp of when the driver/partner arrived at destination|
|»»» destination_in_at|string(date-time)|false|none|The timestamp of when the driver/partner in at destination|
|»»» destination_delivered_at|string(date-time)|false|none|The timestamp of when the driver/partner delievered up at destination|
|»»» destination_out_at|string(date-time)|false|none|The timestamp of when the driver/partner out at destination|

#### Enumerated Values

|Property|Value|
|---|---|
|status|new|
|status|saved|
|status|cancelled|
|status|quoting|
|status|quoted|
|status|no-quote|
|status|spot-quote-requested|
|status|pending-dispatch|
|status|dispatched|
|status|in-transit|
|status|delivered|
|status|archived|
|status|invoice-created|
|status|invoice-sent|
|status|invoice-paid|
|status|claim|
|status|draft-quick-quote|
|status|quick-quoting|
|status|quick-quoted|
|status|no-quick-quote|
|status|spot-qq-requested|
|status|pickup-request|
|status|rejected|
|billing_option|prepaid|
|billing_option|collect|
|billing_option|thirdparty|
|declared_value_currency|cad|
|declared_value_currency|usd|
|dim_type|ltl|
|dim_type|ftl|
|dim_type|volume|
|measurement_unit|inch|
|measurement_unit|cm|
|weight_unit|lb|
|weight_unit|kg|
|commodity_type|skid|
|commodity_type|other|
|status|available|
|status|pending|
|status|dispatched|
|status|arrived_origin|
|status|in_origin|
|status|loaded|
|status|departed_origin|
|status|arrived_destination|
|status|in_destination|
|status|unloaded|
|status|departed_destination|
|status|cancelled|
|status|problem|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: orders )
</aside>

## getOrderByRRID

<a id="opIdgetOrderByRRID"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/orders/{orderID} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://platform.roserocket.com/v1/orders/{orderID} HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/orders/{orderID}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://platform.roserocket.com/v1/orders/{orderID}',
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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://platform.roserocket.com/v1/orders/{orderID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://platform.roserocket.com/v1/orders/{orderID}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://platform.roserocket.com/v1/orders/{orderID}");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://platform.roserocket.com/v1/orders/{orderID}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /orders/{orderID}`

*Get order by Rose Rocket order ID*

<h3 id="getorderbyrrid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|orderID|path|string|true|ID of the order. Must be the Rose Rocket ID of the order.|

> Example responses

> 200 Response

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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "pickup_start_at": "2019-02-21T15:32:17Z",
    "pickup_end_at": "2019-02-21T15:32:17Z",
    "pickup_appt_start_at": "2019-02-21T15:32:17Z",
    "pickup_appt_end_at": "2019-02-21T15:32:17Z",
    "delivery_start_at": "2019-02-21T15:32:17Z",
    "delivery_end_at": "2019-02-21T15:32:17Z",
    "delivery_appt_start_at": "2019-02-21T15:32:17Z",
    "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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

<h3 id="getorderbyrrid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="getorderbyrrid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» order|[Order](#schemaorder)|false|none|Customer's order|
|»» id|string(uuid)|false|read-only|Auto generated system ID|
|»» sequence_id|integer|false|read-only|Auto generated sequence ID per customer|
|»» external_id|string|false|none|External ID for mapping the order to an external system. This field value can be _null_|
|»» public_id|string|false|read-only|Auto generated human readable ID|
|»» customer|[OrderCustomer](#schemaordercustomer)|false|none|Customer|
|»»» id|string(uuid)|false|read-only|Auto generated customer id|
|»»» external_id|string|false|read-only|Customer external id. This field value can be _null_|
|»»» short_code|string|false|read-only|Customer's short code|
|»» origin|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|»»» address_book_id|string(uuid)|false|read-only|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.|
|»»» address_book_external_id|string(uuid)|false|none|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.|
|»»» org_name|string|false|none|Organization name|
|»»» contact_name|string|false|none|Contact name|
|»»» address_1|string|false|none|Address line 1|
|»»» address_2|string|false|none|Address line 2|
|»»» suite|string|false|none|Suite number|
|»»» city|string|false|none|City|
|»»» state|string|false|none|State / Province|
|»»» country|string|false|none|Country (2 letter ISO)|
|»»» postal|string|false|none|Postal / Zip code|
|»»» phone|string|false|none|Phone number|
|»»» phone_ext|string|false|none|Phone extension|
|»»» email|string|false|none|Email|
|»»» fax|string|false|none|Fax|
|»»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»»» bus_hours_start_at|string(date-time)|false|none|Business hours range (start). This field value can be _null_|
|»»» bus_hours_end_at|string(date-time)|false|none|Business hours range (end). This field value can be _null_|
|»» destination|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|»» billing|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|»» status|string|false|read-only|Order Status|
|»» billing_option|string|false|none|Billing Option|
|»» notes|string|false|none|Notes that will appear on BOL|
|»» po_num|string|false|none|Purchase order numbers (if multiple use comma separated values)|
|»» tender_num|string|false|none|Tender number|
|»» ref_num|string|false|none|Reference number|
|»» custom_broker|string|false|none|Custom broker information|
|»» declared_value|number(float)|false|none|Declared value|
|»» declared_value_currency|string|false|none|Declared value currency|
|»» pickup_start_at|string(date-time)|false|none|Pickup time range (start)|
|»» pickup_end_at|string(date-time)|false|none|Pickup time range (end)|
|»» pickup_appt_start_at|string(date-time)|false|none|Pickup appointment time range (start). This field value can be _null_|
|»» pickup_appt_end_at|string(date-time)|false|none|Pickup appointment time range (end). This field value can be _null_|
|»» delivery_start_at|string(date-time)|false|none|Expected delivery time range (start). This field value can be _null_|
|»» delivery_end_at|string(date-time)|false|none|Expected delivery time range (end). This field value can be _null_|
|»» delivery_appt_start_at|string(date-time)|false|none|Delivery appointment time range (start). This field value can be _null_|
|»» delivery_appt_end_at|string(date-time)|false|none|Delivery appointment time range (end). This field value can be _null_|
|»» dim_type|string|false|none|Dimension type|
|»» commodities|[[Commodity](#schemacommodity)]|false|none|Commodities items|
|»»» id|string(uuid)|false|read-only|Auto generated commodity id|
|»»» measurement_unit|string|false|none|Measurement unit|
|»»» weight_unit|string|false|none|Weight unit|
|»»» freight_class|string|false|none|Freight class|
|»»» commodity_type|string|false|none|Commodity type|
|»»» commodity_type_other|string|false|none|If commodity type is set to _other_, then this field must have value|
|»»» description|string|false|none|Description of the commodity|
|»»» feet|number(float)|false|none|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_|
|»»» volume|number(float)|false|none|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_|
|»»» length|number(float)|false|none|Length of the commodity|
|»»» width|number(float)|false|none|Width of the commodity|
|»»» height|number(float)|false|none|Height of the commodity|
|»»» weight|number(float)|false|none|Weight of the commodity|
|»»» nmfc|string|false|none|NMFC number|
|»»» is_stackable|boolean|false|none|Is this commodity can be stacked?|
|»»» quantity|integer|false|none|Quantity of the commodity|
|»»» pieces|integer|false|none|Total number of pieces. This field value can be _null_|
|»»» sku|string|false|none|SKU number|
|»» accessorials|[string]|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|new|
|status|saved|
|status|cancelled|
|status|quoting|
|status|quoted|
|status|no-quote|
|status|spot-quote-requested|
|status|pending-dispatch|
|status|dispatched|
|status|in-transit|
|status|delivered|
|status|archived|
|status|invoice-created|
|status|invoice-sent|
|status|invoice-paid|
|status|claim|
|status|draft-quick-quote|
|status|quick-quoting|
|status|quick-quoted|
|status|no-quick-quote|
|status|spot-qq-requested|
|status|pickup-request|
|status|rejected|
|billing_option|prepaid|
|billing_option|collect|
|billing_option|thirdparty|
|declared_value_currency|cad|
|declared_value_currency|usd|
|dim_type|ltl|
|dim_type|ftl|
|dim_type|volume|
|measurement_unit|inch|
|measurement_unit|cm|
|weight_unit|lb|
|weight_unit|kg|
|commodity_type|skid|
|commodity_type|other|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: orders )
</aside>

## getOrderFilesById

<a id="opIdgetOrderFilesById"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /customers/{customerID}/orders/{orderID}/files`

*Get all leg files/documents for a given ID of a leg*

<h3 id="getorderfilesbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|orderID|path|string|true|ID of the order to get files for. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|
|customerID|path|string|true|ID of the customer to of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|

> Example responses

> 200 Response

```json
{
  "leg_files": [
    {
      "id": "string",
      "created_at": "2019-02-21T15:32:17Z",
      "updated_at": "2019-02-21T15:32:17Z",
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

<h3 id="getorderfilesbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="getorderfilesbyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» leg_files|[[OrderFile](#schemaorderfile)]|false|none|[The file for the order]|
|»» id|string(uuid)|false|none|The uuid for the order file|
|»» created_at|string(date-time)|false|none|The timestamp for the creation of the order file|
|»» updated_at|string(date-time)|false|none|The timestamp for the last update of the order file|
|»» org_id|string(uuid)|false|none|The uuid for the organization of the order file|
|»» leg_id|string(uuid)|false|none|The uuid of the order corresponding to the order file|
|»» uploaded_by|string(uuid)|false|none|The uuid of the user who uploaded the order file|
|»» uploaded_at|string(uuid)|false|none|The uuid|
|»» type|string|false|none|The type of order file|
|»» url|string|false|none|The url location for the order file|
|»» description|string|false|none|A description of the order file|
|»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» metadata|object|false|none|Metadata object for the order file|

#### Enumerated Values

|Property|Value|
|---|---|
|type|other|
|type|comm-invoice|
|type|pod|
|type|pop|
|type|pod-sig|
|type|pop-sig|
|type|carrier-invoice|
|type|smc|
|type|bol|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: legs )
</aside>

## addOrderFileByLegId

<a id="opIdaddOrderFileByLegId"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');
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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
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
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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

<h3 id="addorderfilebylegid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|orderID|path|string|true|ID of the order to get files for. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|
|customerID|path|string|true|ID of the customer to of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|[OrderFileRequest](#schemaorderfilerequest)|true|Order file create request|

> Example responses

> 200 Response

```json
{
  "leg_file": {
    "id": "string",
    "created_at": "2019-02-21T15:32:17Z",
    "updated_at": "2019-02-21T15:32:17Z",
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

<h3 id="addorderfilebylegid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="addorderfilebylegid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» leg_file|[OrderFile](#schemaorderfile)|false|none|The file for the order|
|»» id|string(uuid)|false|none|The uuid for the order file|
|»» created_at|string(date-time)|false|none|The timestamp for the creation of the order file|
|»» updated_at|string(date-time)|false|none|The timestamp for the last update of the order file|
|»» org_id|string(uuid)|false|none|The uuid for the organization of the order file|
|»» leg_id|string(uuid)|false|none|The uuid of the order corresponding to the order file|
|»» uploaded_by|string(uuid)|false|none|The uuid of the user who uploaded the order file|
|»» uploaded_at|string(uuid)|false|none|The uuid|
|»» type|string|false|none|The type of order file|
|»» url|string|false|none|The url location for the order file|
|»» description|string|false|none|A description of the order file|
|»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» metadata|object|false|none|Metadata object for the order file|

#### Enumerated Values

|Property|Value|
|---|---|
|type|other|
|type|comm-invoice|
|type|pod|
|type|pop|
|type|pod-sig|
|type|pop-sig|
|type|carrier-invoice|
|type|smc|
|type|bol|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: legs )
</aside>

## updateFileByOrderAndFileID

<a id="opIdupdateFileByOrderAndFileID"></a>

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
const fetch = require('node-fetch');
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"multipart/form-data"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files/{fileID}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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

<h3 id="updatefilebyorderandfileid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|orderID|path|string|true|ID of the order to get files for. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|
|fileID|path|string|true|ID of the order file.|
|customerID|path|string|true|ID of the customer to of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|[OrderFileRequest](#schemaorderfilerequest)|true|Order file create request|

> Example responses

> 200 Response

```json
{
  "leg_file": {
    "id": "string",
    "created_at": "2019-02-21T15:32:17Z",
    "updated_at": "2019-02-21T15:32:17Z",
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

<h3 id="updatefilebyorderandfileid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="updatefilebyorderandfileid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» leg_file|[OrderFile](#schemaorderfile)|false|none|The file for the order|
|»» id|string(uuid)|false|none|The uuid for the order file|
|»» created_at|string(date-time)|false|none|The timestamp for the creation of the order file|
|»» updated_at|string(date-time)|false|none|The timestamp for the last update of the order file|
|»» org_id|string(uuid)|false|none|The uuid for the organization of the order file|
|»» leg_id|string(uuid)|false|none|The uuid of the order corresponding to the order file|
|»» uploaded_by|string(uuid)|false|none|The uuid of the user who uploaded the order file|
|»» uploaded_at|string(uuid)|false|none|The uuid|
|»» type|string|false|none|The type of order file|
|»» url|string|false|none|The url location for the order file|
|»» description|string|false|none|A description of the order file|
|»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» metadata|object|false|none|Metadata object for the order file|

#### Enumerated Values

|Property|Value|
|---|---|
|type|other|
|type|comm-invoice|
|type|pod|
|type|pop|
|type|pod-sig|
|type|pop-sig|
|type|carrier-invoice|
|type|smc|
|type|bol|

<aside class="success">
This operation does not require authentication
</aside>

## deleteFileByOrderAndFileID

<a id="opIddeleteFileByOrderAndFileID"></a>

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
const fetch = require('node-fetch');

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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/files/{fileID}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /customers/{customerID}/orders/{orderID}/files/{fileID}`

*Delete a file for a specified order*

<h3 id="deletefilebyorderandfileid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|orderID|path|string|true|ID of the order to get files for. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|
|fileID|path|string|true|ID of the order file.|
|customerID|path|string|true|ID of the customer to of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|

> Example responses

> 200 Response

```json
{
  "Message": "Success"
}
```

<h3 id="deletefilebyorderandfileid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="deletefilebyorderandfileid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» Message|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|Message|Success|
|Message|Failure|

<aside class="success">
This operation does not require authentication
</aside>

## uploadOrderBOL

<a id="opIduploadOrderBOL"></a>

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
const fetch = require('node-fetch');
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"multipart/form-data"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/upload_bol", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /customers/{customerID}/orders/{orderID}/upload_bol`

*Upload BOL for a specified order*

> Body parameter

```yaml
file: string

```

<h3 id="uploadorderbol-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|orderID|path|string|true|ID of the order to get files for. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|
|customerID|path|string|true|ID of the customer to of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|[uploadLegBOLByLegID](#schemauploadlegbolbylegid)|false|none|
|» file|body|string(binary)|true|File to upload|

> Example responses

> 200 Response

```json
{
  "order_file": {
    "id": "string",
    "created_at": "2019-02-21T15:32:17Z",
    "updated_at": "2019-02-21T15:32:17Z",
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

<h3 id="uploadorderbol-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="uploadorderbol-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» order_file|[OrderFile](#schemaorderfile)|false|none|The file for the order|
|»» id|string(uuid)|false|none|The uuid for the order file|
|»» created_at|string(date-time)|false|none|The timestamp for the creation of the order file|
|»» updated_at|string(date-time)|false|none|The timestamp for the last update of the order file|
|»» org_id|string(uuid)|false|none|The uuid for the organization of the order file|
|»» leg_id|string(uuid)|false|none|The uuid of the order corresponding to the order file|
|»» uploaded_by|string(uuid)|false|none|The uuid of the user who uploaded the order file|
|»» uploaded_at|string(uuid)|false|none|The uuid|
|»» type|string|false|none|The type of order file|
|»» url|string|false|none|The url location for the order file|
|»» description|string|false|none|A description of the order file|
|»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» metadata|object|false|none|Metadata object for the order file|

#### Enumerated Values

|Property|Value|
|---|---|
|type|other|
|type|comm-invoice|
|type|pod|
|type|pop|
|type|pod-sig|
|type|pop-sig|
|type|carrier-invoice|
|type|smc|
|type|bol|

<aside class="success">
This operation does not require authentication
</aside>

## uploadOrderFile

<a id="opIduploadOrderFile"></a>

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
const fetch = require('node-fetch');
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"multipart/form-data"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/upload_file", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /customers/{customerID}/orders/{orderID}/upload_file`

*Upload file for a specified order*

> Body parameter

```yaml
file: string
type: other

```

<h3 id="uploadorderfile-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|orderID|path|string|true|ID of the order to get files for. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|
|customerID|path|string|true|ID of the customer to of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|[uploadOrderFile](#schemauploadorderfile)|false|none|
|» file|body|string(binary)|true|File to upload|
|» type|body|string|true|Type of order file to upload|

#### Enumerated Values

|Parameter|Value|
|---|---|
|» type|other|
|» type|comm-invoice|
|» type|pod|
|» type|pop|
|» type|pod-sig|
|» type|pop-sig|
|» type|carrier-invoice|
|» type|smc|
|» type|bol|

> Example responses

> 200 Response

```json
{
  "order_file": {
    "id": "string",
    "created_at": "2019-02-21T15:32:17Z",
    "updated_at": "2019-02-21T15:32:17Z",
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

<h3 id="uploadorderfile-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="uploadorderfile-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» order_file|[OrderFile](#schemaorderfile)|false|none|The file for the order|
|»» id|string(uuid)|false|none|The uuid for the order file|
|»» created_at|string(date-time)|false|none|The timestamp for the creation of the order file|
|»» updated_at|string(date-time)|false|none|The timestamp for the last update of the order file|
|»» org_id|string(uuid)|false|none|The uuid for the organization of the order file|
|»» leg_id|string(uuid)|false|none|The uuid of the order corresponding to the order file|
|»» uploaded_by|string(uuid)|false|none|The uuid of the user who uploaded the order file|
|»» uploaded_at|string(uuid)|false|none|The uuid|
|»» type|string|false|none|The type of order file|
|»» url|string|false|none|The url location for the order file|
|»» description|string|false|none|A description of the order file|
|»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» metadata|object|false|none|Metadata object for the order file|

#### Enumerated Values

|Property|Value|
|---|---|
|type|other|
|type|comm-invoice|
|type|pod|
|type|pop|
|type|pod-sig|
|type|pop-sig|
|type|carrier-invoice|
|type|smc|
|type|bol|

<aside class="success">
This operation does not require authentication
</aside>

## updateOrderFile

<a id="opIdupdateOrderFile"></a>

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
const fetch = require('node-fetch');
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"multipart/form-data"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/upload_file/{fileID}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /customers/{customerID}/orders/{orderID}/upload_file/{fileID}`

*Update an uploaded file for a specified order*

> Body parameter

```yaml
file: string
type: other

```

<h3 id="updateorderfile-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|orderID|path|string|true|ID of the order to get files for. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|
|fileID|path|string|true|ID of the order file.|
|customerID|path|string|true|ID of the customer to of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|[uploadOrderFile](#schemauploadorderfile)|false|none|
|» file|body|string(binary)|true|File to upload|
|» type|body|string|true|Type of order file to upload|

#### Enumerated Values

|Parameter|Value|
|---|---|
|» type|other|
|» type|comm-invoice|
|» type|pod|
|» type|pop|
|» type|pod-sig|
|» type|pop-sig|
|» type|carrier-invoice|
|» type|smc|
|» type|bol|

> Example responses

> 200 Response

```json
{
  "order_file": {
    "id": "string",
    "created_at": "2019-02-21T15:32:17Z",
    "updated_at": "2019-02-21T15:32:17Z",
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

<h3 id="updateorderfile-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="updateorderfile-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» order_file|[OrderFile](#schemaorderfile)|false|none|The file for the order|
|»» id|string(uuid)|false|none|The uuid for the order file|
|»» created_at|string(date-time)|false|none|The timestamp for the creation of the order file|
|»» updated_at|string(date-time)|false|none|The timestamp for the last update of the order file|
|»» org_id|string(uuid)|false|none|The uuid for the organization of the order file|
|»» leg_id|string(uuid)|false|none|The uuid of the order corresponding to the order file|
|»» uploaded_by|string(uuid)|false|none|The uuid of the user who uploaded the order file|
|»» uploaded_at|string(uuid)|false|none|The uuid|
|»» type|string|false|none|The type of order file|
|»» url|string|false|none|The url location for the order file|
|»» description|string|false|none|A description of the order file|
|»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» metadata|object|false|none|Metadata object for the order file|

#### Enumerated Values

|Property|Value|
|---|---|
|type|other|
|type|comm-invoice|
|type|pod|
|type|pop|
|type|pod-sig|
|type|pop-sig|
|type|carrier-invoice|
|type|smc|
|type|bol|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="rose-rocket-platform-rest-api-quote">quote</h1>

Manage quotes

## createOrderSpotQuote

<a id="opIdcreateOrderSpotQuote"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/spot_quote \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');
const inputBody = '{
  "notes": "string",
  "est_delivery_start_at": "2019-02-21T15:32:17Z",
  "est_delivery_end_at": "2019-02-21T15:32:17Z",
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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
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
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/spot_quote", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /customers/{customerID}/orders/{orderID}/spot_quote`

*Create a spot quote for a customer's order*

> Body parameter

```json
{
  "notes": "string",
  "est_delivery_start_at": "2019-02-21T15:32:17Z",
  "est_delivery_end_at": "2019-02-21T15:32:17Z",
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

<h3 id="createorderspotquote-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.|
|orderID|path|string(uuid)|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|[SpotQuote](#schemaspotquote)|true|Order object|

> Example responses

> 200 Response

```json
{
  "quote": {
    "id": "string",
    "order_id": "string",
    "currency": "cad",
    "customer_service_id": "string",
    "is_expired": true,
    "pickup_start_at": "2019-02-21T15:32:17Z",
    "pickup_end_at": "2019-02-21T15:32:17Z",
    "est_delivery_start_at": "2019-02-21T15:32:17Z",
    "est_delivery_end_at": "2019-02-21T15:32:17Z",
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

<h3 id="createorderspotquote-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="createorderspotquote-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» quote|[Quote](#schemaquote)|false|read-only|Quote|
|»» id|string(uuid)|false|read-only|Auto generated quote id|
|»» order_id|string(uuid)|false|none|Order id this quote is associated to|
|»» currency|string|false|none|Declared value currency|
|»» customer_service_id|string(uuid)|false|none|Customer's service of this quote generated from|
|»» is_expired|boolean|false|none|Is this quote has expired?|
|»» pickup_start_at|string(date-time)|false|none|Pickup time range (start)|
|»» pickup_end_at|string(date-time)|false|none|Pickup time range (end)|
|»» est_delivery_start_at|string(date-time)|false|none|Estimated delivery time range (start). This field value can be _null_|
|»» est_delivery_end_at|string(date-time)|false|none|Estimated delivery time range (end). This field value can be _null_|
|»» notes|string|false|none|Notes|
|»» error_message|string|false|none|Error message|
|»» status|string|false|none|Status|
|»» charges|object|false|none|none|
|»»» type|string(uuid)|false|none|Type|
|»»» quote_id|string(uuid)|false|read-only|Quote id this item is associated to|
|»»» description|string|false|none|Description|
|»»» quantity|integer|false|none|Unit quantity|
|»»» unit_price|integer|false|none|Unit price|
|»»» total|integer|false|none|Total|
|»» freight|number(float)|false|none|Freight charge|
|»» fuel|number(float)|false|none|Fuel charge|
|»» accessorials|number(float)|false|none|Accessorials charge|
|»» total|number(float)|false|none|Total charge|

#### Enumerated Values

|Property|Value|
|---|---|
|currency|cad|
|currency|usd|
|status|quote-success|
|status|quote-pending|
|status|quote-rejected|
|status|quote-error|
|status|dispatch-success|
|status|dispatch-pending|
|status|dispatch-rejected|
|status|dispatch-error|
|type|freight|
|type|freight-cwt|
|type|freight-cwt-min|
|type|freight-spot|
|type|freight-pallets|
|type|freight-pallets-min|
|type|accessorial|
|type|fuel|
|type|misc|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: orders )
</aside>

## generateOrderQuotes

<a id="opIdgenerateOrderQuotes"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/quotes \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/quotes HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/quotes',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/quotes", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /customers/{customerID}/orders/{orderID}/quotes`

*Generate new quotes for a customer's order*

<h3 id="generateorderquotes-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.|
|orderID|path|string(uuid)|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|

> Example responses

> 200 Response

```json
{
  "quotes": [
    {
      "id": "string",
      "order_id": "string",
      "currency": "cad",
      "customer_service_id": "string",
      "is_expired": true,
      "pickup_start_at": "2019-02-21T15:32:17Z",
      "pickup_end_at": "2019-02-21T15:32:17Z",
      "est_delivery_start_at": "2019-02-21T15:32:17Z",
      "est_delivery_end_at": "2019-02-21T15:32:17Z",
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

<h3 id="generateorderquotes-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="generateorderquotes-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» quotes|[[Quote](#schemaquote)]|false|none|[Quote]|
|»» id|string(uuid)|false|read-only|Auto generated quote id|
|»» order_id|string(uuid)|false|none|Order id this quote is associated to|
|»» currency|string|false|none|Declared value currency|
|»» customer_service_id|string(uuid)|false|none|Customer's service of this quote generated from|
|»» is_expired|boolean|false|none|Is this quote has expired?|
|»» pickup_start_at|string(date-time)|false|none|Pickup time range (start)|
|»» pickup_end_at|string(date-time)|false|none|Pickup time range (end)|
|»» est_delivery_start_at|string(date-time)|false|none|Estimated delivery time range (start). This field value can be _null_|
|»» est_delivery_end_at|string(date-time)|false|none|Estimated delivery time range (end). This field value can be _null_|
|»» notes|string|false|none|Notes|
|»» error_message|string|false|none|Error message|
|»» status|string|false|none|Status|
|»» charges|object|false|none|none|
|»»» type|string(uuid)|false|none|Type|
|»»» quote_id|string(uuid)|false|read-only|Quote id this item is associated to|
|»»» description|string|false|none|Description|
|»»» quantity|integer|false|none|Unit quantity|
|»»» unit_price|integer|false|none|Unit price|
|»»» total|integer|false|none|Total|
|»» freight|number(float)|false|none|Freight charge|
|»» fuel|number(float)|false|none|Fuel charge|
|»» accessorials|number(float)|false|none|Accessorials charge|
|»» total|number(float)|false|none|Total charge|
|» offset|integer|false|none|none|
|» limit|integer|false|none|none|
|» total|integer|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|currency|cad|
|currency|usd|
|status|quote-success|
|status|quote-pending|
|status|quote-rejected|
|status|quote-error|
|status|dispatch-success|
|status|dispatch-pending|
|status|dispatch-rejected|
|status|dispatch-error|
|type|freight|
|type|freight-cwt|
|type|freight-cwt-min|
|type|freight-spot|
|type|freight-pallets|
|type|freight-pallets-min|
|type|accessorial|
|type|fuel|
|type|misc|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: orders )
</aside>

## getOrderQuotes

<a id="opIdgetOrderQuotes"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/quotes \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/quotes HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/quotes',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://platform.roserocket.com/v1/customers/{customerID}/orders/{orderID}/quotes", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /customers/{customerID}/orders/{orderID}/quotes`

*Get existing quotes for a customer's order*

<h3 id="getorderquotes-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.|
|orderID|path|string(uuid)|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|

> Example responses

> 200 Response

```json
{
  "quotes": [
    {
      "id": "string",
      "order_id": "string",
      "currency": "cad",
      "customer_service_id": "string",
      "is_expired": true,
      "pickup_start_at": "2019-02-21T15:32:17Z",
      "pickup_end_at": "2019-02-21T15:32:17Z",
      "est_delivery_start_at": "2019-02-21T15:32:17Z",
      "est_delivery_end_at": "2019-02-21T15:32:17Z",
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

<h3 id="getorderquotes-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="getorderquotes-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» quotes|[[Quote](#schemaquote)]|false|none|[Quote]|
|»» id|string(uuid)|false|read-only|Auto generated quote id|
|»» order_id|string(uuid)|false|none|Order id this quote is associated to|
|»» currency|string|false|none|Declared value currency|
|»» customer_service_id|string(uuid)|false|none|Customer's service of this quote generated from|
|»» is_expired|boolean|false|none|Is this quote has expired?|
|»» pickup_start_at|string(date-time)|false|none|Pickup time range (start)|
|»» pickup_end_at|string(date-time)|false|none|Pickup time range (end)|
|»» est_delivery_start_at|string(date-time)|false|none|Estimated delivery time range (start). This field value can be _null_|
|»» est_delivery_end_at|string(date-time)|false|none|Estimated delivery time range (end). This field value can be _null_|
|»» notes|string|false|none|Notes|
|»» error_message|string|false|none|Error message|
|»» status|string|false|none|Status|
|»» charges|object|false|none|none|
|»»» type|string(uuid)|false|none|Type|
|»»» quote_id|string(uuid)|false|read-only|Quote id this item is associated to|
|»»» description|string|false|none|Description|
|»»» quantity|integer|false|none|Unit quantity|
|»»» unit_price|integer|false|none|Unit price|
|»»» total|integer|false|none|Total|
|»» freight|number(float)|false|none|Freight charge|
|»» fuel|number(float)|false|none|Fuel charge|
|»» accessorials|number(float)|false|none|Accessorials charge|
|»» total|number(float)|false|none|Total charge|
|» offset|integer|false|none|none|
|» limit|integer|false|none|none|
|» total|integer|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|currency|cad|
|currency|usd|
|status|quote-success|
|status|quote-pending|
|status|quote-rejected|
|status|quote-error|
|status|dispatch-success|
|status|dispatch-pending|
|status|dispatch-rejected|
|status|dispatch-error|
|type|freight|
|type|freight-cwt|
|type|freight-cwt-min|
|type|freight-spot|
|type|freight-pallets|
|type|freight-pallets-min|
|type|accessorial|
|type|fuel|
|type|misc|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: orders )
</aside>

<h1 id="rose-rocket-platform-rest-api-customer">customer</h1>

Manage customers

## searchCustomers

<a id="opIdsearchCustomers"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/customers \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://platform.roserocket.com/v1/customers HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://platform.roserocket.com/v1/customers',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://platform.roserocket.com/v1/customers", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /customers`

*Search customers*

<h3 id="searchcustomers-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|search_term|query|string|false|Search term|
|external_id|query|string|false|External ID to filter by|
|in_external_ids|query|array[string]|false|External IDs to filter by|
|offset|query|integer|false|Pagination offset|
|limit|query|integer|false|Pagination limit|

> Example responses

> 200 Response

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

<h3 id="searchcustomers-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="searchcustomers-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» customers|[[Customer](#schemacustomer)]|false|none|[Customer]|
|»» id|string(uuid)|false|read-only|Auto generated customner id|
|»» external_id|string|false|read-only|Customer external id. This field value can be _null_|
|»» short_code|string|false|read-only|Customer's short code|
|»» name|string|false|none|Organization name|
|»» address_1|string|false|none|Address line 1|
|»» address_2|string|false|none|Address line 2|
|»» suite|string|false|none|Suite number|
|»» city|string|false|none|City|
|»» state|string|false|none|State / Province|
|»» country|string|false|none|Country (2 letter ISO)|
|»» postal|string|false|none|Postal / Zip code|
|»» phone|string|false|none|Phone number|
|»» phone_ext|string|false|none|Phone extension|
|»» email|string|false|none|Email|
|»» fax|string|false|none|Fax|
|»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» default_billing_option|string|false|none|Billing Option|
|»» default_dim_type|string|false|none|Dimension type|
|»» default_order_notes|string|false|none|This notes will always show up as internal note everytime an order is created for this customer|
|»» currency|string|false|none|Currency used when doing billing/invoicing|
|»» is_active|boolean|false|none|Is customer active?|
|»» credit_limit|number(float)|false|none|Credit limit for this customer|
|»» credit_balance|number(float)|false|none|Credit balance for this customer|
|»» dispatch__contact_name|string|false|none|Dispatch contact name|
|»» dispatch_contact_phone|string|false|none|Dispatch contact phone|
|»» dispatch_contact_email|string|false|none|Dispatch contact email|
|»» billing_contact_name|string|false|none|Billing contact name|
|»» billing_contact_phone|string|false|none|Billing contact phone|
|»» billing_contact_email|string|false|none|Billing contact email|
|»» sales_contact_name|string|false|none|Sales contact name|
|»» sales_contact_phone|string|false|none|Sales contact phone|
|»» sales_contact_email|string|false|none|Sales contact email|
|»» management_contact_name|string|false|none|Management contact name|
|»» management_contact_phone|string|false|none|Management contact phone|
|»» management_contact_email|string|false|none|Management contact email|
|»» other_contact_name|string|false|none|Other contact name|
|»» other_contact_phone|string|false|none|Other contact phone|
|»» other_contact_email|string|false|none|Other contact email|
|» offset|integer|false|none|none|
|» limit|integer|false|none|none|
|» total|integer|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|default_billing_option|prepaid|
|default_billing_option|collect|
|default_billing_option|thirdparty|
|default_dim_type|ltl|
|default_dim_type|ftl|
|default_dim_type|volume|
|currency|cad|
|currency|usd|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: customers )
</aside>

## createCustomer

<a id="opIdcreateCustomer"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/customers \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');
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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
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
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/customers", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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

<h3 id="createcustomer-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Customer](#schemacustomer)|true|Order object|

> Example responses

> 200 Response

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

<h3 id="createcustomer-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="createcustomer-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» customer|[Customer](#schemacustomer)|false|none|Customer|
|»» id|string(uuid)|false|read-only|Auto generated customner id|
|»» external_id|string|false|read-only|Customer external id. This field value can be _null_|
|»» short_code|string|false|read-only|Customer's short code|
|»» name|string|false|none|Organization name|
|»» address_1|string|false|none|Address line 1|
|»» address_2|string|false|none|Address line 2|
|»» suite|string|false|none|Suite number|
|»» city|string|false|none|City|
|»» state|string|false|none|State / Province|
|»» country|string|false|none|Country (2 letter ISO)|
|»» postal|string|false|none|Postal / Zip code|
|»» phone|string|false|none|Phone number|
|»» phone_ext|string|false|none|Phone extension|
|»» email|string|false|none|Email|
|»» fax|string|false|none|Fax|
|»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» default_billing_option|string|false|none|Billing Option|
|»» default_dim_type|string|false|none|Dimension type|
|»» default_order_notes|string|false|none|This notes will always show up as internal note everytime an order is created for this customer|
|»» currency|string|false|none|Currency used when doing billing/invoicing|
|»» is_active|boolean|false|none|Is customer active?|
|»» credit_limit|number(float)|false|none|Credit limit for this customer|
|»» credit_balance|number(float)|false|none|Credit balance for this customer|
|»» dispatch__contact_name|string|false|none|Dispatch contact name|
|»» dispatch_contact_phone|string|false|none|Dispatch contact phone|
|»» dispatch_contact_email|string|false|none|Dispatch contact email|
|»» billing_contact_name|string|false|none|Billing contact name|
|»» billing_contact_phone|string|false|none|Billing contact phone|
|»» billing_contact_email|string|false|none|Billing contact email|
|»» sales_contact_name|string|false|none|Sales contact name|
|»» sales_contact_phone|string|false|none|Sales contact phone|
|»» sales_contact_email|string|false|none|Sales contact email|
|»» management_contact_name|string|false|none|Management contact name|
|»» management_contact_phone|string|false|none|Management contact phone|
|»» management_contact_email|string|false|none|Management contact email|
|»» other_contact_name|string|false|none|Other contact name|
|»» other_contact_phone|string|false|none|Other contact phone|
|»» other_contact_email|string|false|none|Other contact email|

#### Enumerated Values

|Property|Value|
|---|---|
|default_billing_option|prepaid|
|default_billing_option|collect|
|default_billing_option|thirdparty|
|default_dim_type|ltl|
|default_dim_type|ftl|
|default_dim_type|volume|
|currency|cad|
|currency|usd|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: customers )
</aside>

## getCustomerByID

<a id="opIdgetCustomerByID"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/customers/{customerID} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://platform.roserocket.com/v1/customers/{customerID} HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://platform.roserocket.com/v1/customers/{customerID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://platform.roserocket.com/v1/customers/{customerID}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /customers/{customerID}`

*Get customer by ID*

<h3 id="getcustomerbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.|

> Example responses

> 200 Response

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

<h3 id="getcustomerbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="getcustomerbyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» customer|[Customer](#schemacustomer)|false|none|Customer|
|»» id|string(uuid)|false|read-only|Auto generated customner id|
|»» external_id|string|false|read-only|Customer external id. This field value can be _null_|
|»» short_code|string|false|read-only|Customer's short code|
|»» name|string|false|none|Organization name|
|»» address_1|string|false|none|Address line 1|
|»» address_2|string|false|none|Address line 2|
|»» suite|string|false|none|Suite number|
|»» city|string|false|none|City|
|»» state|string|false|none|State / Province|
|»» country|string|false|none|Country (2 letter ISO)|
|»» postal|string|false|none|Postal / Zip code|
|»» phone|string|false|none|Phone number|
|»» phone_ext|string|false|none|Phone extension|
|»» email|string|false|none|Email|
|»» fax|string|false|none|Fax|
|»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» default_billing_option|string|false|none|Billing Option|
|»» default_dim_type|string|false|none|Dimension type|
|»» default_order_notes|string|false|none|This notes will always show up as internal note everytime an order is created for this customer|
|»» currency|string|false|none|Currency used when doing billing/invoicing|
|»» is_active|boolean|false|none|Is customer active?|
|»» credit_limit|number(float)|false|none|Credit limit for this customer|
|»» credit_balance|number(float)|false|none|Credit balance for this customer|
|»» dispatch__contact_name|string|false|none|Dispatch contact name|
|»» dispatch_contact_phone|string|false|none|Dispatch contact phone|
|»» dispatch_contact_email|string|false|none|Dispatch contact email|
|»» billing_contact_name|string|false|none|Billing contact name|
|»» billing_contact_phone|string|false|none|Billing contact phone|
|»» billing_contact_email|string|false|none|Billing contact email|
|»» sales_contact_name|string|false|none|Sales contact name|
|»» sales_contact_phone|string|false|none|Sales contact phone|
|»» sales_contact_email|string|false|none|Sales contact email|
|»» management_contact_name|string|false|none|Management contact name|
|»» management_contact_phone|string|false|none|Management contact phone|
|»» management_contact_email|string|false|none|Management contact email|
|»» other_contact_name|string|false|none|Other contact name|
|»» other_contact_phone|string|false|none|Other contact phone|
|»» other_contact_email|string|false|none|Other contact email|

#### Enumerated Values

|Property|Value|
|---|---|
|default_billing_option|prepaid|
|default_billing_option|collect|
|default_billing_option|thirdparty|
|default_dim_type|ltl|
|default_dim_type|ftl|
|default_dim_type|volume|
|currency|cad|
|currency|usd|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: customers )
</aside>

## updateCustomerByID

<a id="opIdupdateCustomerByID"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/customers/{customerID} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');
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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
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
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://platform.roserocket.com/v1/customers/{customerID}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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

<h3 id="updatecustomerbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|customerID|path|string|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|[Customer](#schemacustomer)|true|Order object|

> Example responses

> 200 Response

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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "pickup_start_at": "2019-02-21T15:32:17Z",
    "pickup_end_at": "2019-02-21T15:32:17Z",
    "pickup_appt_start_at": "2019-02-21T15:32:17Z",
    "pickup_appt_end_at": "2019-02-21T15:32:17Z",
    "delivery_start_at": "2019-02-21T15:32:17Z",
    "delivery_end_at": "2019-02-21T15:32:17Z",
    "delivery_appt_start_at": "2019-02-21T15:32:17Z",
    "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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

<h3 id="updatecustomerbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="updatecustomerbyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» order|[Order](#schemaorder)|false|none|Customer's order|
|»» id|string(uuid)|false|read-only|Auto generated system ID|
|»» sequence_id|integer|false|read-only|Auto generated sequence ID per customer|
|»» external_id|string|false|none|External ID for mapping the order to an external system. This field value can be _null_|
|»» public_id|string|false|read-only|Auto generated human readable ID|
|»» customer|[OrderCustomer](#schemaordercustomer)|false|none|Customer|
|»»» id|string(uuid)|false|read-only|Auto generated customer id|
|»»» external_id|string|false|read-only|Customer external id. This field value can be _null_|
|»»» short_code|string|false|read-only|Customer's short code|
|»» origin|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|»»» address_book_id|string(uuid)|false|read-only|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.|
|»»» address_book_external_id|string(uuid)|false|none|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.|
|»»» org_name|string|false|none|Organization name|
|»»» contact_name|string|false|none|Contact name|
|»»» address_1|string|false|none|Address line 1|
|»»» address_2|string|false|none|Address line 2|
|»»» suite|string|false|none|Suite number|
|»»» city|string|false|none|City|
|»»» state|string|false|none|State / Province|
|»»» country|string|false|none|Country (2 letter ISO)|
|»»» postal|string|false|none|Postal / Zip code|
|»»» phone|string|false|none|Phone number|
|»»» phone_ext|string|false|none|Phone extension|
|»»» email|string|false|none|Email|
|»»» fax|string|false|none|Fax|
|»»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»»» bus_hours_start_at|string(date-time)|false|none|Business hours range (start). This field value can be _null_|
|»»» bus_hours_end_at|string(date-time)|false|none|Business hours range (end). This field value can be _null_|
|»» destination|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|»» billing|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|»» status|string|false|read-only|Order Status|
|»» billing_option|string|false|none|Billing Option|
|»» notes|string|false|none|Notes that will appear on BOL|
|»» po_num|string|false|none|Purchase order numbers (if multiple use comma separated values)|
|»» tender_num|string|false|none|Tender number|
|»» ref_num|string|false|none|Reference number|
|»» custom_broker|string|false|none|Custom broker information|
|»» declared_value|number(float)|false|none|Declared value|
|»» declared_value_currency|string|false|none|Declared value currency|
|»» pickup_start_at|string(date-time)|false|none|Pickup time range (start)|
|»» pickup_end_at|string(date-time)|false|none|Pickup time range (end)|
|»» pickup_appt_start_at|string(date-time)|false|none|Pickup appointment time range (start). This field value can be _null_|
|»» pickup_appt_end_at|string(date-time)|false|none|Pickup appointment time range (end). This field value can be _null_|
|»» delivery_start_at|string(date-time)|false|none|Expected delivery time range (start). This field value can be _null_|
|»» delivery_end_at|string(date-time)|false|none|Expected delivery time range (end). This field value can be _null_|
|»» delivery_appt_start_at|string(date-time)|false|none|Delivery appointment time range (start). This field value can be _null_|
|»» delivery_appt_end_at|string(date-time)|false|none|Delivery appointment time range (end). This field value can be _null_|
|»» dim_type|string|false|none|Dimension type|
|»» commodities|[[Commodity](#schemacommodity)]|false|none|Commodities items|
|»»» id|string(uuid)|false|read-only|Auto generated commodity id|
|»»» measurement_unit|string|false|none|Measurement unit|
|»»» weight_unit|string|false|none|Weight unit|
|»»» freight_class|string|false|none|Freight class|
|»»» commodity_type|string|false|none|Commodity type|
|»»» commodity_type_other|string|false|none|If commodity type is set to _other_, then this field must have value|
|»»» description|string|false|none|Description of the commodity|
|»»» feet|number(float)|false|none|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_|
|»»» volume|number(float)|false|none|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_|
|»»» length|number(float)|false|none|Length of the commodity|
|»»» width|number(float)|false|none|Width of the commodity|
|»»» height|number(float)|false|none|Height of the commodity|
|»»» weight|number(float)|false|none|Weight of the commodity|
|»»» nmfc|string|false|none|NMFC number|
|»»» is_stackable|boolean|false|none|Is this commodity can be stacked?|
|»»» quantity|integer|false|none|Quantity of the commodity|
|»»» pieces|integer|false|none|Total number of pieces. This field value can be _null_|
|»»» sku|string|false|none|SKU number|
|»» accessorials|[string]|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|new|
|status|saved|
|status|cancelled|
|status|quoting|
|status|quoted|
|status|no-quote|
|status|spot-quote-requested|
|status|pending-dispatch|
|status|dispatched|
|status|in-transit|
|status|delivered|
|status|archived|
|status|invoice-created|
|status|invoice-sent|
|status|invoice-paid|
|status|claim|
|status|draft-quick-quote|
|status|quick-quoting|
|status|quick-quoted|
|status|no-quick-quote|
|status|spot-qq-requested|
|status|pickup-request|
|status|rejected|
|billing_option|prepaid|
|billing_option|collect|
|billing_option|thirdparty|
|declared_value_currency|cad|
|declared_value_currency|usd|
|dim_type|ltl|
|dim_type|ftl|
|dim_type|volume|
|measurement_unit|inch|
|measurement_unit|cm|
|weight_unit|lb|
|weight_unit|kg|
|commodity_type|skid|
|commodity_type|other|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: customers )
</aside>

## deleteCustomerByID

<a id="opIddeleteCustomerByID"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE https://platform.roserocket.com/v1/customers/{customerID} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE https://platform.roserocket.com/v1/customers/{customerID} HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete 'https://platform.roserocket.com/v1/customers/{customerID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://platform.roserocket.com/v1/customers/{customerID}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /customers/{customerID}`

*Delete customer by ID*

<h3 id="deletecustomerbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|customerID|path|string(uuid)|true|ID of the customer that creates the order. It could also be the external ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.|

> Example responses

> 200 Response

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

<h3 id="deletecustomerbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="deletecustomerbyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» customer|[Customer](#schemacustomer)|false|none|Customer|
|»» id|string(uuid)|false|read-only|Auto generated customner id|
|»» external_id|string|false|read-only|Customer external id. This field value can be _null_|
|»» short_code|string|false|read-only|Customer's short code|
|»» name|string|false|none|Organization name|
|»» address_1|string|false|none|Address line 1|
|»» address_2|string|false|none|Address line 2|
|»» suite|string|false|none|Suite number|
|»» city|string|false|none|City|
|»» state|string|false|none|State / Province|
|»» country|string|false|none|Country (2 letter ISO)|
|»» postal|string|false|none|Postal / Zip code|
|»» phone|string|false|none|Phone number|
|»» phone_ext|string|false|none|Phone extension|
|»» email|string|false|none|Email|
|»» fax|string|false|none|Fax|
|»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» default_billing_option|string|false|none|Billing Option|
|»» default_dim_type|string|false|none|Dimension type|
|»» default_order_notes|string|false|none|This notes will always show up as internal note everytime an order is created for this customer|
|»» currency|string|false|none|Currency used when doing billing/invoicing|
|»» is_active|boolean|false|none|Is customer active?|
|»» credit_limit|number(float)|false|none|Credit limit for this customer|
|»» credit_balance|number(float)|false|none|Credit balance for this customer|
|»» dispatch__contact_name|string|false|none|Dispatch contact name|
|»» dispatch_contact_phone|string|false|none|Dispatch contact phone|
|»» dispatch_contact_email|string|false|none|Dispatch contact email|
|»» billing_contact_name|string|false|none|Billing contact name|
|»» billing_contact_phone|string|false|none|Billing contact phone|
|»» billing_contact_email|string|false|none|Billing contact email|
|»» sales_contact_name|string|false|none|Sales contact name|
|»» sales_contact_phone|string|false|none|Sales contact phone|
|»» sales_contact_email|string|false|none|Sales contact email|
|»» management_contact_name|string|false|none|Management contact name|
|»» management_contact_phone|string|false|none|Management contact phone|
|»» management_contact_email|string|false|none|Management contact email|
|»» other_contact_name|string|false|none|Other contact name|
|»» other_contact_phone|string|false|none|Other contact phone|
|»» other_contact_email|string|false|none|Other contact email|

#### Enumerated Values

|Property|Value|
|---|---|
|default_billing_option|prepaid|
|default_billing_option|collect|
|default_billing_option|thirdparty|
|default_dim_type|ltl|
|default_dim_type|ftl|
|default_dim_type|volume|
|currency|cad|
|currency|usd|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: customers )
</aside>

## upsertCustomerByID

<a id="opIdupsertCustomerByID"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/customers/{customerExtID}/upsert \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');
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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
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
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://platform.roserocket.com/v1/customers/{customerExtID}/upsert", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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

<h3 id="upsertcustomerbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|customerExtID|path|string|true|External ID of the customer, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the customer's external ID is __test123__ then the value of customerID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|[Customer](#schemacustomer)|true|Order object|

> Example responses

> 200 Response

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

<h3 id="upsertcustomerbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="upsertcustomerbyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» customer|[Customer](#schemacustomer)|false|none|Customer|
|»» id|string(uuid)|false|read-only|Auto generated customner id|
|»» external_id|string|false|read-only|Customer external id. This field value can be _null_|
|»» short_code|string|false|read-only|Customer's short code|
|»» name|string|false|none|Organization name|
|»» address_1|string|false|none|Address line 1|
|»» address_2|string|false|none|Address line 2|
|»» suite|string|false|none|Suite number|
|»» city|string|false|none|City|
|»» state|string|false|none|State / Province|
|»» country|string|false|none|Country (2 letter ISO)|
|»» postal|string|false|none|Postal / Zip code|
|»» phone|string|false|none|Phone number|
|»» phone_ext|string|false|none|Phone extension|
|»» email|string|false|none|Email|
|»» fax|string|false|none|Fax|
|»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» default_billing_option|string|false|none|Billing Option|
|»» default_dim_type|string|false|none|Dimension type|
|»» default_order_notes|string|false|none|This notes will always show up as internal note everytime an order is created for this customer|
|»» currency|string|false|none|Currency used when doing billing/invoicing|
|»» is_active|boolean|false|none|Is customer active?|
|»» credit_limit|number(float)|false|none|Credit limit for this customer|
|»» credit_balance|number(float)|false|none|Credit balance for this customer|
|»» dispatch__contact_name|string|false|none|Dispatch contact name|
|»» dispatch_contact_phone|string|false|none|Dispatch contact phone|
|»» dispatch_contact_email|string|false|none|Dispatch contact email|
|»» billing_contact_name|string|false|none|Billing contact name|
|»» billing_contact_phone|string|false|none|Billing contact phone|
|»» billing_contact_email|string|false|none|Billing contact email|
|»» sales_contact_name|string|false|none|Sales contact name|
|»» sales_contact_phone|string|false|none|Sales contact phone|
|»» sales_contact_email|string|false|none|Sales contact email|
|»» management_contact_name|string|false|none|Management contact name|
|»» management_contact_phone|string|false|none|Management contact phone|
|»» management_contact_email|string|false|none|Management contact email|
|»» other_contact_name|string|false|none|Other contact name|
|»» other_contact_phone|string|false|none|Other contact phone|
|»» other_contact_email|string|false|none|Other contact email|

#### Enumerated Values

|Property|Value|
|---|---|
|default_billing_option|prepaid|
|default_billing_option|collect|
|default_billing_option|thirdparty|
|default_dim_type|ltl|
|default_dim_type|ftl|
|default_dim_type|volume|
|currency|cad|
|currency|usd|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: customers )
</aside>

<h1 id="rose-rocket-platform-rest-api-leg">leg</h1>

## searchLegs

<a id="opIdsearchLegs"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/legs \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://platform.roserocket.com/v1/legs HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://platform.roserocket.com/v1/legs',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://platform.roserocket.com/v1/legs", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /legs`

*Search legs*

<h3 id="searchlegs-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|created_start_at|query|string(date-time)|false|Date range (start)|
|created_end_at|query|string(date-time)|false|Date range (end)|
|search_term|query|string|false|Search term|
|external_id|query|string|false|External ID to filter by|
|offset|query|integer|false|Pagination offset|
|limit|query|integer|false|Pagination limit|

> Example responses

> 200 Response

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
      "origin_start_at": "2019-02-21T15:32:17Z",
      "origin_end_at": "2019-02-21T15:32:17Z",
      "origin_appt_start_at": "2019-02-21T15:32:17Z",
      "origin_appt_end_at": "2019-02-21T15:32:17Z",
      "destination_start_at": "2019-02-21T15:32:17Z",
      "destination_end_at": "2019-02-21T15:32:17Z",
      "destination_appt_start_at": "2019-02-21T15:32:17Z",
      "destination_appt_end_at": "2019-02-21T15:32:17Z",
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
        "origin_arrived_at": "2019-02-21T15:32:17Z",
        "origin_in_at": "2019-02-21T15:32:17Z",
        "origin_pickedup_at": "2019-02-21T15:32:17Z",
        "origin_out_at": "2019-02-21T15:32:17Z",
        "destination_arrived_at": "2019-02-21T15:32:17Z",
        "destination_in_at": "2019-02-21T15:32:17Z",
        "destination_delivered_at": "2019-02-21T15:32:17Z",
        "destination_out_at": "2019-02-21T15:32:17Z"
      }
    }
  ],
  "offset": 0,
  "limit": 0,
  "total": 0
}
```

<h3 id="searchlegs-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="searchlegs-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» legs|[[Leg](#schemaleg)]|false|none|[Leg]|
|»» id|string(uuid)|false|read-only|Auto generated system ID|
|»» sequence_id|integer|false|read-only|Auto generated sequence ID per customer|
|»» version|integer|false|read-only|Auto generated version number (incremental)|
|»» external_id|string|false|none|External ID for mapping the leg to an external system. This field value can be _null_|
|»» public_id|string|false|read-only|Auto generated human readable ID|
|»» order_id|string|false|read-only|Related order ID|
|»» manifest_id|string|false|none|Related manifest ID (assigned). This field value can be _null_|
|»» origin_stop_id|string|false|read-only|Stop ID of the origin (only if this leg has been assigned to a manifest). This field value can be _null_|
|»» destination_stop_id|string|false|read-only|Stop ID of the destination (only if this leg has been assigned to a manifest). This field value can be _null_|
|»» origin|[LegAddress](#schemalegaddress)|false|none|Leg address|
|»»» terminal_id|string(uuid)|false|none|Related terminal ID. This field value can be _null_|
|»»» org_name|string|false|none|Organization name|
|»»» contact_name|string|false|none|Contact name|
|»»» address_1|string|false|none|Address line 1|
|»»» address_2|string|false|none|Address line 2|
|»»» suite|string|false|none|Suite number|
|»»» city|string|false|none|City|
|»»» state|string|false|none|State / Province|
|»»» country|string|false|none|Country (2 letter ISO)|
|»»» postal|string|false|none|Postal / Zip code|
|»»» phone|string|false|none|Phone number|
|»»» phone_ext|string|false|none|Phone extension|
|»»» email|string|false|none|Email|
|»»» fax|string|false|none|Fax|
|»»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» destination|[LegAddress](#schemalegaddress)|false|none|Leg address|
|»» status|string|false|read-only|Leg Status|
|»» origin_start_at|string(date-time)|false|none|Origin ready time range (start)|
|»» origin_end_at|string(date-time)|false|none|Origin ready time range (end)|
|»» origin_appt_start_at|string(date-time)|false|none|Origin appointment time range (start). This field value can be _null_|
|»» origin_appt_end_at|string(date-time)|false|none|Origin appointment time range (end). This field value can be _null_|
|»» destination_start_at|string(date-time)|false|none|Destination expected time range (start). This field value can be _null_|
|»» destination_end_at|string(date-time)|false|none|Destination expected time range (end). This field value can be _null_|
|»» destination_appt_start_at|string(date-time)|false|none|Destination appointment time range (start). This field value can be _null_|
|»» destination_appt_end_at|string(date-time)|false|none|Destination appointment time range (end). This field value can be _null_|
|»» commodities|[[Commodity](#schemacommodity)]|false|none|Commodities items|
|»»» id|string(uuid)|false|read-only|Auto generated commodity id|
|»»» measurement_unit|string|false|none|Measurement unit|
|»»» weight_unit|string|false|none|Weight unit|
|»»» freight_class|string|false|none|Freight class|
|»»» commodity_type|string|false|none|Commodity type|
|»»» commodity_type_other|string|false|none|If commodity type is set to _other_, then this field must have value|
|»»» description|string|false|none|Description of the commodity|
|»»» feet|number(float)|false|none|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_|
|»»» volume|number(float)|false|none|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_|
|»»» length|number(float)|false|none|Length of the commodity|
|»»» width|number(float)|false|none|Width of the commodity|
|»»» height|number(float)|false|none|Height of the commodity|
|»»» weight|number(float)|false|none|Weight of the commodity|
|»»» nmfc|string|false|none|NMFC number|
|»»» is_stackable|boolean|false|none|Is this commodity can be stacked?|
|»»» quantity|integer|false|none|Quantity of the commodity|
|»»» pieces|integer|false|none|Total number of pieces. This field value can be _null_|
|»»» sku|string|false|none|SKU number|
|»» accessorials|[string]|false|none|none|
|»» history|[LegHistory](#schemaleghistory)|false|read-only|Historical timestamps of a leg|
|»»» origin_arrived_at|string(date-time)|false|none|The timestamp of when the driver/partner arrived at origin|
|»»» origin_in_at|string(date-time)|false|none|The timestamp of when the driver/partner in at origin|
|»»» origin_pickedup_at|string(date-time)|false|none|The timestamp of when the driver/partner picked up at origin|
|»»» origin_out_at|string(date-time)|false|none|The timestamp of when the driver/partner out at origin|
|»»» destination_arrived_at|string(date-time)|false|none|The timestamp of when the driver/partner arrived at destination|
|»»» destination_in_at|string(date-time)|false|none|The timestamp of when the driver/partner in at destination|
|»»» destination_delivered_at|string(date-time)|false|none|The timestamp of when the driver/partner delievered up at destination|
|»»» destination_out_at|string(date-time)|false|none|The timestamp of when the driver/partner out at destination|
|»» offset|integer|false|none|none|
|»» limit|integer|false|none|none|
|»» total|integer|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|available|
|status|pending|
|status|dispatched|
|status|arrived_origin|
|status|in_origin|
|status|loaded|
|status|departed_origin|
|status|arrived_destination|
|status|in_destination|
|status|unloaded|
|status|departed_destination|
|status|cancelled|
|status|problem|
|measurement_unit|inch|
|measurement_unit|cm|
|weight_unit|lb|
|weight_unit|kg|
|commodity_type|skid|
|commodity_type|other|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: legs )
</aside>

## reviseLegOriginById

<a id="opIdreviseLegOriginById"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/legs/{legID}/revise_origin \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');
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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
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
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://platform.roserocket.com/v1/legs/{legID}/revise_origin", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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

<h3 id="reviselegoriginbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|legID|path|string|true|ID of the leg to revise. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|[LegAddressReviseRequest](#schemalegaddressreviserequest)|true|Leg address revise object|

> Example responses

> 200 Response

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
    "origin_start_at": "2019-02-21T15:32:17Z",
    "origin_end_at": "2019-02-21T15:32:17Z",
    "origin_appt_start_at": "2019-02-21T15:32:17Z",
    "origin_appt_end_at": "2019-02-21T15:32:17Z",
    "destination_start_at": "2019-02-21T15:32:17Z",
    "destination_end_at": "2019-02-21T15:32:17Z",
    "destination_appt_start_at": "2019-02-21T15:32:17Z",
    "destination_appt_end_at": "2019-02-21T15:32:17Z",
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
      "origin_arrived_at": "2019-02-21T15:32:17Z",
      "origin_in_at": "2019-02-21T15:32:17Z",
      "origin_pickedup_at": "2019-02-21T15:32:17Z",
      "origin_out_at": "2019-02-21T15:32:17Z",
      "destination_arrived_at": "2019-02-21T15:32:17Z",
      "destination_in_at": "2019-02-21T15:32:17Z",
      "destination_delivered_at": "2019-02-21T15:32:17Z",
      "destination_out_at": "2019-02-21T15:32:17Z"
    }
  }
}
```

<h3 id="reviselegoriginbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="reviselegoriginbyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» leg|[Leg](#schemaleg)|false|none|Leg|
|»» id|string(uuid)|false|read-only|Auto generated system ID|
|»» sequence_id|integer|false|read-only|Auto generated sequence ID per customer|
|»» version|integer|false|read-only|Auto generated version number (incremental)|
|»» external_id|string|false|none|External ID for mapping the leg to an external system. This field value can be _null_|
|»» public_id|string|false|read-only|Auto generated human readable ID|
|»» order_id|string|false|read-only|Related order ID|
|»» manifest_id|string|false|none|Related manifest ID (assigned). This field value can be _null_|
|»» origin_stop_id|string|false|read-only|Stop ID of the origin (only if this leg has been assigned to a manifest). This field value can be _null_|
|»» destination_stop_id|string|false|read-only|Stop ID of the destination (only if this leg has been assigned to a manifest). This field value can be _null_|
|»» origin|[LegAddress](#schemalegaddress)|false|none|Leg address|
|»»» terminal_id|string(uuid)|false|none|Related terminal ID. This field value can be _null_|
|»»» org_name|string|false|none|Organization name|
|»»» contact_name|string|false|none|Contact name|
|»»» address_1|string|false|none|Address line 1|
|»»» address_2|string|false|none|Address line 2|
|»»» suite|string|false|none|Suite number|
|»»» city|string|false|none|City|
|»»» state|string|false|none|State / Province|
|»»» country|string|false|none|Country (2 letter ISO)|
|»»» postal|string|false|none|Postal / Zip code|
|»»» phone|string|false|none|Phone number|
|»»» phone_ext|string|false|none|Phone extension|
|»»» email|string|false|none|Email|
|»»» fax|string|false|none|Fax|
|»»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» destination|[LegAddress](#schemalegaddress)|false|none|Leg address|
|»» status|string|false|read-only|Leg Status|
|»» origin_start_at|string(date-time)|false|none|Origin ready time range (start)|
|»» origin_end_at|string(date-time)|false|none|Origin ready time range (end)|
|»» origin_appt_start_at|string(date-time)|false|none|Origin appointment time range (start). This field value can be _null_|
|»» origin_appt_end_at|string(date-time)|false|none|Origin appointment time range (end). This field value can be _null_|
|»» destination_start_at|string(date-time)|false|none|Destination expected time range (start). This field value can be _null_|
|»» destination_end_at|string(date-time)|false|none|Destination expected time range (end). This field value can be _null_|
|»» destination_appt_start_at|string(date-time)|false|none|Destination appointment time range (start). This field value can be _null_|
|»» destination_appt_end_at|string(date-time)|false|none|Destination appointment time range (end). This field value can be _null_|
|»» commodities|[[Commodity](#schemacommodity)]|false|none|Commodities items|
|»»» id|string(uuid)|false|read-only|Auto generated commodity id|
|»»» measurement_unit|string|false|none|Measurement unit|
|»»» weight_unit|string|false|none|Weight unit|
|»»» freight_class|string|false|none|Freight class|
|»»» commodity_type|string|false|none|Commodity type|
|»»» commodity_type_other|string|false|none|If commodity type is set to _other_, then this field must have value|
|»»» description|string|false|none|Description of the commodity|
|»»» feet|number(float)|false|none|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_|
|»»» volume|number(float)|false|none|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_|
|»»» length|number(float)|false|none|Length of the commodity|
|»»» width|number(float)|false|none|Width of the commodity|
|»»» height|number(float)|false|none|Height of the commodity|
|»»» weight|number(float)|false|none|Weight of the commodity|
|»»» nmfc|string|false|none|NMFC number|
|»»» is_stackable|boolean|false|none|Is this commodity can be stacked?|
|»»» quantity|integer|false|none|Quantity of the commodity|
|»»» pieces|integer|false|none|Total number of pieces. This field value can be _null_|
|»»» sku|string|false|none|SKU number|
|»» accessorials|[string]|false|none|none|
|»» history|[LegHistory](#schemaleghistory)|false|read-only|Historical timestamps of a leg|
|»»» origin_arrived_at|string(date-time)|false|none|The timestamp of when the driver/partner arrived at origin|
|»»» origin_in_at|string(date-time)|false|none|The timestamp of when the driver/partner in at origin|
|»»» origin_pickedup_at|string(date-time)|false|none|The timestamp of when the driver/partner picked up at origin|
|»»» origin_out_at|string(date-time)|false|none|The timestamp of when the driver/partner out at origin|
|»»» destination_arrived_at|string(date-time)|false|none|The timestamp of when the driver/partner arrived at destination|
|»»» destination_in_at|string(date-time)|false|none|The timestamp of when the driver/partner in at destination|
|»»» destination_delivered_at|string(date-time)|false|none|The timestamp of when the driver/partner delievered up at destination|
|»»» destination_out_at|string(date-time)|false|none|The timestamp of when the driver/partner out at destination|

#### Enumerated Values

|Property|Value|
|---|---|
|status|available|
|status|pending|
|status|dispatched|
|status|arrived_origin|
|status|in_origin|
|status|loaded|
|status|departed_origin|
|status|arrived_destination|
|status|in_destination|
|status|unloaded|
|status|departed_destination|
|status|cancelled|
|status|problem|
|measurement_unit|inch|
|measurement_unit|cm|
|weight_unit|lb|
|weight_unit|kg|
|commodity_type|skid|
|commodity_type|other|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: legs )
</aside>

## reviseLegDestinationById

<a id="opIdreviseLegDestinationById"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/legs/{legID}/revise_destination \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');
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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
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
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://platform.roserocket.com/v1/legs/{legID}/revise_destination", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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

<h3 id="reviselegdestinationbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|legID|path|string|true|ID of the leg to revise. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|[LegAddressReviseRequest](#schemalegaddressreviserequest)|true|Leg address revise object|

> Example responses

> 200 Response

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
    "origin_start_at": "2019-02-21T15:32:17Z",
    "origin_end_at": "2019-02-21T15:32:17Z",
    "origin_appt_start_at": "2019-02-21T15:32:17Z",
    "origin_appt_end_at": "2019-02-21T15:32:17Z",
    "destination_start_at": "2019-02-21T15:32:17Z",
    "destination_end_at": "2019-02-21T15:32:17Z",
    "destination_appt_start_at": "2019-02-21T15:32:17Z",
    "destination_appt_end_at": "2019-02-21T15:32:17Z",
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
      "origin_arrived_at": "2019-02-21T15:32:17Z",
      "origin_in_at": "2019-02-21T15:32:17Z",
      "origin_pickedup_at": "2019-02-21T15:32:17Z",
      "origin_out_at": "2019-02-21T15:32:17Z",
      "destination_arrived_at": "2019-02-21T15:32:17Z",
      "destination_in_at": "2019-02-21T15:32:17Z",
      "destination_delivered_at": "2019-02-21T15:32:17Z",
      "destination_out_at": "2019-02-21T15:32:17Z"
    }
  }
}
```

<h3 id="reviselegdestinationbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="reviselegdestinationbyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» leg|[Leg](#schemaleg)|false|none|Leg|
|»» id|string(uuid)|false|read-only|Auto generated system ID|
|»» sequence_id|integer|false|read-only|Auto generated sequence ID per customer|
|»» version|integer|false|read-only|Auto generated version number (incremental)|
|»» external_id|string|false|none|External ID for mapping the leg to an external system. This field value can be _null_|
|»» public_id|string|false|read-only|Auto generated human readable ID|
|»» order_id|string|false|read-only|Related order ID|
|»» manifest_id|string|false|none|Related manifest ID (assigned). This field value can be _null_|
|»» origin_stop_id|string|false|read-only|Stop ID of the origin (only if this leg has been assigned to a manifest). This field value can be _null_|
|»» destination_stop_id|string|false|read-only|Stop ID of the destination (only if this leg has been assigned to a manifest). This field value can be _null_|
|»» origin|[LegAddress](#schemalegaddress)|false|none|Leg address|
|»»» terminal_id|string(uuid)|false|none|Related terminal ID. This field value can be _null_|
|»»» org_name|string|false|none|Organization name|
|»»» contact_name|string|false|none|Contact name|
|»»» address_1|string|false|none|Address line 1|
|»»» address_2|string|false|none|Address line 2|
|»»» suite|string|false|none|Suite number|
|»»» city|string|false|none|City|
|»»» state|string|false|none|State / Province|
|»»» country|string|false|none|Country (2 letter ISO)|
|»»» postal|string|false|none|Postal / Zip code|
|»»» phone|string|false|none|Phone number|
|»»» phone_ext|string|false|none|Phone extension|
|»»» email|string|false|none|Email|
|»»» fax|string|false|none|Fax|
|»»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» destination|[LegAddress](#schemalegaddress)|false|none|Leg address|
|»» status|string|false|read-only|Leg Status|
|»» origin_start_at|string(date-time)|false|none|Origin ready time range (start)|
|»» origin_end_at|string(date-time)|false|none|Origin ready time range (end)|
|»» origin_appt_start_at|string(date-time)|false|none|Origin appointment time range (start). This field value can be _null_|
|»» origin_appt_end_at|string(date-time)|false|none|Origin appointment time range (end). This field value can be _null_|
|»» destination_start_at|string(date-time)|false|none|Destination expected time range (start). This field value can be _null_|
|»» destination_end_at|string(date-time)|false|none|Destination expected time range (end). This field value can be _null_|
|»» destination_appt_start_at|string(date-time)|false|none|Destination appointment time range (start). This field value can be _null_|
|»» destination_appt_end_at|string(date-time)|false|none|Destination appointment time range (end). This field value can be _null_|
|»» commodities|[[Commodity](#schemacommodity)]|false|none|Commodities items|
|»»» id|string(uuid)|false|read-only|Auto generated commodity id|
|»»» measurement_unit|string|false|none|Measurement unit|
|»»» weight_unit|string|false|none|Weight unit|
|»»» freight_class|string|false|none|Freight class|
|»»» commodity_type|string|false|none|Commodity type|
|»»» commodity_type_other|string|false|none|If commodity type is set to _other_, then this field must have value|
|»»» description|string|false|none|Description of the commodity|
|»»» feet|number(float)|false|none|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_|
|»»» volume|number(float)|false|none|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_|
|»»» length|number(float)|false|none|Length of the commodity|
|»»» width|number(float)|false|none|Width of the commodity|
|»»» height|number(float)|false|none|Height of the commodity|
|»»» weight|number(float)|false|none|Weight of the commodity|
|»»» nmfc|string|false|none|NMFC number|
|»»» is_stackable|boolean|false|none|Is this commodity can be stacked?|
|»»» quantity|integer|false|none|Quantity of the commodity|
|»»» pieces|integer|false|none|Total number of pieces. This field value can be _null_|
|»»» sku|string|false|none|SKU number|
|»» accessorials|[string]|false|none|none|
|»» history|[LegHistory](#schemaleghistory)|false|read-only|Historical timestamps of a leg|
|»»» origin_arrived_at|string(date-time)|false|none|The timestamp of when the driver/partner arrived at origin|
|»»» origin_in_at|string(date-time)|false|none|The timestamp of when the driver/partner in at origin|
|»»» origin_pickedup_at|string(date-time)|false|none|The timestamp of when the driver/partner picked up at origin|
|»»» origin_out_at|string(date-time)|false|none|The timestamp of when the driver/partner out at origin|
|»»» destination_arrived_at|string(date-time)|false|none|The timestamp of when the driver/partner arrived at destination|
|»»» destination_in_at|string(date-time)|false|none|The timestamp of when the driver/partner in at destination|
|»»» destination_delivered_at|string(date-time)|false|none|The timestamp of when the driver/partner delievered up at destination|
|»»» destination_out_at|string(date-time)|false|none|The timestamp of when the driver/partner out at destination|

#### Enumerated Values

|Property|Value|
|---|---|
|status|available|
|status|pending|
|status|dispatched|
|status|arrived_origin|
|status|in_origin|
|status|loaded|
|status|departed_origin|
|status|arrived_destination|
|status|in_destination|
|status|unloaded|
|status|departed_destination|
|status|cancelled|
|status|problem|
|measurement_unit|inch|
|measurement_unit|cm|
|weight_unit|lb|
|weight_unit|kg|
|commodity_type|skid|
|commodity_type|other|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: legs )
</aside>

## reviseLegCommoditiesById

<a id="opIdreviseLegCommoditiesById"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/legs/{legID}/revise_commodities \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');
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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
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
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://platform.roserocket.com/v1/legs/{legID}/revise_commodities", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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

<h3 id="reviselegcommoditiesbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|legID|path|string|true|ID of the leg to revise. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|[CommodityReviseRequest](#schemacommodityreviserequest)|true|Leg address revise object|

> Example responses

> 200 Response

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
    "origin_start_at": "2019-02-21T15:32:17Z",
    "origin_end_at": "2019-02-21T15:32:17Z",
    "origin_appt_start_at": "2019-02-21T15:32:17Z",
    "origin_appt_end_at": "2019-02-21T15:32:17Z",
    "destination_start_at": "2019-02-21T15:32:17Z",
    "destination_end_at": "2019-02-21T15:32:17Z",
    "destination_appt_start_at": "2019-02-21T15:32:17Z",
    "destination_appt_end_at": "2019-02-21T15:32:17Z",
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
      "origin_arrived_at": "2019-02-21T15:32:17Z",
      "origin_in_at": "2019-02-21T15:32:17Z",
      "origin_pickedup_at": "2019-02-21T15:32:17Z",
      "origin_out_at": "2019-02-21T15:32:17Z",
      "destination_arrived_at": "2019-02-21T15:32:17Z",
      "destination_in_at": "2019-02-21T15:32:17Z",
      "destination_delivered_at": "2019-02-21T15:32:17Z",
      "destination_out_at": "2019-02-21T15:32:17Z"
    }
  }
}
```

<h3 id="reviselegcommoditiesbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="reviselegcommoditiesbyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» leg|[Leg](#schemaleg)|false|none|Leg|
|»» id|string(uuid)|false|read-only|Auto generated system ID|
|»» sequence_id|integer|false|read-only|Auto generated sequence ID per customer|
|»» version|integer|false|read-only|Auto generated version number (incremental)|
|»» external_id|string|false|none|External ID for mapping the leg to an external system. This field value can be _null_|
|»» public_id|string|false|read-only|Auto generated human readable ID|
|»» order_id|string|false|read-only|Related order ID|
|»» manifest_id|string|false|none|Related manifest ID (assigned). This field value can be _null_|
|»» origin_stop_id|string|false|read-only|Stop ID of the origin (only if this leg has been assigned to a manifest). This field value can be _null_|
|»» destination_stop_id|string|false|read-only|Stop ID of the destination (only if this leg has been assigned to a manifest). This field value can be _null_|
|»» origin|[LegAddress](#schemalegaddress)|false|none|Leg address|
|»»» terminal_id|string(uuid)|false|none|Related terminal ID. This field value can be _null_|
|»»» org_name|string|false|none|Organization name|
|»»» contact_name|string|false|none|Contact name|
|»»» address_1|string|false|none|Address line 1|
|»»» address_2|string|false|none|Address line 2|
|»»» suite|string|false|none|Suite number|
|»»» city|string|false|none|City|
|»»» state|string|false|none|State / Province|
|»»» country|string|false|none|Country (2 letter ISO)|
|»»» postal|string|false|none|Postal / Zip code|
|»»» phone|string|false|none|Phone number|
|»»» phone_ext|string|false|none|Phone extension|
|»»» email|string|false|none|Email|
|»»» fax|string|false|none|Fax|
|»»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» destination|[LegAddress](#schemalegaddress)|false|none|Leg address|
|»» status|string|false|read-only|Leg Status|
|»» origin_start_at|string(date-time)|false|none|Origin ready time range (start)|
|»» origin_end_at|string(date-time)|false|none|Origin ready time range (end)|
|»» origin_appt_start_at|string(date-time)|false|none|Origin appointment time range (start). This field value can be _null_|
|»» origin_appt_end_at|string(date-time)|false|none|Origin appointment time range (end). This field value can be _null_|
|»» destination_start_at|string(date-time)|false|none|Destination expected time range (start). This field value can be _null_|
|»» destination_end_at|string(date-time)|false|none|Destination expected time range (end). This field value can be _null_|
|»» destination_appt_start_at|string(date-time)|false|none|Destination appointment time range (start). This field value can be _null_|
|»» destination_appt_end_at|string(date-time)|false|none|Destination appointment time range (end). This field value can be _null_|
|»» commodities|[[Commodity](#schemacommodity)]|false|none|Commodities items|
|»»» id|string(uuid)|false|read-only|Auto generated commodity id|
|»»» measurement_unit|string|false|none|Measurement unit|
|»»» weight_unit|string|false|none|Weight unit|
|»»» freight_class|string|false|none|Freight class|
|»»» commodity_type|string|false|none|Commodity type|
|»»» commodity_type_other|string|false|none|If commodity type is set to _other_, then this field must have value|
|»»» description|string|false|none|Description of the commodity|
|»»» feet|number(float)|false|none|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_|
|»»» volume|number(float)|false|none|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_|
|»»» length|number(float)|false|none|Length of the commodity|
|»»» width|number(float)|false|none|Width of the commodity|
|»»» height|number(float)|false|none|Height of the commodity|
|»»» weight|number(float)|false|none|Weight of the commodity|
|»»» nmfc|string|false|none|NMFC number|
|»»» is_stackable|boolean|false|none|Is this commodity can be stacked?|
|»»» quantity|integer|false|none|Quantity of the commodity|
|»»» pieces|integer|false|none|Total number of pieces. This field value can be _null_|
|»»» sku|string|false|none|SKU number|
|»» accessorials|[string]|false|none|none|
|»» history|[LegHistory](#schemaleghistory)|false|read-only|Historical timestamps of a leg|
|»»» origin_arrived_at|string(date-time)|false|none|The timestamp of when the driver/partner arrived at origin|
|»»» origin_in_at|string(date-time)|false|none|The timestamp of when the driver/partner in at origin|
|»»» origin_pickedup_at|string(date-time)|false|none|The timestamp of when the driver/partner picked up at origin|
|»»» origin_out_at|string(date-time)|false|none|The timestamp of when the driver/partner out at origin|
|»»» destination_arrived_at|string(date-time)|false|none|The timestamp of when the driver/partner arrived at destination|
|»»» destination_in_at|string(date-time)|false|none|The timestamp of when the driver/partner in at destination|
|»»» destination_delivered_at|string(date-time)|false|none|The timestamp of when the driver/partner delievered up at destination|
|»»» destination_out_at|string(date-time)|false|none|The timestamp of when the driver/partner out at destination|

#### Enumerated Values

|Property|Value|
|---|---|
|status|available|
|status|pending|
|status|dispatched|
|status|arrived_origin|
|status|in_origin|
|status|loaded|
|status|departed_origin|
|status|arrived_destination|
|status|in_destination|
|status|unloaded|
|status|departed_destination|
|status|cancelled|
|status|problem|
|measurement_unit|inch|
|measurement_unit|cm|
|weight_unit|lb|
|weight_unit|kg|
|commodity_type|skid|
|commodity_type|other|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: legs )
</aside>

## loadLegById

<a id="opIdloadLegById"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/legs/{legID}/load \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://platform.roserocket.com/v1/legs/{legID}/load HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://platform.roserocket.com/v1/legs/{legID}/load',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/legs/{legID}/load", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /legs/{legID}/load`

*Load leg by ID*

<h3 id="loadlegbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|legID|path|string|true|ID of the leg to load. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.|
|from_arrive_at|query|string(date-time)|false|From arrive at|
|from_in_at|query|string(date-time)|false|From in at|
|from_out_at|query|string(date-time)|false|From out at|
|pickedup_at|query|string(date-time)|false|Picked up at|

> Example responses

> 200 Response

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
    "origin_start_at": "2019-02-21T15:32:17Z",
    "origin_end_at": "2019-02-21T15:32:17Z",
    "origin_appt_start_at": "2019-02-21T15:32:17Z",
    "origin_appt_end_at": "2019-02-21T15:32:17Z",
    "destination_start_at": "2019-02-21T15:32:17Z",
    "destination_end_at": "2019-02-21T15:32:17Z",
    "destination_appt_start_at": "2019-02-21T15:32:17Z",
    "destination_appt_end_at": "2019-02-21T15:32:17Z",
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
      "origin_arrived_at": "2019-02-21T15:32:17Z",
      "origin_in_at": "2019-02-21T15:32:17Z",
      "origin_pickedup_at": "2019-02-21T15:32:17Z",
      "origin_out_at": "2019-02-21T15:32:17Z",
      "destination_arrived_at": "2019-02-21T15:32:17Z",
      "destination_in_at": "2019-02-21T15:32:17Z",
      "destination_delivered_at": "2019-02-21T15:32:17Z",
      "destination_out_at": "2019-02-21T15:32:17Z"
    }
  }
}
```

<h3 id="loadlegbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="loadlegbyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» leg|[Leg](#schemaleg)|false|none|Leg|
|»» id|string(uuid)|false|read-only|Auto generated system ID|
|»» sequence_id|integer|false|read-only|Auto generated sequence ID per customer|
|»» version|integer|false|read-only|Auto generated version number (incremental)|
|»» external_id|string|false|none|External ID for mapping the leg to an external system. This field value can be _null_|
|»» public_id|string|false|read-only|Auto generated human readable ID|
|»» order_id|string|false|read-only|Related order ID|
|»» manifest_id|string|false|none|Related manifest ID (assigned). This field value can be _null_|
|»» origin_stop_id|string|false|read-only|Stop ID of the origin (only if this leg has been assigned to a manifest). This field value can be _null_|
|»» destination_stop_id|string|false|read-only|Stop ID of the destination (only if this leg has been assigned to a manifest). This field value can be _null_|
|»» origin|[LegAddress](#schemalegaddress)|false|none|Leg address|
|»»» terminal_id|string(uuid)|false|none|Related terminal ID. This field value can be _null_|
|»»» org_name|string|false|none|Organization name|
|»»» contact_name|string|false|none|Contact name|
|»»» address_1|string|false|none|Address line 1|
|»»» address_2|string|false|none|Address line 2|
|»»» suite|string|false|none|Suite number|
|»»» city|string|false|none|City|
|»»» state|string|false|none|State / Province|
|»»» country|string|false|none|Country (2 letter ISO)|
|»»» postal|string|false|none|Postal / Zip code|
|»»» phone|string|false|none|Phone number|
|»»» phone_ext|string|false|none|Phone extension|
|»»» email|string|false|none|Email|
|»»» fax|string|false|none|Fax|
|»»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» destination|[LegAddress](#schemalegaddress)|false|none|Leg address|
|»» status|string|false|read-only|Leg Status|
|»» origin_start_at|string(date-time)|false|none|Origin ready time range (start)|
|»» origin_end_at|string(date-time)|false|none|Origin ready time range (end)|
|»» origin_appt_start_at|string(date-time)|false|none|Origin appointment time range (start). This field value can be _null_|
|»» origin_appt_end_at|string(date-time)|false|none|Origin appointment time range (end). This field value can be _null_|
|»» destination_start_at|string(date-time)|false|none|Destination expected time range (start). This field value can be _null_|
|»» destination_end_at|string(date-time)|false|none|Destination expected time range (end). This field value can be _null_|
|»» destination_appt_start_at|string(date-time)|false|none|Destination appointment time range (start). This field value can be _null_|
|»» destination_appt_end_at|string(date-time)|false|none|Destination appointment time range (end). This field value can be _null_|
|»» commodities|[[Commodity](#schemacommodity)]|false|none|Commodities items|
|»»» id|string(uuid)|false|read-only|Auto generated commodity id|
|»»» measurement_unit|string|false|none|Measurement unit|
|»»» weight_unit|string|false|none|Weight unit|
|»»» freight_class|string|false|none|Freight class|
|»»» commodity_type|string|false|none|Commodity type|
|»»» commodity_type_other|string|false|none|If commodity type is set to _other_, then this field must have value|
|»»» description|string|false|none|Description of the commodity|
|»»» feet|number(float)|false|none|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_|
|»»» volume|number(float)|false|none|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_|
|»»» length|number(float)|false|none|Length of the commodity|
|»»» width|number(float)|false|none|Width of the commodity|
|»»» height|number(float)|false|none|Height of the commodity|
|»»» weight|number(float)|false|none|Weight of the commodity|
|»»» nmfc|string|false|none|NMFC number|
|»»» is_stackable|boolean|false|none|Is this commodity can be stacked?|
|»»» quantity|integer|false|none|Quantity of the commodity|
|»»» pieces|integer|false|none|Total number of pieces. This field value can be _null_|
|»»» sku|string|false|none|SKU number|
|»» accessorials|[string]|false|none|none|
|»» history|[LegHistory](#schemaleghistory)|false|read-only|Historical timestamps of a leg|
|»»» origin_arrived_at|string(date-time)|false|none|The timestamp of when the driver/partner arrived at origin|
|»»» origin_in_at|string(date-time)|false|none|The timestamp of when the driver/partner in at origin|
|»»» origin_pickedup_at|string(date-time)|false|none|The timestamp of when the driver/partner picked up at origin|
|»»» origin_out_at|string(date-time)|false|none|The timestamp of when the driver/partner out at origin|
|»»» destination_arrived_at|string(date-time)|false|none|The timestamp of when the driver/partner arrived at destination|
|»»» destination_in_at|string(date-time)|false|none|The timestamp of when the driver/partner in at destination|
|»»» destination_delivered_at|string(date-time)|false|none|The timestamp of when the driver/partner delievered up at destination|
|»»» destination_out_at|string(date-time)|false|none|The timestamp of when the driver/partner out at destination|

#### Enumerated Values

|Property|Value|
|---|---|
|status|available|
|status|pending|
|status|dispatched|
|status|arrived_origin|
|status|in_origin|
|status|loaded|
|status|departed_origin|
|status|arrived_destination|
|status|in_destination|
|status|unloaded|
|status|departed_destination|
|status|cancelled|
|status|problem|
|measurement_unit|inch|
|measurement_unit|cm|
|weight_unit|lb|
|weight_unit|kg|
|commodity_type|skid|
|commodity_type|other|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: legs )
</aside>

## unloadLegById

<a id="opIdunloadLegById"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/legs/{legID}/unload \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://platform.roserocket.com/v1/legs/{legID}/unload HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://platform.roserocket.com/v1/legs/{legID}/unload',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/legs/{legID}/unload", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /legs/{legID}/unload`

*Unload leg by ID*

<h3 id="unloadlegbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|legID|path|string|true|ID of the leg to unload. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.|
|to_arrive_at|query|string(date-time)|false|From arrive at|
|to_in_at|query|string(date-time)|false|From in at|
|to_out_at|query|string(date-time)|false|From out at|
|delivered_at|query|string(date-time)|false|Picked up at|

> Example responses

> 200 Response

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
    "origin_start_at": "2019-02-21T15:32:17Z",
    "origin_end_at": "2019-02-21T15:32:17Z",
    "origin_appt_start_at": "2019-02-21T15:32:17Z",
    "origin_appt_end_at": "2019-02-21T15:32:17Z",
    "destination_start_at": "2019-02-21T15:32:17Z",
    "destination_end_at": "2019-02-21T15:32:17Z",
    "destination_appt_start_at": "2019-02-21T15:32:17Z",
    "destination_appt_end_at": "2019-02-21T15:32:17Z",
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
      "origin_arrived_at": "2019-02-21T15:32:17Z",
      "origin_in_at": "2019-02-21T15:32:17Z",
      "origin_pickedup_at": "2019-02-21T15:32:17Z",
      "origin_out_at": "2019-02-21T15:32:17Z",
      "destination_arrived_at": "2019-02-21T15:32:17Z",
      "destination_in_at": "2019-02-21T15:32:17Z",
      "destination_delivered_at": "2019-02-21T15:32:17Z",
      "destination_out_at": "2019-02-21T15:32:17Z"
    }
  }
}
```

<h3 id="unloadlegbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="unloadlegbyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» leg|[Leg](#schemaleg)|false|none|Leg|
|»» id|string(uuid)|false|read-only|Auto generated system ID|
|»» sequence_id|integer|false|read-only|Auto generated sequence ID per customer|
|»» version|integer|false|read-only|Auto generated version number (incremental)|
|»» external_id|string|false|none|External ID for mapping the leg to an external system. This field value can be _null_|
|»» public_id|string|false|read-only|Auto generated human readable ID|
|»» order_id|string|false|read-only|Related order ID|
|»» manifest_id|string|false|none|Related manifest ID (assigned). This field value can be _null_|
|»» origin_stop_id|string|false|read-only|Stop ID of the origin (only if this leg has been assigned to a manifest). This field value can be _null_|
|»» destination_stop_id|string|false|read-only|Stop ID of the destination (only if this leg has been assigned to a manifest). This field value can be _null_|
|»» origin|[LegAddress](#schemalegaddress)|false|none|Leg address|
|»»» terminal_id|string(uuid)|false|none|Related terminal ID. This field value can be _null_|
|»»» org_name|string|false|none|Organization name|
|»»» contact_name|string|false|none|Contact name|
|»»» address_1|string|false|none|Address line 1|
|»»» address_2|string|false|none|Address line 2|
|»»» suite|string|false|none|Suite number|
|»»» city|string|false|none|City|
|»»» state|string|false|none|State / Province|
|»»» country|string|false|none|Country (2 letter ISO)|
|»»» postal|string|false|none|Postal / Zip code|
|»»» phone|string|false|none|Phone number|
|»»» phone_ext|string|false|none|Phone extension|
|»»» email|string|false|none|Email|
|»»» fax|string|false|none|Fax|
|»»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» destination|[LegAddress](#schemalegaddress)|false|none|Leg address|
|»» status|string|false|read-only|Leg Status|
|»» origin_start_at|string(date-time)|false|none|Origin ready time range (start)|
|»» origin_end_at|string(date-time)|false|none|Origin ready time range (end)|
|»» origin_appt_start_at|string(date-time)|false|none|Origin appointment time range (start). This field value can be _null_|
|»» origin_appt_end_at|string(date-time)|false|none|Origin appointment time range (end). This field value can be _null_|
|»» destination_start_at|string(date-time)|false|none|Destination expected time range (start). This field value can be _null_|
|»» destination_end_at|string(date-time)|false|none|Destination expected time range (end). This field value can be _null_|
|»» destination_appt_start_at|string(date-time)|false|none|Destination appointment time range (start). This field value can be _null_|
|»» destination_appt_end_at|string(date-time)|false|none|Destination appointment time range (end). This field value can be _null_|
|»» commodities|[[Commodity](#schemacommodity)]|false|none|Commodities items|
|»»» id|string(uuid)|false|read-only|Auto generated commodity id|
|»»» measurement_unit|string|false|none|Measurement unit|
|»»» weight_unit|string|false|none|Weight unit|
|»»» freight_class|string|false|none|Freight class|
|»»» commodity_type|string|false|none|Commodity type|
|»»» commodity_type_other|string|false|none|If commodity type is set to _other_, then this field must have value|
|»»» description|string|false|none|Description of the commodity|
|»»» feet|number(float)|false|none|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_|
|»»» volume|number(float)|false|none|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_|
|»»» length|number(float)|false|none|Length of the commodity|
|»»» width|number(float)|false|none|Width of the commodity|
|»»» height|number(float)|false|none|Height of the commodity|
|»»» weight|number(float)|false|none|Weight of the commodity|
|»»» nmfc|string|false|none|NMFC number|
|»»» is_stackable|boolean|false|none|Is this commodity can be stacked?|
|»»» quantity|integer|false|none|Quantity of the commodity|
|»»» pieces|integer|false|none|Total number of pieces. This field value can be _null_|
|»»» sku|string|false|none|SKU number|
|»» accessorials|[string]|false|none|none|
|»» history|[LegHistory](#schemaleghistory)|false|read-only|Historical timestamps of a leg|
|»»» origin_arrived_at|string(date-time)|false|none|The timestamp of when the driver/partner arrived at origin|
|»»» origin_in_at|string(date-time)|false|none|The timestamp of when the driver/partner in at origin|
|»»» origin_pickedup_at|string(date-time)|false|none|The timestamp of when the driver/partner picked up at origin|
|»»» origin_out_at|string(date-time)|false|none|The timestamp of when the driver/partner out at origin|
|»»» destination_arrived_at|string(date-time)|false|none|The timestamp of when the driver/partner arrived at destination|
|»»» destination_in_at|string(date-time)|false|none|The timestamp of when the driver/partner in at destination|
|»»» destination_delivered_at|string(date-time)|false|none|The timestamp of when the driver/partner delievered up at destination|
|»»» destination_out_at|string(date-time)|false|none|The timestamp of when the driver/partner out at destination|

#### Enumerated Values

|Property|Value|
|---|---|
|status|available|
|status|pending|
|status|dispatched|
|status|arrived_origin|
|status|in_origin|
|status|loaded|
|status|departed_origin|
|status|arrived_destination|
|status|in_destination|
|status|unloaded|
|status|departed_destination|
|status|cancelled|
|status|problem|
|measurement_unit|inch|
|measurement_unit|cm|
|weight_unit|lb|
|weight_unit|kg|
|commodity_type|skid|
|commodity_type|other|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: legs )
</aside>

## updateLegFileByLegIdAndFileID

<a id="opIdupdateLegFileByLegIdAndFileID"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/legs/{legID}/files/{fileID} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');
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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
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
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://platform.roserocket.com/v1/legs/{legID}/files/{fileID}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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

<h3 id="updatelegfilebylegidandfileid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|legID|path|string|true|ID of the leg for which to update a file/document. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.|
|fileID|path|string|true|ID of the leg file|
|body|body|[LegFileRequest](#schemalegfilerequest)|true|Leg file create request|

> Example responses

> 200 Response

```json
{
  "leg_file": {
    "id": "string",
    "created_at": "2019-02-21T15:32:17Z",
    "updated_at": "2019-02-21T15:32:17Z",
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

<h3 id="updatelegfilebylegidandfileid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="updatelegfilebylegidandfileid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» leg_file|[LegFile](#schemalegfile)|false|none|The file for the leg|
|»» id|string(uuid)|false|none|The uuid for the leg file|
|»» created_at|string(date-time)|false|none|The timestamp for the creation of the leg file|
|»» updated_at|string(date-time)|false|none|The timestamp for the last update of the leg file|
|»» org_id|string(uuid)|false|none|The uuid for the organization of the leg file|
|»» leg_id|string(uuid)|false|none|The uuid of the leg corresponding to the leg file|
|»» uploaded_by|string(uuid)|false|none|The uuid of the user who uploaded the leg file|
|»» uploaded_at|string(uuid)|false|none|The uuid|
|»» type|string|false|none|The type of leg file|
|»» url|string|false|none|The url location for the leg file|
|»» description|string|false|none|A description of the leg file|
|»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» metadata|object|false|none|Metadata object for the leg file|
|»» task_id|string(uuid)|false|none|The task id of the leg that corresponds to the leg file|

#### Enumerated Values

|Property|Value|
|---|---|
|type|other|
|type|comm-invoice|
|type|pod|
|type|pop|
|type|pod-sig|
|type|pop-sig|
|type|carrier-invoice|
|type|smc|
|type|bol|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: legs )
</aside>

## deleteLegFileByLegIdAndFileID

<a id="opIddeleteLegFileByLegIdAndFileID"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE https://platform.roserocket.com/v1/legs/{legID}/files/{fileID} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE https://platform.roserocket.com/v1/legs/{legID}/files/{fileID} HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete 'https://platform.roserocket.com/v1/legs/{legID}/files/{fileID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://platform.roserocket.com/v1/legs/{legID}/files/{fileID}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /legs/{legID}/files/{fileID}`

*Delete a file/document from a specified leg*

<h3 id="deletelegfilebylegidandfileid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|legID|path|string|true|ID of the leg for which to delete file/document. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.|
|fileID|path|string|true|ID of the leg file to delete|

> Example responses

> 200 Response

```json
{
  "Message": "Success"
}
```

<h3 id="deletelegfilebylegidandfileid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="deletelegfilebylegidandfileid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» Message|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|Message|Success|
|Message|Failure|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: legs )
</aside>

## getLegFilesById

<a id="opIdgetLegFilesById"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/legs/{legID}/files \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://platform.roserocket.com/v1/legs/{legID}/files HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://platform.roserocket.com/v1/legs/{legID}/files',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://platform.roserocket.com/v1/legs/{legID}/files", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /legs/{legID}/files`

*Get all leg files/documents for a given ID of a leg*

<h3 id="getlegfilesbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|legID|path|string|true|ID of the leg to get files for. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.|

> Example responses

> 200 Response

```json
{
  "leg_files": [
    {
      "id": "string",
      "created_at": "2019-02-21T15:32:17Z",
      "updated_at": "2019-02-21T15:32:17Z",
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

<h3 id="getlegfilesbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="getlegfilesbyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» leg_files|[[LegFile](#schemalegfile)]|false|none|[The file for the leg]|
|»» id|string(uuid)|false|none|The uuid for the leg file|
|»» created_at|string(date-time)|false|none|The timestamp for the creation of the leg file|
|»» updated_at|string(date-time)|false|none|The timestamp for the last update of the leg file|
|»» org_id|string(uuid)|false|none|The uuid for the organization of the leg file|
|»» leg_id|string(uuid)|false|none|The uuid of the leg corresponding to the leg file|
|»» uploaded_by|string(uuid)|false|none|The uuid of the user who uploaded the leg file|
|»» uploaded_at|string(uuid)|false|none|The uuid|
|»» type|string|false|none|The type of leg file|
|»» url|string|false|none|The url location for the leg file|
|»» description|string|false|none|A description of the leg file|
|»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» metadata|object|false|none|Metadata object for the leg file|
|»» task_id|string(uuid)|false|none|The task id of the leg that corresponds to the leg file|

#### Enumerated Values

|Property|Value|
|---|---|
|type|other|
|type|comm-invoice|
|type|pod|
|type|pop|
|type|pod-sig|
|type|pop-sig|
|type|carrier-invoice|
|type|smc|
|type|bol|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: legs )
</aside>

## addLegFileByLegId

<a id="opIdaddLegFileByLegId"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/legs/{legID}/files \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');
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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
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
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/legs/{legID}/files", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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

<h3 id="addlegfilebylegid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|legID|path|string|true|ID of the leg for which to add a file/document. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|[LegFileRequest](#schemalegfilerequest)|true|Leg file create request|

> Example responses

> 200 Response

```json
{
  "leg_file": {
    "id": "string",
    "created_at": "2019-02-21T15:32:17Z",
    "updated_at": "2019-02-21T15:32:17Z",
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

<h3 id="addlegfilebylegid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="addlegfilebylegid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» leg_file|[LegFile](#schemalegfile)|false|none|The file for the leg|
|»» id|string(uuid)|false|none|The uuid for the leg file|
|»» created_at|string(date-time)|false|none|The timestamp for the creation of the leg file|
|»» updated_at|string(date-time)|false|none|The timestamp for the last update of the leg file|
|»» org_id|string(uuid)|false|none|The uuid for the organization of the leg file|
|»» leg_id|string(uuid)|false|none|The uuid of the leg corresponding to the leg file|
|»» uploaded_by|string(uuid)|false|none|The uuid of the user who uploaded the leg file|
|»» uploaded_at|string(uuid)|false|none|The uuid|
|»» type|string|false|none|The type of leg file|
|»» url|string|false|none|The url location for the leg file|
|»» description|string|false|none|A description of the leg file|
|»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» metadata|object|false|none|Metadata object for the leg file|
|»» task_id|string(uuid)|false|none|The task id of the leg that corresponds to the leg file|

#### Enumerated Values

|Property|Value|
|---|---|
|type|other|
|type|comm-invoice|
|type|pod|
|type|pop|
|type|pod-sig|
|type|pop-sig|
|type|carrier-invoice|
|type|smc|
|type|bol|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: legs )
</aside>

## uploadLegBOLByLegID

<a id="opIduploadLegBOLByLegID"></a>

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
const fetch = require('node-fetch');
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"multipart/form-data"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/legs/{legID}/upload_bol", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /legs/{legID}/upload_bol`

*Upload BOL for a specified leg*

> Body parameter

```yaml
file: string

```

<h3 id="uploadlegbolbylegid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|legID|path|string|true|ID of the leg. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|[uploadLegBOLByLegID](#schemauploadlegbolbylegid)|false|none|
|» file|body|string(binary)|true|File to upload|

> Example responses

> 200 Response

```json
{
  "leg_file": {
    "id": "string",
    "created_at": "2019-02-21T15:32:17Z",
    "updated_at": "2019-02-21T15:32:17Z",
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

<h3 id="uploadlegbolbylegid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="uploadlegbolbylegid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» leg_file|[LegFile](#schemalegfile)|false|none|The file for the leg|
|»» id|string(uuid)|false|none|The uuid for the leg file|
|»» created_at|string(date-time)|false|none|The timestamp for the creation of the leg file|
|»» updated_at|string(date-time)|false|none|The timestamp for the last update of the leg file|
|»» org_id|string(uuid)|false|none|The uuid for the organization of the leg file|
|»» leg_id|string(uuid)|false|none|The uuid of the leg corresponding to the leg file|
|»» uploaded_by|string(uuid)|false|none|The uuid of the user who uploaded the leg file|
|»» uploaded_at|string(uuid)|false|none|The uuid|
|»» type|string|false|none|The type of leg file|
|»» url|string|false|none|The url location for the leg file|
|»» description|string|false|none|A description of the leg file|
|»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» metadata|object|false|none|Metadata object for the leg file|
|»» task_id|string(uuid)|false|none|The task id of the leg that corresponds to the leg file|

#### Enumerated Values

|Property|Value|
|---|---|
|type|other|
|type|comm-invoice|
|type|pod|
|type|pop|
|type|pod-sig|
|type|pop-sig|
|type|carrier-invoice|
|type|smc|
|type|bol|

<aside class="success">
This operation does not require authentication
</aside>

## uploadLegFileByLegID

<a id="opIduploadLegFileByLegID"></a>

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
const fetch = require('node-fetch');
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"multipart/form-data"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/legs/{legID}/upload_file", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /legs/{legID}/upload_file`

*Upload file for a specified leg*

> Body parameter

```yaml
file: string
type: other

```

<h3 id="uploadlegfilebylegid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|legID|path|string|true|ID of the leg. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|[uploadLegFileByLegID](#schemauploadlegfilebylegid)|false|none|
|» file|body|string(binary)|true|File to upload|
|» type|body|string|true|Type of leg file to upload|

#### Enumerated Values

|Parameter|Value|
|---|---|
|» type|other|
|» type|comm-invoice|
|» type|pod|
|» type|pop|
|» type|pod-sig|
|» type|pop-sig|
|» type|carrier-invoice|
|» type|smc|
|» type|bol|

> Example responses

> 200 Response

```json
{
  "leg_file": {
    "id": "string",
    "created_at": "2019-02-21T15:32:17Z",
    "updated_at": "2019-02-21T15:32:17Z",
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

<h3 id="uploadlegfilebylegid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="uploadlegfilebylegid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» leg_file|[LegFile](#schemalegfile)|false|none|The file for the leg|
|»» id|string(uuid)|false|none|The uuid for the leg file|
|»» created_at|string(date-time)|false|none|The timestamp for the creation of the leg file|
|»» updated_at|string(date-time)|false|none|The timestamp for the last update of the leg file|
|»» org_id|string(uuid)|false|none|The uuid for the organization of the leg file|
|»» leg_id|string(uuid)|false|none|The uuid of the leg corresponding to the leg file|
|»» uploaded_by|string(uuid)|false|none|The uuid of the user who uploaded the leg file|
|»» uploaded_at|string(uuid)|false|none|The uuid|
|»» type|string|false|none|The type of leg file|
|»» url|string|false|none|The url location for the leg file|
|»» description|string|false|none|A description of the leg file|
|»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» metadata|object|false|none|Metadata object for the leg file|
|»» task_id|string(uuid)|false|none|The task id of the leg that corresponds to the leg file|

#### Enumerated Values

|Property|Value|
|---|---|
|type|other|
|type|comm-invoice|
|type|pod|
|type|pop|
|type|pod-sig|
|type|pop-sig|
|type|carrier-invoice|
|type|smc|
|type|bol|

<aside class="success">
This operation does not require authentication
</aside>

## updateUploadedFileByLegAndFileID

<a id="opIdupdateUploadedFileByLegAndFileID"></a>

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
const fetch = require('node-fetch');
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"multipart/form-data"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://platform.roserocket.com/v1/legs/{legID}/upload_file/{fileID}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /legs/{legID}/upload_file/{fileID}`

*Update an uploaded file for a specified leg*

> Body parameter

```yaml
file: string
type: other

```

<h3 id="updateuploadedfilebylegandfileid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|legID|path|string|true|ID of the leg to get files for. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.|
|fileID|path|string|true|ID of the leg file.|
|body|body|[uploadLegFileByLegID](#schemauploadlegfilebylegid)|false|none|
|» file|body|string(binary)|true|File to upload|
|» type|body|string|true|Type of leg file to upload|

#### Enumerated Values

|Parameter|Value|
|---|---|
|» type|other|
|» type|comm-invoice|
|» type|pod|
|» type|pop|
|» type|pod-sig|
|» type|pop-sig|
|» type|carrier-invoice|
|» type|smc|
|» type|bol|

> Example responses

> 200 Response

```json
{
  "leg_file": {
    "id": "string",
    "created_at": "2019-02-21T15:32:17Z",
    "updated_at": "2019-02-21T15:32:17Z",
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

<h3 id="updateuploadedfilebylegandfileid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="updateuploadedfilebylegandfileid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» leg_file|[LegFile](#schemalegfile)|false|none|The file for the leg|
|»» id|string(uuid)|false|none|The uuid for the leg file|
|»» created_at|string(date-time)|false|none|The timestamp for the creation of the leg file|
|»» updated_at|string(date-time)|false|none|The timestamp for the last update of the leg file|
|»» org_id|string(uuid)|false|none|The uuid for the organization of the leg file|
|»» leg_id|string(uuid)|false|none|The uuid of the leg corresponding to the leg file|
|»» uploaded_by|string(uuid)|false|none|The uuid of the user who uploaded the leg file|
|»» uploaded_at|string(uuid)|false|none|The uuid|
|»» type|string|false|none|The type of leg file|
|»» url|string|false|none|The url location for the leg file|
|»» description|string|false|none|A description of the leg file|
|»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» metadata|object|false|none|Metadata object for the leg file|
|»» task_id|string(uuid)|false|none|The task id of the leg that corresponds to the leg file|

#### Enumerated Values

|Property|Value|
|---|---|
|type|other|
|type|comm-invoice|
|type|pod|
|type|pop|
|type|pod-sig|
|type|pop-sig|
|type|carrier-invoice|
|type|smc|
|type|bol|

<aside class="success">
This operation does not require authentication
</aside>

## getLegsByOrder

<a id="opIdgetLegsByOrder"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/orders/{orderID}/legs \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://platform.roserocket.com/v1/orders/{orderID}/legs HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://platform.roserocket.com/v1/orders/{orderID}/legs',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://platform.roserocket.com/v1/orders/{orderID}/legs", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /orders/{orderID}/legs`

*Get legs by order ID*

<h3 id="getlegsbyorder-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|orderID|path|string|true|ID of the order. It could also be the external ID of the order, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the order's external ID is __test123__ then the value of orderID should be __ext:test1234__ or __external_id:test1234__.|

> Example responses

> 200 Response

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
      "origin_start_at": "2019-02-21T15:32:17Z",
      "origin_end_at": "2019-02-21T15:32:17Z",
      "origin_appt_start_at": "2019-02-21T15:32:17Z",
      "origin_appt_end_at": "2019-02-21T15:32:17Z",
      "destination_start_at": "2019-02-21T15:32:17Z",
      "destination_end_at": "2019-02-21T15:32:17Z",
      "destination_appt_start_at": "2019-02-21T15:32:17Z",
      "destination_appt_end_at": "2019-02-21T15:32:17Z",
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
        "origin_arrived_at": "2019-02-21T15:32:17Z",
        "origin_in_at": "2019-02-21T15:32:17Z",
        "origin_pickedup_at": "2019-02-21T15:32:17Z",
        "origin_out_at": "2019-02-21T15:32:17Z",
        "destination_arrived_at": "2019-02-21T15:32:17Z",
        "destination_in_at": "2019-02-21T15:32:17Z",
        "destination_delivered_at": "2019-02-21T15:32:17Z",
        "destination_out_at": "2019-02-21T15:32:17Z"
      }
    }
  ]
}
```

<h3 id="getlegsbyorder-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="getlegsbyorder-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» legs|[[Leg](#schemaleg)]|false|none|[Leg]|
|»» id|string(uuid)|false|read-only|Auto generated system ID|
|»» sequence_id|integer|false|read-only|Auto generated sequence ID per customer|
|»» version|integer|false|read-only|Auto generated version number (incremental)|
|»» external_id|string|false|none|External ID for mapping the leg to an external system. This field value can be _null_|
|»» public_id|string|false|read-only|Auto generated human readable ID|
|»» order_id|string|false|read-only|Related order ID|
|»» manifest_id|string|false|none|Related manifest ID (assigned). This field value can be _null_|
|»» origin_stop_id|string|false|read-only|Stop ID of the origin (only if this leg has been assigned to a manifest). This field value can be _null_|
|»» destination_stop_id|string|false|read-only|Stop ID of the destination (only if this leg has been assigned to a manifest). This field value can be _null_|
|»» origin|[LegAddress](#schemalegaddress)|false|none|Leg address|
|»»» terminal_id|string(uuid)|false|none|Related terminal ID. This field value can be _null_|
|»»» org_name|string|false|none|Organization name|
|»»» contact_name|string|false|none|Contact name|
|»»» address_1|string|false|none|Address line 1|
|»»» address_2|string|false|none|Address line 2|
|»»» suite|string|false|none|Suite number|
|»»» city|string|false|none|City|
|»»» state|string|false|none|State / Province|
|»»» country|string|false|none|Country (2 letter ISO)|
|»»» postal|string|false|none|Postal / Zip code|
|»»» phone|string|false|none|Phone number|
|»»» phone_ext|string|false|none|Phone extension|
|»»» email|string|false|none|Email|
|»»» fax|string|false|none|Fax|
|»»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» destination|[LegAddress](#schemalegaddress)|false|none|Leg address|
|»» status|string|false|read-only|Leg Status|
|»» origin_start_at|string(date-time)|false|none|Origin ready time range (start)|
|»» origin_end_at|string(date-time)|false|none|Origin ready time range (end)|
|»» origin_appt_start_at|string(date-time)|false|none|Origin appointment time range (start). This field value can be _null_|
|»» origin_appt_end_at|string(date-time)|false|none|Origin appointment time range (end). This field value can be _null_|
|»» destination_start_at|string(date-time)|false|none|Destination expected time range (start). This field value can be _null_|
|»» destination_end_at|string(date-time)|false|none|Destination expected time range (end). This field value can be _null_|
|»» destination_appt_start_at|string(date-time)|false|none|Destination appointment time range (start). This field value can be _null_|
|»» destination_appt_end_at|string(date-time)|false|none|Destination appointment time range (end). This field value can be _null_|
|»» commodities|[[Commodity](#schemacommodity)]|false|none|Commodities items|
|»»» id|string(uuid)|false|read-only|Auto generated commodity id|
|»»» measurement_unit|string|false|none|Measurement unit|
|»»» weight_unit|string|false|none|Weight unit|
|»»» freight_class|string|false|none|Freight class|
|»»» commodity_type|string|false|none|Commodity type|
|»»» commodity_type_other|string|false|none|If commodity type is set to _other_, then this field must have value|
|»»» description|string|false|none|Description of the commodity|
|»»» feet|number(float)|false|none|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_|
|»»» volume|number(float)|false|none|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_|
|»»» length|number(float)|false|none|Length of the commodity|
|»»» width|number(float)|false|none|Width of the commodity|
|»»» height|number(float)|false|none|Height of the commodity|
|»»» weight|number(float)|false|none|Weight of the commodity|
|»»» nmfc|string|false|none|NMFC number|
|»»» is_stackable|boolean|false|none|Is this commodity can be stacked?|
|»»» quantity|integer|false|none|Quantity of the commodity|
|»»» pieces|integer|false|none|Total number of pieces. This field value can be _null_|
|»»» sku|string|false|none|SKU number|
|»» accessorials|[string]|false|none|none|
|»» history|[LegHistory](#schemaleghistory)|false|read-only|Historical timestamps of a leg|
|»»» origin_arrived_at|string(date-time)|false|none|The timestamp of when the driver/partner arrived at origin|
|»»» origin_in_at|string(date-time)|false|none|The timestamp of when the driver/partner in at origin|
|»»» origin_pickedup_at|string(date-time)|false|none|The timestamp of when the driver/partner picked up at origin|
|»»» origin_out_at|string(date-time)|false|none|The timestamp of when the driver/partner out at origin|
|»»» destination_arrived_at|string(date-time)|false|none|The timestamp of when the driver/partner arrived at destination|
|»»» destination_in_at|string(date-time)|false|none|The timestamp of when the driver/partner in at destination|
|»»» destination_delivered_at|string(date-time)|false|none|The timestamp of when the driver/partner delievered up at destination|
|»»» destination_out_at|string(date-time)|false|none|The timestamp of when the driver/partner out at destination|

#### Enumerated Values

|Property|Value|
|---|---|
|status|available|
|status|pending|
|status|dispatched|
|status|arrived_origin|
|status|in_origin|
|status|loaded|
|status|departed_origin|
|status|arrived_destination|
|status|in_destination|
|status|unloaded|
|status|departed_destination|
|status|cancelled|
|status|problem|
|measurement_unit|inch|
|measurement_unit|cm|
|weight_unit|lb|
|weight_unit|kg|
|commodity_type|skid|
|commodity_type|other|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: legs )
</aside>

## getLegByID

<a id="opIdgetLegByID"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/legs/{legID} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://platform.roserocket.com/v1/legs/{legID} HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://platform.roserocket.com/v1/legs/{legID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://platform.roserocket.com/v1/legs/{legID}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /legs/{legID}`

*Get leg by ID*

<h3 id="getlegbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|legID|path|string|true|ID of the leg. It could also be the external ID of the leg, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the leg's external ID is __test123__ then the value of legID should be __ext:test1234__ or __external_id:test1234__.|

> Example responses

> 200 Response

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
    "origin_start_at": "2019-02-21T15:32:17Z",
    "origin_end_at": "2019-02-21T15:32:17Z",
    "origin_appt_start_at": "2019-02-21T15:32:17Z",
    "origin_appt_end_at": "2019-02-21T15:32:17Z",
    "destination_start_at": "2019-02-21T15:32:17Z",
    "destination_end_at": "2019-02-21T15:32:17Z",
    "destination_appt_start_at": "2019-02-21T15:32:17Z",
    "destination_appt_end_at": "2019-02-21T15:32:17Z",
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
      "origin_arrived_at": "2019-02-21T15:32:17Z",
      "origin_in_at": "2019-02-21T15:32:17Z",
      "origin_pickedup_at": "2019-02-21T15:32:17Z",
      "origin_out_at": "2019-02-21T15:32:17Z",
      "destination_arrived_at": "2019-02-21T15:32:17Z",
      "destination_in_at": "2019-02-21T15:32:17Z",
      "destination_delivered_at": "2019-02-21T15:32:17Z",
      "destination_out_at": "2019-02-21T15:32:17Z"
    }
  }
}
```

<h3 id="getlegbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="getlegbyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» leg|[Leg](#schemaleg)|false|none|Leg|
|»» id|string(uuid)|false|read-only|Auto generated system ID|
|»» sequence_id|integer|false|read-only|Auto generated sequence ID per customer|
|»» version|integer|false|read-only|Auto generated version number (incremental)|
|»» external_id|string|false|none|External ID for mapping the leg to an external system. This field value can be _null_|
|»» public_id|string|false|read-only|Auto generated human readable ID|
|»» order_id|string|false|read-only|Related order ID|
|»» manifest_id|string|false|none|Related manifest ID (assigned). This field value can be _null_|
|»» origin_stop_id|string|false|read-only|Stop ID of the origin (only if this leg has been assigned to a manifest). This field value can be _null_|
|»» destination_stop_id|string|false|read-only|Stop ID of the destination (only if this leg has been assigned to a manifest). This field value can be _null_|
|»» origin|[LegAddress](#schemalegaddress)|false|none|Leg address|
|»»» terminal_id|string(uuid)|false|none|Related terminal ID. This field value can be _null_|
|»»» org_name|string|false|none|Organization name|
|»»» contact_name|string|false|none|Contact name|
|»»» address_1|string|false|none|Address line 1|
|»»» address_2|string|false|none|Address line 2|
|»»» suite|string|false|none|Suite number|
|»»» city|string|false|none|City|
|»»» state|string|false|none|State / Province|
|»»» country|string|false|none|Country (2 letter ISO)|
|»»» postal|string|false|none|Postal / Zip code|
|»»» phone|string|false|none|Phone number|
|»»» phone_ext|string|false|none|Phone extension|
|»»» email|string|false|none|Email|
|»»» fax|string|false|none|Fax|
|»»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» destination|[LegAddress](#schemalegaddress)|false|none|Leg address|
|»» status|string|false|read-only|Leg Status|
|»» origin_start_at|string(date-time)|false|none|Origin ready time range (start)|
|»» origin_end_at|string(date-time)|false|none|Origin ready time range (end)|
|»» origin_appt_start_at|string(date-time)|false|none|Origin appointment time range (start). This field value can be _null_|
|»» origin_appt_end_at|string(date-time)|false|none|Origin appointment time range (end). This field value can be _null_|
|»» destination_start_at|string(date-time)|false|none|Destination expected time range (start). This field value can be _null_|
|»» destination_end_at|string(date-time)|false|none|Destination expected time range (end). This field value can be _null_|
|»» destination_appt_start_at|string(date-time)|false|none|Destination appointment time range (start). This field value can be _null_|
|»» destination_appt_end_at|string(date-time)|false|none|Destination appointment time range (end). This field value can be _null_|
|»» commodities|[[Commodity](#schemacommodity)]|false|none|Commodities items|
|»»» id|string(uuid)|false|read-only|Auto generated commodity id|
|»»» measurement_unit|string|false|none|Measurement unit|
|»»» weight_unit|string|false|none|Weight unit|
|»»» freight_class|string|false|none|Freight class|
|»»» commodity_type|string|false|none|Commodity type|
|»»» commodity_type_other|string|false|none|If commodity type is set to _other_, then this field must have value|
|»»» description|string|false|none|Description of the commodity|
|»»» feet|number(float)|false|none|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_|
|»»» volume|number(float)|false|none|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_|
|»»» length|number(float)|false|none|Length of the commodity|
|»»» width|number(float)|false|none|Width of the commodity|
|»»» height|number(float)|false|none|Height of the commodity|
|»»» weight|number(float)|false|none|Weight of the commodity|
|»»» nmfc|string|false|none|NMFC number|
|»»» is_stackable|boolean|false|none|Is this commodity can be stacked?|
|»»» quantity|integer|false|none|Quantity of the commodity|
|»»» pieces|integer|false|none|Total number of pieces. This field value can be _null_|
|»»» sku|string|false|none|SKU number|
|»» accessorials|[string]|false|none|none|
|»» history|[LegHistory](#schemaleghistory)|false|read-only|Historical timestamps of a leg|
|»»» origin_arrived_at|string(date-time)|false|none|The timestamp of when the driver/partner arrived at origin|
|»»» origin_in_at|string(date-time)|false|none|The timestamp of when the driver/partner in at origin|
|»»» origin_pickedup_at|string(date-time)|false|none|The timestamp of when the driver/partner picked up at origin|
|»»» origin_out_at|string(date-time)|false|none|The timestamp of when the driver/partner out at origin|
|»»» destination_arrived_at|string(date-time)|false|none|The timestamp of when the driver/partner arrived at destination|
|»»» destination_in_at|string(date-time)|false|none|The timestamp of when the driver/partner in at destination|
|»»» destination_delivered_at|string(date-time)|false|none|The timestamp of when the driver/partner delievered up at destination|
|»»» destination_out_at|string(date-time)|false|none|The timestamp of when the driver/partner out at destination|

#### Enumerated Values

|Property|Value|
|---|---|
|status|available|
|status|pending|
|status|dispatched|
|status|arrived_origin|
|status|in_origin|
|status|loaded|
|status|departed_origin|
|status|arrived_destination|
|status|in_destination|
|status|unloaded|
|status|departed_destination|
|status|cancelled|
|status|problem|
|measurement_unit|inch|
|measurement_unit|cm|
|weight_unit|lb|
|weight_unit|kg|
|commodity_type|skid|
|commodity_type|other|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: legs )
</aside>

<h1 id="rose-rocket-platform-rest-api-manifest">manifest</h1>

## getManifestByID

<a id="opIdgetManifestByID"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/manifests/{manifestID} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://platform.roserocket.com/v1/manifests/{manifestID} HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://platform.roserocket.com/v1/manifests/{manifestID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://platform.roserocket.com/v1/manifests/{manifestID}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /manifests/{manifestID}`

*Get manifest by ID*

<h3 id="getmanifestbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|manifestID|path|string|true|ID of the manifest. It could also be the external ID of the manifest, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the manifest's external ID is __test123__ then the value of manifestID should be __ext:test1234__ or __external_id:test1234__.|

> Example responses

> 200 Response

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
    "start_at": "2019-02-21T15:32:17Z",
    "status": "planning",
    "dispatched_at": "2019-02-21T15:32:17Z",
    "completed_at": "2019-02-21T15:32:17Z"
  }
}
```

<h3 id="getmanifestbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="getmanifestbyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» manifest|[Manifest](#schemamanifest)|false|none|none|
|»» id|string(uuid)|false|none|Id of the manifest|
|»» nickname|string|false|none|The nickname for the manifest|
|»» org_id|string(uuid)|false|none|Id of the organization to which the manifest belongs|
|»» vehicle_id|string(uuid)|false|none|Id of the vehicle corresponding to the manifest|
|»» dispathcer_user_id|string(uuid)|false|none|Id of the dispatcher of the manifest|
|»» driver_user_id|string(uuid)|false|none|Id of the driver corresponding to the manifest|
|»» trailer_id|string(uuid)|false|none|Id of the trailer corresponding to the manifest|
|»» partner_carrier_id|string(uuid)|false|none|Id of the partner/carrier that corresponds to the manifest|
|»» partner_carrier_service_id|string(uuid)|false|none|Id of the partner/carrier service that corresponds to the manifest|
|»» sequential_id|string(uuid)|false|none|The manifest's sequential id|
|»» full_id|string(uuid)|false|none|The full id of the string|
|»» start_at|string(date-time)|false|none|The time at which the manifest was scheduled to start|
|»» status|string|false|none|The status of the manifest|
|»» dispatched_at|string(date-time)|false|none|The time at which the manifest was dispatched|
|»» completed_at|string(date-time)|false|none|The time at which the manifest was completed|

#### Enumerated Values

|Property|Value|
|---|---|
|status|planning|
|status|planned|
|status|cancelled|
|status|assigned|
|status|accepted|
|status|rejected|
|status|problem|
|status|completed|
|status|bill-created|
|status|bill-sent|
|status|bill-paid|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: manifests )
</aside>

## createManifest

<a id="opIdcreateManifest"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/manifests \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://platform.roserocket.com/v1/manifests HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/manifests',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
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
    "start_at": "2019-02-21T15:32:17Z",
    "status": "planning",
    "dispatched_at": "2019-02-21T15:32:17Z",
    "completed_at": "2019-02-21T15:32:17Z"
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://platform.roserocket.com/v1/manifests',
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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://platform.roserocket.com/v1/manifests',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://platform.roserocket.com/v1/manifests', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://platform.roserocket.com/v1/manifests");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/manifests", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /manifests`

*Create a new manifest*

> Body parameter

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
    "start_at": "2019-02-21T15:32:17Z",
    "status": "planning",
    "dispatched_at": "2019-02-21T15:32:17Z",
    "completed_at": "2019-02-21T15:32:17Z"
  }
}
```

<h3 id="createmanifest-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|Manifest create object|
|» manifest|body|[Manifest](#schemamanifest)|false|none|
|»» id|body|string(uuid)|false|Id of the manifest|
|»» nickname|body|string|false|The nickname for the manifest|
|»» org_id|body|string(uuid)|false|Id of the organization to which the manifest belongs|
|»» vehicle_id|body|string(uuid)|false|Id of the vehicle corresponding to the manifest|
|»» dispathcer_user_id|body|string(uuid)|false|Id of the dispatcher of the manifest|
|»» driver_user_id|body|string(uuid)|false|Id of the driver corresponding to the manifest|
|»» trailer_id|body|string(uuid)|false|Id of the trailer corresponding to the manifest|
|»» partner_carrier_id|body|string(uuid)|false|Id of the partner/carrier that corresponds to the manifest|
|»» partner_carrier_service_id|body|string(uuid)|false|Id of the partner/carrier service that corresponds to the manifest|
|»» sequential_id|body|string(uuid)|false|The manifest's sequential id|
|»» full_id|body|string(uuid)|false|The full id of the string|
|»» start_at|body|string(date-time)|false|The time at which the manifest was scheduled to start|
|»» status|body|string|false|The status of the manifest|
|»» dispatched_at|body|string(date-time)|false|The time at which the manifest was dispatched|
|»» completed_at|body|string(date-time)|false|The time at which the manifest was completed|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»» status|planning|
|»» status|planned|
|»» status|cancelled|
|»» status|assigned|
|»» status|accepted|
|»» status|rejected|
|»» status|problem|
|»» status|completed|
|»» status|bill-created|
|»» status|bill-sent|
|»» status|bill-paid|

> Example responses

> 200 Response

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
    "start_at": "2019-02-21T15:32:17Z",
    "status": "planning",
    "dispatched_at": "2019-02-21T15:32:17Z",
    "completed_at": "2019-02-21T15:32:17Z"
  }
}
```

<h3 id="createmanifest-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="createmanifest-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» manifest|[Manifest](#schemamanifest)|false|none|none|
|»» id|string(uuid)|false|none|Id of the manifest|
|»» nickname|string|false|none|The nickname for the manifest|
|»» org_id|string(uuid)|false|none|Id of the organization to which the manifest belongs|
|»» vehicle_id|string(uuid)|false|none|Id of the vehicle corresponding to the manifest|
|»» dispathcer_user_id|string(uuid)|false|none|Id of the dispatcher of the manifest|
|»» driver_user_id|string(uuid)|false|none|Id of the driver corresponding to the manifest|
|»» trailer_id|string(uuid)|false|none|Id of the trailer corresponding to the manifest|
|»» partner_carrier_id|string(uuid)|false|none|Id of the partner/carrier that corresponds to the manifest|
|»» partner_carrier_service_id|string(uuid)|false|none|Id of the partner/carrier service that corresponds to the manifest|
|»» sequential_id|string(uuid)|false|none|The manifest's sequential id|
|»» full_id|string(uuid)|false|none|The full id of the string|
|»» start_at|string(date-time)|false|none|The time at which the manifest was scheduled to start|
|»» status|string|false|none|The status of the manifest|
|»» dispatched_at|string(date-time)|false|none|The time at which the manifest was dispatched|
|»» completed_at|string(date-time)|false|none|The time at which the manifest was completed|

#### Enumerated Values

|Property|Value|
|---|---|
|status|planning|
|status|planned|
|status|cancelled|
|status|assigned|
|status|accepted|
|status|rejected|
|status|problem|
|status|completed|
|status|bill-created|
|status|bill-sent|
|status|bill-paid|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: manifests )
</aside>

## assignDriverToManifest

<a id="opIdassignDriverToManifest"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/manifests/{manifestID}/assign_driver \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://platform.roserocket.com/v1/manifests/{manifestID}/assign_driver HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/manifests/{manifestID}/assign_driver',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "driver_user_id": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://platform.roserocket.com/v1/manifests/{manifestID}/assign_driver',
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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://platform.roserocket.com/v1/manifests/{manifestID}/assign_driver',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://platform.roserocket.com/v1/manifests/{manifestID}/assign_driver', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://platform.roserocket.com/v1/manifests/{manifestID}/assign_driver");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/manifests/{manifestID}/assign_driver", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /manifests/{manifestID}/assign_driver`

*Assign a driver to a manifest*

> Body parameter

```json
{
  "driver_user_id": "string"
}
```

<h3 id="assigndrivertomanifest-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|manifestID|path|string|true|ID of the manifest. It could also be the external ID of the manifest, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the manifest's external ID is __test123__ then the value of manifestID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|object|true|Assign manifest driver request object|
|» driver_user_id|body|string(uuid)|false|none|

> Example responses

> 200 Response

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
    "start_at": "2019-02-21T15:32:17Z",
    "status": "planning",
    "dispatched_at": "2019-02-21T15:32:17Z",
    "completed_at": "2019-02-21T15:32:17Z"
  },
  "driver_user_name": "string"
}
```

<h3 id="assigndrivertomanifest-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="assigndrivertomanifest-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» manifest|[Manifest](#schemamanifest)|false|none|none|
|»» id|string(uuid)|false|none|Id of the manifest|
|»» nickname|string|false|none|The nickname for the manifest|
|»» org_id|string(uuid)|false|none|Id of the organization to which the manifest belongs|
|»» vehicle_id|string(uuid)|false|none|Id of the vehicle corresponding to the manifest|
|»» dispathcer_user_id|string(uuid)|false|none|Id of the dispatcher of the manifest|
|»» driver_user_id|string(uuid)|false|none|Id of the driver corresponding to the manifest|
|»» trailer_id|string(uuid)|false|none|Id of the trailer corresponding to the manifest|
|»» partner_carrier_id|string(uuid)|false|none|Id of the partner/carrier that corresponds to the manifest|
|»» partner_carrier_service_id|string(uuid)|false|none|Id of the partner/carrier service that corresponds to the manifest|
|»» sequential_id|string(uuid)|false|none|The manifest's sequential id|
|»» full_id|string(uuid)|false|none|The full id of the string|
|»» start_at|string(date-time)|false|none|The time at which the manifest was scheduled to start|
|»» status|string|false|none|The status of the manifest|
|»» dispatched_at|string(date-time)|false|none|The time at which the manifest was dispatched|
|»» completed_at|string(date-time)|false|none|The time at which the manifest was completed|
|» driver_user_name|string(uuid)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|planning|
|status|planned|
|status|cancelled|
|status|assigned|
|status|accepted|
|status|rejected|
|status|problem|
|status|completed|
|status|bill-created|
|status|bill-sent|
|status|bill-paid|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: manifests )
</aside>

## assignCarrierToManifest

<a id="opIdassignCarrierToManifest"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/manifests/{manifestID}/assign_carrier \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://platform.roserocket.com/v1/manifests/{manifestID}/assign_carrier HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/manifests/{manifestID}/assign_carrier',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "partner_carrier_id": "string",
  "service_id": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://platform.roserocket.com/v1/manifests/{manifestID}/assign_carrier',
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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://platform.roserocket.com/v1/manifests/{manifestID}/assign_carrier',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://platform.roserocket.com/v1/manifests/{manifestID}/assign_carrier', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://platform.roserocket.com/v1/manifests/{manifestID}/assign_carrier");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/manifests/{manifestID}/assign_carrier", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /manifests/{manifestID}/assign_carrier`

*Assign a carrier to a manifest*

> Body parameter

```json
{
  "partner_carrier_id": "string",
  "service_id": "string"
}
```

<h3 id="assigncarriertomanifest-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|manifestID|path|string|true|ID of the manifest. It could also be the external ID of the manifest, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the manifest's external ID is __test123__ then the value of manifestID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|object|true|Assign manifest carrier request object|
|» partner_carrier_id|body|string(uuid)|false|none|
|» service_id|body|string(uuid)|false|none|

> Example responses

> 200 Response

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
    "start_at": "2019-02-21T15:32:17Z",
    "status": "planning",
    "dispatched_at": "2019-02-21T15:32:17Z",
    "completed_at": "2019-02-21T15:32:17Z"
  },
  "partner_carrier_id": "string",
  "service_id": "string"
}
```

<h3 id="assigncarriertomanifest-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="assigncarriertomanifest-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» manifest|[Manifest](#schemamanifest)|false|none|none|
|»» id|string(uuid)|false|none|Id of the manifest|
|»» nickname|string|false|none|The nickname for the manifest|
|»» org_id|string(uuid)|false|none|Id of the organization to which the manifest belongs|
|»» vehicle_id|string(uuid)|false|none|Id of the vehicle corresponding to the manifest|
|»» dispathcer_user_id|string(uuid)|false|none|Id of the dispatcher of the manifest|
|»» driver_user_id|string(uuid)|false|none|Id of the driver corresponding to the manifest|
|»» trailer_id|string(uuid)|false|none|Id of the trailer corresponding to the manifest|
|»» partner_carrier_id|string(uuid)|false|none|Id of the partner/carrier that corresponds to the manifest|
|»» partner_carrier_service_id|string(uuid)|false|none|Id of the partner/carrier service that corresponds to the manifest|
|»» sequential_id|string(uuid)|false|none|The manifest's sequential id|
|»» full_id|string(uuid)|false|none|The full id of the string|
|»» start_at|string(date-time)|false|none|The time at which the manifest was scheduled to start|
|»» status|string|false|none|The status of the manifest|
|»» dispatched_at|string(date-time)|false|none|The time at which the manifest was dispatched|
|»» completed_at|string(date-time)|false|none|The time at which the manifest was completed|
|» partner_carrier_id|string(uuid)|false|none|none|
|» service_id|string(uuid)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|planning|
|status|planned|
|status|cancelled|
|status|assigned|
|status|accepted|
|status|rejected|
|status|problem|
|status|completed|
|status|bill-created|
|status|bill-sent|
|status|bill-paid|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: manifests )
</aside>

## dispatchManifestToCarrier

<a id="opIddispatchManifestToCarrier"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/manifests/{manifestID}/dispatch_to_carrier \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://platform.roserocket.com/v1/manifests/{manifestID}/dispatch_to_carrier HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/manifests/{manifestID}/dispatch_to_carrier',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "from": "string",
  "cc": "string",
  "subject": "string",
  "to": "string",
  "message": "string",
  "copy_to_myself": "string",
  "include_as_attachment": "string",
  "attach_rate_confirmation": "string",
  "attach_bol": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://platform.roserocket.com/v1/manifests/{manifestID}/dispatch_to_carrier',
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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://platform.roserocket.com/v1/manifests/{manifestID}/dispatch_to_carrier',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://platform.roserocket.com/v1/manifests/{manifestID}/dispatch_to_carrier', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://platform.roserocket.com/v1/manifests/{manifestID}/dispatch_to_carrier");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/manifests/{manifestID}/dispatch_to_carrier", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /manifests/{manifestID}/dispatch_to_carrier`

*Dispatch a manifest to a carrier*

> Body parameter

```json
{
  "from": "string",
  "cc": "string",
  "subject": "string",
  "to": "string",
  "message": "string",
  "copy_to_myself": "string",
  "include_as_attachment": "string",
  "attach_rate_confirmation": "string",
  "attach_bol": "string"
}
```

<h3 id="dispatchmanifesttocarrier-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|manifestID|path|string|true|ID of the manifest. It could also be the external ID of the manifest, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the manifest's external ID is __test123__ then the value of manifestID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|object|true|Dispatch to carrier request|
|» from|body|string|false|none|
|» cc|body|string|false|none|
|» subject|body|string|false|none|
|» to|body|string|false|none|
|» message|body|string|false|none|
|» copy_to_myself|body|string|false|none|
|» include_as_attachment|body|string|false|none|
|» attach_rate_confirmation|body|string|false|none|
|» attach_bol|body|string|false|none|

> Example responses

> 200 Response

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
    "start_at": "2019-02-21T15:32:17Z",
    "status": "planning",
    "dispatched_at": "2019-02-21T15:32:17Z",
    "completed_at": "2019-02-21T15:32:17Z"
  },
  "partner_carrier_id": "string",
  "service_id": "string"
}
```

<h3 id="dispatchmanifesttocarrier-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="dispatchmanifesttocarrier-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» manifest|[Manifest](#schemamanifest)|false|none|none|
|»» id|string(uuid)|false|none|Id of the manifest|
|»» nickname|string|false|none|The nickname for the manifest|
|»» org_id|string(uuid)|false|none|Id of the organization to which the manifest belongs|
|»» vehicle_id|string(uuid)|false|none|Id of the vehicle corresponding to the manifest|
|»» dispathcer_user_id|string(uuid)|false|none|Id of the dispatcher of the manifest|
|»» driver_user_id|string(uuid)|false|none|Id of the driver corresponding to the manifest|
|»» trailer_id|string(uuid)|false|none|Id of the trailer corresponding to the manifest|
|»» partner_carrier_id|string(uuid)|false|none|Id of the partner/carrier that corresponds to the manifest|
|»» partner_carrier_service_id|string(uuid)|false|none|Id of the partner/carrier service that corresponds to the manifest|
|»» sequential_id|string(uuid)|false|none|The manifest's sequential id|
|»» full_id|string(uuid)|false|none|The full id of the string|
|»» start_at|string(date-time)|false|none|The time at which the manifest was scheduled to start|
|»» status|string|false|none|The status of the manifest|
|»» dispatched_at|string(date-time)|false|none|The time at which the manifest was dispatched|
|»» completed_at|string(date-time)|false|none|The time at which the manifest was completed|
|» partner_carrier_id|string(uuid)|false|none|none|
|» service_id|string(uuid)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|planning|
|status|planned|
|status|cancelled|
|status|assigned|
|status|accepted|
|status|rejected|
|status|problem|
|status|completed|
|status|bill-created|
|status|bill-sent|
|status|bill-paid|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: manifests )
</aside>

## assignAndDispatchManifestToCarrier

<a id="opIdassignAndDispatchManifestToCarrier"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/manifests/{manifestID}/assign_and_dispatch_to_carrier \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://platform.roserocket.com/v1/manifests/{manifestID}/assign_and_dispatch_to_carrier HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/manifests/{manifestID}/assign_and_dispatch_to_carrier',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "dispatch_request": {
    "from": "string",
    "cc": "string",
    "subject": "string",
    "to": "string",
    "message": "string",
    "copy_to_myself": "string",
    "include_as_attachment": "string",
    "attach_rate_confirmation": "string",
    "attach_bol": "string"
  },
  "partner_carrier_id": "string",
  "service_id": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://platform.roserocket.com/v1/manifests/{manifestID}/assign_and_dispatch_to_carrier',
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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://platform.roserocket.com/v1/manifests/{manifestID}/assign_and_dispatch_to_carrier',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://platform.roserocket.com/v1/manifests/{manifestID}/assign_and_dispatch_to_carrier', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://platform.roserocket.com/v1/manifests/{manifestID}/assign_and_dispatch_to_carrier");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/manifests/{manifestID}/assign_and_dispatch_to_carrier", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /manifests/{manifestID}/assign_and_dispatch_to_carrier`

*Dispatch a manifest to a carrier*

> Body parameter

```json
{
  "dispatch_request": {
    "from": "string",
    "cc": "string",
    "subject": "string",
    "to": "string",
    "message": "string",
    "copy_to_myself": "string",
    "include_as_attachment": "string",
    "attach_rate_confirmation": "string",
    "attach_bol": "string"
  },
  "partner_carrier_id": "string",
  "service_id": "string"
}
```

<h3 id="assignanddispatchmanifesttocarrier-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|manifestID|path|string|true|ID of the manifest. It could also be the external ID of the manifest, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the manifest's external ID is __test123__ then the value of manifestID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|object|true|Dispatch to carrier request|
|» dispatch_request|body|object|false|none|
|»» from|body|string|false|none|
|»» cc|body|string|false|none|
|»» subject|body|string|false|none|
|»» to|body|string|false|none|
|»» message|body|string|false|none|
|»» copy_to_myself|body|string|false|none|
|»» include_as_attachment|body|string|false|none|
|»» attach_rate_confirmation|body|string|false|none|
|»» attach_bol|body|string|false|none|
|» partner_carrier_id|body|string(uuid)|false|none|
|» service_id|body|string(uuid)|false|none|

> Example responses

> 200 Response

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
    "start_at": "2019-02-21T15:32:17Z",
    "status": "planning",
    "dispatched_at": "2019-02-21T15:32:17Z",
    "completed_at": "2019-02-21T15:32:17Z"
  },
  "partner_carrier_id": "string",
  "service_id": "string"
}
```

<h3 id="assignanddispatchmanifesttocarrier-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="assignanddispatchmanifesttocarrier-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» manifest|[Manifest](#schemamanifest)|false|none|none|
|»» id|string(uuid)|false|none|Id of the manifest|
|»» nickname|string|false|none|The nickname for the manifest|
|»» org_id|string(uuid)|false|none|Id of the organization to which the manifest belongs|
|»» vehicle_id|string(uuid)|false|none|Id of the vehicle corresponding to the manifest|
|»» dispathcer_user_id|string(uuid)|false|none|Id of the dispatcher of the manifest|
|»» driver_user_id|string(uuid)|false|none|Id of the driver corresponding to the manifest|
|»» trailer_id|string(uuid)|false|none|Id of the trailer corresponding to the manifest|
|»» partner_carrier_id|string(uuid)|false|none|Id of the partner/carrier that corresponds to the manifest|
|»» partner_carrier_service_id|string(uuid)|false|none|Id of the partner/carrier service that corresponds to the manifest|
|»» sequential_id|string(uuid)|false|none|The manifest's sequential id|
|»» full_id|string(uuid)|false|none|The full id of the string|
|»» start_at|string(date-time)|false|none|The time at which the manifest was scheduled to start|
|»» status|string|false|none|The status of the manifest|
|»» dispatched_at|string(date-time)|false|none|The time at which the manifest was dispatched|
|»» completed_at|string(date-time)|false|none|The time at which the manifest was completed|
|» partner_carrier_id|string(uuid)|false|none|none|
|» service_id|string(uuid)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|planning|
|status|planned|
|status|cancelled|
|status|assigned|
|status|accepted|
|status|rejected|
|status|problem|
|status|completed|
|status|bill-created|
|status|bill-sent|
|status|bill-paid|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: manifests )
</aside>

## getLegsByManifestID

<a id="opIdgetLegsByManifestID"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/manifests/{manifestID}/legs \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://platform.roserocket.com/v1/manifests/{manifestID}/legs HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://platform.roserocket.com/v1/manifests/{manifestID}/legs',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://platform.roserocket.com/v1/manifests/{manifestID}/legs", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /manifests/{manifestID}/legs`

*Get legs by manifest ID*

<h3 id="getlegsbymanifestid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|manifestID|path|string|true|ID of the manifest for which to get legs. It could also be the external ID of the manifest, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the manifest's external ID is __test123__ then the value of manifestID should be __ext:test1234__ or __external_id:test1234__.|

> Example responses

> 200 Response

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
      "origin_start_at": "2019-02-21T15:32:17Z",
      "origin_end_at": "2019-02-21T15:32:17Z",
      "origin_appt_start_at": "2019-02-21T15:32:17Z",
      "origin_appt_end_at": "2019-02-21T15:32:17Z",
      "destination_start_at": "2019-02-21T15:32:17Z",
      "destination_end_at": "2019-02-21T15:32:17Z",
      "destination_appt_start_at": "2019-02-21T15:32:17Z",
      "destination_appt_end_at": "2019-02-21T15:32:17Z",
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
        "origin_arrived_at": "2019-02-21T15:32:17Z",
        "origin_in_at": "2019-02-21T15:32:17Z",
        "origin_pickedup_at": "2019-02-21T15:32:17Z",
        "origin_out_at": "2019-02-21T15:32:17Z",
        "destination_arrived_at": "2019-02-21T15:32:17Z",
        "destination_in_at": "2019-02-21T15:32:17Z",
        "destination_delivered_at": "2019-02-21T15:32:17Z",
        "destination_out_at": "2019-02-21T15:32:17Z"
      }
    }
  ]
}
```

<h3 id="getlegsbymanifestid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="getlegsbymanifestid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» legs|[[Leg](#schemaleg)]|false|none|[Leg]|
|»» id|string(uuid)|false|read-only|Auto generated system ID|
|»» sequence_id|integer|false|read-only|Auto generated sequence ID per customer|
|»» version|integer|false|read-only|Auto generated version number (incremental)|
|»» external_id|string|false|none|External ID for mapping the leg to an external system. This field value can be _null_|
|»» public_id|string|false|read-only|Auto generated human readable ID|
|»» order_id|string|false|read-only|Related order ID|
|»» manifest_id|string|false|none|Related manifest ID (assigned). This field value can be _null_|
|»» origin_stop_id|string|false|read-only|Stop ID of the origin (only if this leg has been assigned to a manifest). This field value can be _null_|
|»» destination_stop_id|string|false|read-only|Stop ID of the destination (only if this leg has been assigned to a manifest). This field value can be _null_|
|»» origin|[LegAddress](#schemalegaddress)|false|none|Leg address|
|»»» terminal_id|string(uuid)|false|none|Related terminal ID. This field value can be _null_|
|»»» org_name|string|false|none|Organization name|
|»»» contact_name|string|false|none|Contact name|
|»»» address_1|string|false|none|Address line 1|
|»»» address_2|string|false|none|Address line 2|
|»»» suite|string|false|none|Suite number|
|»»» city|string|false|none|City|
|»»» state|string|false|none|State / Province|
|»»» country|string|false|none|Country (2 letter ISO)|
|»»» postal|string|false|none|Postal / Zip code|
|»»» phone|string|false|none|Phone number|
|»»» phone_ext|string|false|none|Phone extension|
|»»» email|string|false|none|Email|
|»»» fax|string|false|none|Fax|
|»»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» destination|[LegAddress](#schemalegaddress)|false|none|Leg address|
|»» status|string|false|read-only|Leg Status|
|»» origin_start_at|string(date-time)|false|none|Origin ready time range (start)|
|»» origin_end_at|string(date-time)|false|none|Origin ready time range (end)|
|»» origin_appt_start_at|string(date-time)|false|none|Origin appointment time range (start). This field value can be _null_|
|»» origin_appt_end_at|string(date-time)|false|none|Origin appointment time range (end). This field value can be _null_|
|»» destination_start_at|string(date-time)|false|none|Destination expected time range (start). This field value can be _null_|
|»» destination_end_at|string(date-time)|false|none|Destination expected time range (end). This field value can be _null_|
|»» destination_appt_start_at|string(date-time)|false|none|Destination appointment time range (start). This field value can be _null_|
|»» destination_appt_end_at|string(date-time)|false|none|Destination appointment time range (end). This field value can be _null_|
|»» commodities|[[Commodity](#schemacommodity)]|false|none|Commodities items|
|»»» id|string(uuid)|false|read-only|Auto generated commodity id|
|»»» measurement_unit|string|false|none|Measurement unit|
|»»» weight_unit|string|false|none|Weight unit|
|»»» freight_class|string|false|none|Freight class|
|»»» commodity_type|string|false|none|Commodity type|
|»»» commodity_type_other|string|false|none|If commodity type is set to _other_, then this field must have value|
|»»» description|string|false|none|Description of the commodity|
|»»» feet|number(float)|false|none|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_|
|»»» volume|number(float)|false|none|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_|
|»»» length|number(float)|false|none|Length of the commodity|
|»»» width|number(float)|false|none|Width of the commodity|
|»»» height|number(float)|false|none|Height of the commodity|
|»»» weight|number(float)|false|none|Weight of the commodity|
|»»» nmfc|string|false|none|NMFC number|
|»»» is_stackable|boolean|false|none|Is this commodity can be stacked?|
|»»» quantity|integer|false|none|Quantity of the commodity|
|»»» pieces|integer|false|none|Total number of pieces. This field value can be _null_|
|»»» sku|string|false|none|SKU number|
|»» accessorials|[string]|false|none|none|
|»» history|[LegHistory](#schemaleghistory)|false|read-only|Historical timestamps of a leg|
|»»» origin_arrived_at|string(date-time)|false|none|The timestamp of when the driver/partner arrived at origin|
|»»» origin_in_at|string(date-time)|false|none|The timestamp of when the driver/partner in at origin|
|»»» origin_pickedup_at|string(date-time)|false|none|The timestamp of when the driver/partner picked up at origin|
|»»» origin_out_at|string(date-time)|false|none|The timestamp of when the driver/partner out at origin|
|»»» destination_arrived_at|string(date-time)|false|none|The timestamp of when the driver/partner arrived at destination|
|»»» destination_in_at|string(date-time)|false|none|The timestamp of when the driver/partner in at destination|
|»»» destination_delivered_at|string(date-time)|false|none|The timestamp of when the driver/partner delievered up at destination|
|»»» destination_out_at|string(date-time)|false|none|The timestamp of when the driver/partner out at destination|

#### Enumerated Values

|Property|Value|
|---|---|
|status|available|
|status|pending|
|status|dispatched|
|status|arrived_origin|
|status|in_origin|
|status|loaded|
|status|departed_origin|
|status|arrived_destination|
|status|in_destination|
|status|unloaded|
|status|departed_destination|
|status|cancelled|
|status|problem|
|measurement_unit|inch|
|measurement_unit|cm|
|weight_unit|lb|
|weight_unit|kg|
|commodity_type|skid|
|commodity_type|other|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: manifests )
</aside>

## bulkAddLegsByManifestID

<a id="opIdbulkAddLegsByManifestID"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/manifests/{manifestID}/add_legs \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://platform.roserocket.com/v1/manifests/{manifestID}/add_legs HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/manifests/{manifestID}/add_legs',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "leg_ids": [
    "string"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://platform.roserocket.com/v1/manifests/{manifestID}/add_legs',
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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://platform.roserocket.com/v1/manifests/{manifestID}/add_legs',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://platform.roserocket.com/v1/manifests/{manifestID}/add_legs', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://platform.roserocket.com/v1/manifests/{manifestID}/add_legs");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/manifests/{manifestID}/add_legs", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /manifests/{manifestID}/add_legs`

*Bulk add legs to specified manifest*

> Body parameter

```json
{
  "leg_ids": [
    "string"
  ]
}
```

<h3 id="bulkaddlegsbymanifestid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|manifestID|path|string|true|ID of the manifest for which to add legs. It could also be the external ID of the manifest, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the manifest's external ID is __test123__ then the value of manifestID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|object|true|Add legs to manifest request object|
|» leg_ids|body|[string]|false|none|

> Example responses

> 200 Response

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
      "origin_start_at": "2019-02-21T15:32:17Z",
      "origin_end_at": "2019-02-21T15:32:17Z",
      "origin_appt_start_at": "2019-02-21T15:32:17Z",
      "origin_appt_end_at": "2019-02-21T15:32:17Z",
      "destination_start_at": "2019-02-21T15:32:17Z",
      "destination_end_at": "2019-02-21T15:32:17Z",
      "destination_appt_start_at": "2019-02-21T15:32:17Z",
      "destination_appt_end_at": "2019-02-21T15:32:17Z",
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
        "origin_arrived_at": "2019-02-21T15:32:17Z",
        "origin_in_at": "2019-02-21T15:32:17Z",
        "origin_pickedup_at": "2019-02-21T15:32:17Z",
        "origin_out_at": "2019-02-21T15:32:17Z",
        "destination_arrived_at": "2019-02-21T15:32:17Z",
        "destination_in_at": "2019-02-21T15:32:17Z",
        "destination_delivered_at": "2019-02-21T15:32:17Z",
        "destination_out_at": "2019-02-21T15:32:17Z"
      }
    }
  ]
}
```

<h3 id="bulkaddlegsbymanifestid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="bulkaddlegsbymanifestid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» legs|[[Leg](#schemaleg)]|false|none|[Leg]|
|»» id|string(uuid)|false|read-only|Auto generated system ID|
|»» sequence_id|integer|false|read-only|Auto generated sequence ID per customer|
|»» version|integer|false|read-only|Auto generated version number (incremental)|
|»» external_id|string|false|none|External ID for mapping the leg to an external system. This field value can be _null_|
|»» public_id|string|false|read-only|Auto generated human readable ID|
|»» order_id|string|false|read-only|Related order ID|
|»» manifest_id|string|false|none|Related manifest ID (assigned). This field value can be _null_|
|»» origin_stop_id|string|false|read-only|Stop ID of the origin (only if this leg has been assigned to a manifest). This field value can be _null_|
|»» destination_stop_id|string|false|read-only|Stop ID of the destination (only if this leg has been assigned to a manifest). This field value can be _null_|
|»» origin|[LegAddress](#schemalegaddress)|false|none|Leg address|
|»»» terminal_id|string(uuid)|false|none|Related terminal ID. This field value can be _null_|
|»»» org_name|string|false|none|Organization name|
|»»» contact_name|string|false|none|Contact name|
|»»» address_1|string|false|none|Address line 1|
|»»» address_2|string|false|none|Address line 2|
|»»» suite|string|false|none|Suite number|
|»»» city|string|false|none|City|
|»»» state|string|false|none|State / Province|
|»»» country|string|false|none|Country (2 letter ISO)|
|»»» postal|string|false|none|Postal / Zip code|
|»»» phone|string|false|none|Phone number|
|»»» phone_ext|string|false|none|Phone extension|
|»»» email|string|false|none|Email|
|»»» fax|string|false|none|Fax|
|»»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|»» destination|[LegAddress](#schemalegaddress)|false|none|Leg address|
|»» status|string|false|read-only|Leg Status|
|»» origin_start_at|string(date-time)|false|none|Origin ready time range (start)|
|»» origin_end_at|string(date-time)|false|none|Origin ready time range (end)|
|»» origin_appt_start_at|string(date-time)|false|none|Origin appointment time range (start). This field value can be _null_|
|»» origin_appt_end_at|string(date-time)|false|none|Origin appointment time range (end). This field value can be _null_|
|»» destination_start_at|string(date-time)|false|none|Destination expected time range (start). This field value can be _null_|
|»» destination_end_at|string(date-time)|false|none|Destination expected time range (end). This field value can be _null_|
|»» destination_appt_start_at|string(date-time)|false|none|Destination appointment time range (start). This field value can be _null_|
|»» destination_appt_end_at|string(date-time)|false|none|Destination appointment time range (end). This field value can be _null_|
|»» commodities|[[Commodity](#schemacommodity)]|false|none|Commodities items|
|»»» id|string(uuid)|false|read-only|Auto generated commodity id|
|»»» measurement_unit|string|false|none|Measurement unit|
|»»» weight_unit|string|false|none|Weight unit|
|»»» freight_class|string|false|none|Freight class|
|»»» commodity_type|string|false|none|Commodity type|
|»»» commodity_type_other|string|false|none|If commodity type is set to _other_, then this field must have value|
|»»» description|string|false|none|Description of the commodity|
|»»» feet|number(float)|false|none|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_|
|»»» volume|number(float)|false|none|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_|
|»»» length|number(float)|false|none|Length of the commodity|
|»»» width|number(float)|false|none|Width of the commodity|
|»»» height|number(float)|false|none|Height of the commodity|
|»»» weight|number(float)|false|none|Weight of the commodity|
|»»» nmfc|string|false|none|NMFC number|
|»»» is_stackable|boolean|false|none|Is this commodity can be stacked?|
|»»» quantity|integer|false|none|Quantity of the commodity|
|»»» pieces|integer|false|none|Total number of pieces. This field value can be _null_|
|»»» sku|string|false|none|SKU number|
|»» accessorials|[string]|false|none|none|
|»» history|[LegHistory](#schemaleghistory)|false|read-only|Historical timestamps of a leg|
|»»» origin_arrived_at|string(date-time)|false|none|The timestamp of when the driver/partner arrived at origin|
|»»» origin_in_at|string(date-time)|false|none|The timestamp of when the driver/partner in at origin|
|»»» origin_pickedup_at|string(date-time)|false|none|The timestamp of when the driver/partner picked up at origin|
|»»» origin_out_at|string(date-time)|false|none|The timestamp of when the driver/partner out at origin|
|»»» destination_arrived_at|string(date-time)|false|none|The timestamp of when the driver/partner arrived at destination|
|»»» destination_in_at|string(date-time)|false|none|The timestamp of when the driver/partner in at destination|
|»»» destination_delivered_at|string(date-time)|false|none|The timestamp of when the driver/partner delievered up at destination|
|»»» destination_out_at|string(date-time)|false|none|The timestamp of when the driver/partner out at destination|

#### Enumerated Values

|Property|Value|
|---|---|
|status|available|
|status|pending|
|status|dispatched|
|status|arrived_origin|
|status|in_origin|
|status|loaded|
|status|departed_origin|
|status|arrived_destination|
|status|in_destination|
|status|unloaded|
|status|departed_destination|
|status|cancelled|
|status|problem|
|measurement_unit|inch|
|measurement_unit|cm|
|weight_unit|lb|
|weight_unit|kg|
|commodity_type|skid|
|commodity_type|other|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: manifests )
</aside>

## getManifestPaymentByManifestID

<a id="opIdgetManifestPaymentByManifestID"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/manifests/{manifestID}/payment \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://platform.roserocket.com/v1/manifests/{manifestID}/payment HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/manifests/{manifestID}/payment',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://platform.roserocket.com/v1/manifests/{manifestID}/payment',
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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://platform.roserocket.com/v1/manifests/{manifestID}/payment',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://platform.roserocket.com/v1/manifests/{manifestID}/payment', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://platform.roserocket.com/v1/manifests/{manifestID}/payment");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://platform.roserocket.com/v1/manifests/{manifestID}/payment", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /manifests/{manifestID}/payment`

*Get manifest payment by manifest ID*

<h3 id="getmanifestpaymentbymanifestid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|manifestID|path|string|true|ID of the manifest for which to get a payment. It could also be the external ID of the manifest, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the manifest's external ID is __test123__ then the value of manifestID should be __ext:test1234__ or __external_id:test1234__.|

> Example responses

> 200 Response

```json
{
  "manifest_payment": {
    "id": "string",
    "created_at": "2019-02-21T15:32:17Z",
    "updated_at": "2019-02-21T15:32:17Z",
    "created_by": "2019-02-21T15:32:17Z",
    "manifest_id": "string",
    "currency_id": "cad",
    "full_id": "string",
    "revision": 0,
    "send_to_email": "string",
    "cc_to_email": "string",
    "pay_to_company_name": "string",
    "pay_to_contact_name": "string",
    "pay_to_address_1": "string",
    "pay_to_address_2": "string",
    "pay_to_city": "string",
    "pay_to_state": "string",
    "pay_to_country": "string",
    "pay_to_timezone": "string",
    "notes": "string",
    "sub_total_amount": 0,
    "tax_amount": 0,
    "total_amount": 0
  },
  "payment_items": [
    {
      "id": "string",
      "created_at": "2019-02-21T15:32:17Z",
      "updated_at": "2019-02-21T15:32:17Z",
      "manifest_payment_id": "string",
      "bill_class": "misc",
      "unit_price": 0,
      "quantity": 0,
      "total_amount": 0,
      "description": "string"
    }
  ]
}
```

<h3 id="getmanifestpaymentbymanifestid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="getmanifestpaymentbymanifestid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» manifest_payment|[ManifestPayment](#schemamanifestpayment)|false|none|none|
|»» id|string(uuid)|false|none|The id of the manifest payment|
|»» created_at|string(date-time)|false|none|The time of the payment's creation|
|»» updated_at|string(date-time)|false|none|The time the payment was last updated|
|»» created_by|string(date-time)|false|none|The id of the user who created the payment|
|»» manifest_id|string(uuid)|false|none|The id of the manifest for which the payment belongs|
|»» currency_id|string|false|none|The currency of the payment|
|»» full_id|string|false|none|The full id of the payment. This includes the full_id of the payment's manifest|
|»» revision|integer|false|none|The revision number of the payment|
|»» send_to_email|string|false|none|The email of the recipient of the payment|
|»» cc_to_email|string|false|none|The email of the cc recipient of the payment|
|»» pay_to_company_name|string|false|none|The company name of the recipient of the payment|
|»» pay_to_contact_name|string|false|none|The contact name of the recipient of the payment|
|»» pay_to_address_1|string|false|none|Line 1 of the address of the recipient of payment|
|»» pay_to_address_2|string|false|none|Line 2 of the address of the recipient of payment|
|»» pay_to_city|string|false|none|The city of recipient of the payment|
|»» pay_to_state|string|false|none|The state/province of the recipient of the payment|
|»» pay_to_country|string|false|none|The country of the recipient of the payment|
|»» pay_to_timezone|string|false|none|The timezone of the recipient of the payment|
|»» notes|string|false|none|Notes on the payment|
|»» sub_total_amount|number|false|none|The subtotal of the payment|
|»» tax_amount|number|false|none|The total tax amount of the payment|
|»» total_amount|number|false|none|The total amount of the payment|
|» payment_items|[[ManifestPaymentItem](#schemamanifestpaymentitem)]|false|none|none|
|»» id|string(uuid)|false|none|The id of the manifest payment item|
|»» created_at|string(date-time)|false|none|The time of the payment item's creation|
|»» updated_at|string(date-time)|false|none|The time the payment item was last updated|
|»» manifest_payment_id|string(uuid)|false|none|The id of the manifest payment to which the payment belongs|
|»» bill_class|string|false|none|The bill class of payment item|
|»» unit_price|number|false|none|The per-unit price of the payment item|
|»» quantity|number|false|none|The quantity of the payment item|
|»» total_amount|number|false|none|The total amount of the payment item|
|»» description|string|false|none|A description of the payment item|

#### Enumerated Values

|Property|Value|
|---|---|
|currency_id|cad|
|currency_id|usd|
|bill_class|misc|
|bill_class|misc-deduction|
|bill_class|partner-freight|
|bill_class|partner-accessorial|
|bill_class|partner-fuel|
|bill_class|partner-misc|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: manifests )
</aside>

## updateManifestPaymentByManifestID

<a id="opIdupdateManifestPaymentByManifestID"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/manifests/{manifestID}/payment \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT https://platform.roserocket.com/v1/manifests/{manifestID}/payment HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/manifests/{manifestID}/payment',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "manifest_payment": {
    "id": "string",
    "created_at": "2019-02-21T15:32:17Z",
    "updated_at": "2019-02-21T15:32:17Z",
    "created_by": "2019-02-21T15:32:17Z",
    "manifest_id": "string",
    "currency_id": "cad",
    "full_id": "string",
    "revision": 0,
    "send_to_email": "string",
    "cc_to_email": "string",
    "pay_to_company_name": "string",
    "pay_to_contact_name": "string",
    "pay_to_address_1": "string",
    "pay_to_address_2": "string",
    "pay_to_city": "string",
    "pay_to_state": "string",
    "pay_to_country": "string",
    "pay_to_timezone": "string",
    "notes": "string",
    "sub_total_amount": 0,
    "tax_amount": 0,
    "total_amount": 0
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://platform.roserocket.com/v1/manifests/{manifestID}/payment',
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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put 'https://platform.roserocket.com/v1/manifests/{manifestID}/payment',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('https://platform.roserocket.com/v1/manifests/{manifestID}/payment', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://platform.roserocket.com/v1/manifests/{manifestID}/payment");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://platform.roserocket.com/v1/manifests/{manifestID}/payment", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /manifests/{manifestID}/payment`

*Update a manifest payment by manifest ID. Note - this endpoint does not affect manifest payment items*

> Body parameter

```json
{
  "manifest_payment": {
    "id": "string",
    "created_at": "2019-02-21T15:32:17Z",
    "updated_at": "2019-02-21T15:32:17Z",
    "created_by": "2019-02-21T15:32:17Z",
    "manifest_id": "string",
    "currency_id": "cad",
    "full_id": "string",
    "revision": 0,
    "send_to_email": "string",
    "cc_to_email": "string",
    "pay_to_company_name": "string",
    "pay_to_contact_name": "string",
    "pay_to_address_1": "string",
    "pay_to_address_2": "string",
    "pay_to_city": "string",
    "pay_to_state": "string",
    "pay_to_country": "string",
    "pay_to_timezone": "string",
    "notes": "string",
    "sub_total_amount": 0,
    "tax_amount": 0,
    "total_amount": 0
  }
}
```

<h3 id="updatemanifestpaymentbymanifestid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|manifestID|path|string|true|ID of the manifest for which to update a payment. It could also be the external ID of the manifest, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the manifest's external ID is __test123__ then the value of manifestID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|object|false|Request to update manifest payment|
|» manifest_payment|body|[ManifestPayment](#schemamanifestpayment)|false|none|
|»» id|body|string(uuid)|false|The id of the manifest payment|
|»» created_at|body|string(date-time)|false|The time of the payment's creation|
|»» updated_at|body|string(date-time)|false|The time the payment was last updated|
|»» created_by|body|string(date-time)|false|The id of the user who created the payment|
|»» manifest_id|body|string(uuid)|false|The id of the manifest for which the payment belongs|
|»» currency_id|body|string|false|The currency of the payment|
|»» full_id|body|string|false|The full id of the payment. This includes the full_id of the payment's manifest|
|»» revision|body|integer|false|The revision number of the payment|
|»» send_to_email|body|string|false|The email of the recipient of the payment|
|»» cc_to_email|body|string|false|The email of the cc recipient of the payment|
|»» pay_to_company_name|body|string|false|The company name of the recipient of the payment|
|»» pay_to_contact_name|body|string|false|The contact name of the recipient of the payment|
|»» pay_to_address_1|body|string|false|Line 1 of the address of the recipient of payment|
|»» pay_to_address_2|body|string|false|Line 2 of the address of the recipient of payment|
|»» pay_to_city|body|string|false|The city of recipient of the payment|
|»» pay_to_state|body|string|false|The state/province of the recipient of the payment|
|»» pay_to_country|body|string|false|The country of the recipient of the payment|
|»» pay_to_timezone|body|string|false|The timezone of the recipient of the payment|
|»» notes|body|string|false|Notes on the payment|
|»» sub_total_amount|body|number|false|The subtotal of the payment|
|»» tax_amount|body|number|false|The total tax amount of the payment|
|»» total_amount|body|number|false|The total amount of the payment|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»» currency_id|cad|
|»» currency_id|usd|

> Example responses

> 200 Response

```json
{
  "manifest_payment": {
    "id": "string",
    "created_at": "2019-02-21T15:32:17Z",
    "updated_at": "2019-02-21T15:32:17Z",
    "created_by": "2019-02-21T15:32:17Z",
    "manifest_id": "string",
    "currency_id": "cad",
    "full_id": "string",
    "revision": 0,
    "send_to_email": "string",
    "cc_to_email": "string",
    "pay_to_company_name": "string",
    "pay_to_contact_name": "string",
    "pay_to_address_1": "string",
    "pay_to_address_2": "string",
    "pay_to_city": "string",
    "pay_to_state": "string",
    "pay_to_country": "string",
    "pay_to_timezone": "string",
    "notes": "string",
    "sub_total_amount": 0,
    "tax_amount": 0,
    "total_amount": 0
  },
  "payment_items": [
    {
      "id": "string",
      "created_at": "2019-02-21T15:32:17Z",
      "updated_at": "2019-02-21T15:32:17Z",
      "manifest_payment_id": "string",
      "bill_class": "misc",
      "unit_price": 0,
      "quantity": 0,
      "total_amount": 0,
      "description": "string"
    }
  ],
  "created_by": "string"
}
```

<h3 id="updatemanifestpaymentbymanifestid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="updatemanifestpaymentbymanifestid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» manifest_payment|[ManifestPayment](#schemamanifestpayment)|false|none|none|
|»» id|string(uuid)|false|none|The id of the manifest payment|
|»» created_at|string(date-time)|false|none|The time of the payment's creation|
|»» updated_at|string(date-time)|false|none|The time the payment was last updated|
|»» created_by|string(date-time)|false|none|The id of the user who created the payment|
|»» manifest_id|string(uuid)|false|none|The id of the manifest for which the payment belongs|
|»» currency_id|string|false|none|The currency of the payment|
|»» full_id|string|false|none|The full id of the payment. This includes the full_id of the payment's manifest|
|»» revision|integer|false|none|The revision number of the payment|
|»» send_to_email|string|false|none|The email of the recipient of the payment|
|»» cc_to_email|string|false|none|The email of the cc recipient of the payment|
|»» pay_to_company_name|string|false|none|The company name of the recipient of the payment|
|»» pay_to_contact_name|string|false|none|The contact name of the recipient of the payment|
|»» pay_to_address_1|string|false|none|Line 1 of the address of the recipient of payment|
|»» pay_to_address_2|string|false|none|Line 2 of the address of the recipient of payment|
|»» pay_to_city|string|false|none|The city of recipient of the payment|
|»» pay_to_state|string|false|none|The state/province of the recipient of the payment|
|»» pay_to_country|string|false|none|The country of the recipient of the payment|
|»» pay_to_timezone|string|false|none|The timezone of the recipient of the payment|
|»» notes|string|false|none|Notes on the payment|
|»» sub_total_amount|number|false|none|The subtotal of the payment|
|»» tax_amount|number|false|none|The total tax amount of the payment|
|»» total_amount|number|false|none|The total amount of the payment|
|» payment_items|[[ManifestPaymentItem](#schemamanifestpaymentitem)]|false|none|none|
|»» id|string(uuid)|false|none|The id of the manifest payment item|
|»» created_at|string(date-time)|false|none|The time of the payment item's creation|
|»» updated_at|string(date-time)|false|none|The time the payment item was last updated|
|»» manifest_payment_id|string(uuid)|false|none|The id of the manifest payment to which the payment belongs|
|»» bill_class|string|false|none|The bill class of payment item|
|»» unit_price|number|false|none|The per-unit price of the payment item|
|»» quantity|number|false|none|The quantity of the payment item|
|»» total_amount|number|false|none|The total amount of the payment item|
|»» description|string|false|none|A description of the payment item|
|» created_by|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|currency_id|cad|
|currency_id|usd|
|bill_class|misc|
|bill_class|misc-deduction|
|bill_class|partner-freight|
|bill_class|partner-accessorial|
|bill_class|partner-fuel|
|bill_class|partner-misc|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: manifests )
</aside>

## upsertManifestPaymentItemsByManifestID

<a id="opIdupsertManifestPaymentItemsByManifestID"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/manifests/{manifestID}/payment/items/upsert \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT https://platform.roserocket.com/v1/manifests/{manifestID}/payment/items/upsert HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/manifests/{manifestID}/payment/items/upsert',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "payment_items": [
    {
      "id": "string",
      "created_at": "2019-02-21T15:32:17Z",
      "updated_at": "2019-02-21T15:32:17Z",
      "manifest_payment_id": "string",
      "bill_class": "misc",
      "unit_price": 0,
      "quantity": 0,
      "total_amount": 0,
      "description": "string"
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://platform.roserocket.com/v1/manifests/{manifestID}/payment/items/upsert',
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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put 'https://platform.roserocket.com/v1/manifests/{manifestID}/payment/items/upsert',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('https://platform.roserocket.com/v1/manifests/{manifestID}/payment/items/upsert', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://platform.roserocket.com/v1/manifests/{manifestID}/payment/items/upsert");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://platform.roserocket.com/v1/manifests/{manifestID}/payment/items/upsert", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /manifests/{manifestID}/payment/items/upsert`

*Upsert payment items to a manifest payment. To update a payment, specify a valid id for the payment. Payments without ids will be created.*

> Body parameter

```json
{
  "payment_items": [
    {
      "id": "string",
      "created_at": "2019-02-21T15:32:17Z",
      "updated_at": "2019-02-21T15:32:17Z",
      "manifest_payment_id": "string",
      "bill_class": "misc",
      "unit_price": 0,
      "quantity": 0,
      "total_amount": 0,
      "description": "string"
    }
  ]
}
```

<h3 id="upsertmanifestpaymentitemsbymanifestid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|manifestID|path|string|true|ID of the manifest for which to upsert a set of payments. It could also be the external ID of the manifest, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the manifest's external ID is __test123__ then the value of manifestID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|object|false|Request to update manifest payment|
|» payment_items|body|[[ManifestPaymentItem](#schemamanifestpaymentitem)]|false|none|
|»» id|body|string(uuid)|false|The id of the manifest payment item|
|»» created_at|body|string(date-time)|false|The time of the payment item's creation|
|»» updated_at|body|string(date-time)|false|The time the payment item was last updated|
|»» manifest_payment_id|body|string(uuid)|false|The id of the manifest payment to which the payment belongs|
|»» bill_class|body|string|false|The bill class of payment item|
|»» unit_price|body|number|false|The per-unit price of the payment item|
|»» quantity|body|number|false|The quantity of the payment item|
|»» total_amount|body|number|false|The total amount of the payment item|
|»» description|body|string|false|A description of the payment item|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»» bill_class|misc|
|»» bill_class|misc-deduction|
|»» bill_class|partner-freight|
|»» bill_class|partner-accessorial|
|»» bill_class|partner-fuel|
|»» bill_class|partner-misc|

> Example responses

> 200 Response

```json
{
  "manifest_payment": {
    "id": "string",
    "created_at": "2019-02-21T15:32:17Z",
    "updated_at": "2019-02-21T15:32:17Z",
    "created_by": "2019-02-21T15:32:17Z",
    "manifest_id": "string",
    "currency_id": "cad",
    "full_id": "string",
    "revision": 0,
    "send_to_email": "string",
    "cc_to_email": "string",
    "pay_to_company_name": "string",
    "pay_to_contact_name": "string",
    "pay_to_address_1": "string",
    "pay_to_address_2": "string",
    "pay_to_city": "string",
    "pay_to_state": "string",
    "pay_to_country": "string",
    "pay_to_timezone": "string",
    "notes": "string",
    "sub_total_amount": 0,
    "tax_amount": 0,
    "total_amount": 0
  },
  "payment_items": [
    {
      "id": "string",
      "created_at": "2019-02-21T15:32:17Z",
      "updated_at": "2019-02-21T15:32:17Z",
      "manifest_payment_id": "string",
      "bill_class": "misc",
      "unit_price": 0,
      "quantity": 0,
      "total_amount": 0,
      "description": "string"
    }
  ],
  "created_by": "string"
}
```

<h3 id="upsertmanifestpaymentitemsbymanifestid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="upsertmanifestpaymentitemsbymanifestid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» manifest_payment|[ManifestPayment](#schemamanifestpayment)|false|none|none|
|»» id|string(uuid)|false|none|The id of the manifest payment|
|»» created_at|string(date-time)|false|none|The time of the payment's creation|
|»» updated_at|string(date-time)|false|none|The time the payment was last updated|
|»» created_by|string(date-time)|false|none|The id of the user who created the payment|
|»» manifest_id|string(uuid)|false|none|The id of the manifest for which the payment belongs|
|»» currency_id|string|false|none|The currency of the payment|
|»» full_id|string|false|none|The full id of the payment. This includes the full_id of the payment's manifest|
|»» revision|integer|false|none|The revision number of the payment|
|»» send_to_email|string|false|none|The email of the recipient of the payment|
|»» cc_to_email|string|false|none|The email of the cc recipient of the payment|
|»» pay_to_company_name|string|false|none|The company name of the recipient of the payment|
|»» pay_to_contact_name|string|false|none|The contact name of the recipient of the payment|
|»» pay_to_address_1|string|false|none|Line 1 of the address of the recipient of payment|
|»» pay_to_address_2|string|false|none|Line 2 of the address of the recipient of payment|
|»» pay_to_city|string|false|none|The city of recipient of the payment|
|»» pay_to_state|string|false|none|The state/province of the recipient of the payment|
|»» pay_to_country|string|false|none|The country of the recipient of the payment|
|»» pay_to_timezone|string|false|none|The timezone of the recipient of the payment|
|»» notes|string|false|none|Notes on the payment|
|»» sub_total_amount|number|false|none|The subtotal of the payment|
|»» tax_amount|number|false|none|The total tax amount of the payment|
|»» total_amount|number|false|none|The total amount of the payment|
|» payment_items|[[ManifestPaymentItem](#schemamanifestpaymentitem)]|false|none|none|
|»» id|string(uuid)|false|none|The id of the manifest payment item|
|»» created_at|string(date-time)|false|none|The time of the payment item's creation|
|»» updated_at|string(date-time)|false|none|The time the payment item was last updated|
|»» manifest_payment_id|string(uuid)|false|none|The id of the manifest payment to which the payment belongs|
|»» bill_class|string|false|none|The bill class of payment item|
|»» unit_price|number|false|none|The per-unit price of the payment item|
|»» quantity|number|false|none|The quantity of the payment item|
|»» total_amount|number|false|none|The total amount of the payment item|
|»» description|string|false|none|A description of the payment item|
|» created_by|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|currency_id|cad|
|currency_id|usd|
|bill_class|misc|
|bill_class|misc-deduction|
|bill_class|partner-freight|
|bill_class|partner-accessorial|
|bill_class|partner-fuel|
|bill_class|partner-misc|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: manifests )
</aside>

## deleteManifestPaymentItemsByManifestID

<a id="opIddeleteManifestPaymentItemsByManifestID"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE https://platform.roserocket.com/v1/manifests/{manifestID}/payment/items \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE https://platform.roserocket.com/v1/manifests/{manifestID}/payment/items HTTP/1.1
Host: platform.roserocket.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/manifests/{manifestID}/payment/items',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "payment_items": [
    "string"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://platform.roserocket.com/v1/manifests/{manifestID}/payment/items',
{
  method: 'DELETE',
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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete 'https://platform.roserocket.com/v1/manifests/{manifestID}/payment/items',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('https://platform.roserocket.com/v1/manifests/{manifestID}/payment/items', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://platform.roserocket.com/v1/manifests/{manifestID}/payment/items");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://platform.roserocket.com/v1/manifests/{manifestID}/payment/items", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /manifests/{manifestID}/payment/items`

*Delete manifest payment items by supplying an array of manifest payment item ids.*

> Body parameter

```json
{
  "payment_items": [
    "string"
  ]
}
```

<h3 id="deletemanifestpaymentitemsbymanifestid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|manifestID|path|string|true|ID of the manifest for which to delete a set of payments. It could also be the external ID of the manifest, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the manifest's external ID is __test123__ then the value of manifestID should be __ext:test1234__ or __external_id:test1234__.|
|body|body|object|false|Request to delete manifest payment items|
|» payment_items|body|[string]|false|none|

> Example responses

> 200 Response

```json
{
  "manifest_payment": {
    "id": "string",
    "created_at": "2019-02-21T15:32:17Z",
    "updated_at": "2019-02-21T15:32:17Z",
    "created_by": "2019-02-21T15:32:17Z",
    "manifest_id": "string",
    "currency_id": "cad",
    "full_id": "string",
    "revision": 0,
    "send_to_email": "string",
    "cc_to_email": "string",
    "pay_to_company_name": "string",
    "pay_to_contact_name": "string",
    "pay_to_address_1": "string",
    "pay_to_address_2": "string",
    "pay_to_city": "string",
    "pay_to_state": "string",
    "pay_to_country": "string",
    "pay_to_timezone": "string",
    "notes": "string",
    "sub_total_amount": 0,
    "tax_amount": 0,
    "total_amount": 0
  },
  "payment_items": [
    {
      "id": "string",
      "created_at": "2019-02-21T15:32:17Z",
      "updated_at": "2019-02-21T15:32:17Z",
      "manifest_payment_id": "string",
      "bill_class": "misc",
      "unit_price": 0,
      "quantity": 0,
      "total_amount": 0,
      "description": "string"
    }
  ],
  "created_by": "string"
}
```

<h3 id="deletemanifestpaymentitemsbymanifestid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="deletemanifestpaymentitemsbymanifestid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» manifest_payment|[ManifestPayment](#schemamanifestpayment)|false|none|none|
|»» id|string(uuid)|false|none|The id of the manifest payment|
|»» created_at|string(date-time)|false|none|The time of the payment's creation|
|»» updated_at|string(date-time)|false|none|The time the payment was last updated|
|»» created_by|string(date-time)|false|none|The id of the user who created the payment|
|»» manifest_id|string(uuid)|false|none|The id of the manifest for which the payment belongs|
|»» currency_id|string|false|none|The currency of the payment|
|»» full_id|string|false|none|The full id of the payment. This includes the full_id of the payment's manifest|
|»» revision|integer|false|none|The revision number of the payment|
|»» send_to_email|string|false|none|The email of the recipient of the payment|
|»» cc_to_email|string|false|none|The email of the cc recipient of the payment|
|»» pay_to_company_name|string|false|none|The company name of the recipient of the payment|
|»» pay_to_contact_name|string|false|none|The contact name of the recipient of the payment|
|»» pay_to_address_1|string|false|none|Line 1 of the address of the recipient of payment|
|»» pay_to_address_2|string|false|none|Line 2 of the address of the recipient of payment|
|»» pay_to_city|string|false|none|The city of recipient of the payment|
|»» pay_to_state|string|false|none|The state/province of the recipient of the payment|
|»» pay_to_country|string|false|none|The country of the recipient of the payment|
|»» pay_to_timezone|string|false|none|The timezone of the recipient of the payment|
|»» notes|string|false|none|Notes on the payment|
|»» sub_total_amount|number|false|none|The subtotal of the payment|
|»» tax_amount|number|false|none|The total tax amount of the payment|
|»» total_amount|number|false|none|The total amount of the payment|
|» payment_items|[[ManifestPaymentItem](#schemamanifestpaymentitem)]|false|none|none|
|»» id|string(uuid)|false|none|The id of the manifest payment item|
|»» created_at|string(date-time)|false|none|The time of the payment item's creation|
|»» updated_at|string(date-time)|false|none|The time the payment item was last updated|
|»» manifest_payment_id|string(uuid)|false|none|The id of the manifest payment to which the payment belongs|
|»» bill_class|string|false|none|The bill class of payment item|
|»» unit_price|number|false|none|The per-unit price of the payment item|
|»» quantity|number|false|none|The quantity of the payment item|
|»» total_amount|number|false|none|The total amount of the payment item|
|»» description|string|false|none|A description of the payment item|
|» created_by|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|currency_id|cad|
|currency_id|usd|
|bill_class|misc|
|bill_class|misc-deduction|
|bill_class|partner-freight|
|bill_class|partner-accessorial|
|bill_class|partner-fuel|
|bill_class|partner-misc|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: manifests )
</aside>

## createNotesByManifestID

<a id="opIdcreateNotesByManifestID"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/manifests/{manifestID}/notes \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://platform.roserocket.com/v1/manifests/{manifestID}/notes HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://platform.roserocket.com/v1/manifests/{manifestID}/notes',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/manifests/{manifestID}/notes", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /manifests/{manifestID}/notes`

*Create notes event for a manifest by manifest ID*

<h3 id="createnotesbymanifestid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|manifestID|path|string|true|ID of the manifest for which to create a notes event. It could also be the external ID of the manifest, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the manifest's external ID is __test123__ then the value of manifestID should be __ext:test1234__ or __external_id:test1234__.|

> Example responses

> 200 Response

```json
{
  "event": {
    "id": "string",
    "created_at": "2019-02-21T15:32:17Z",
    "updated_at": "2019-02-21T15:32:17Z",
    "user_id": "2019-02-21T15:32:17Z",
    "manifest_id": "string",
    "data": {
      "author": "string",
      "text": "string",
      "type": "notes"
    }
  }
}
```

<h3 id="createnotesbymanifestid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="createnotesbymanifestid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» event|[ManifestEvent](#schemamanifestevent)|false|none|none|
|»» id|string(uuid)|false|none|The id of the manifest event|
|»» created_at|string(date-time)|false|none|The time of the event's creation|
|»» updated_at|string(date-time)|false|none|The time the event was last updated|
|»» user_id|string(date-time)|false|none|The id of the user who created the event|
|»» manifest_id|string(uuid)|false|none|The id of the manifest for which the event belongs|
|»» data|object|false|none|none|
|»»» author|string|false|none|The name of the user who authored the event|
|»»» text|string|false|none|The contents of the message|
|»»» type|string|false|none|The type of manifest message|

#### Enumerated Values

|Property|Value|
|---|---|
|type|notes|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: manifests )
</aside>

## getStopsByManifestID

<a id="opIdgetStopsByManifestID"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/manifests/{manifestID}/stops \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://platform.roserocket.com/v1/manifests/{manifestID}/stops HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://platform.roserocket.com/v1/manifests/{manifestID}/stops',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://platform.roserocket.com/v1/manifests/{manifestID}/stops", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /manifests/{manifestID}/stops`

*Get stops by manifest ID*

<h3 id="getstopsbymanifestid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|manifestID|path|string|true|ID of the manifest for which to get stops. It could also be the external ID of the manifest, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the manifest's external ID is __test123__ then the value of manifestID should be __ext:test1234__ or __external_id:test1234__.|

> Example responses

> 200 Response

```json
{
  "stops": [
    {
      "id": "string",
      "manifest_id": "string",
      "ordinal": 0,
      "type": "stop",
      "schedule_start_at": "2019-02-21T15:32:17Z",
      "schedule_end_at": "2019-02-21T15:32:17Z",
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

<h3 id="getstopsbymanifestid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="getstopsbymanifestid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» stops|[[Stop](#schemastop)]|false|none|[Stop]|
|»» id|string(uuid)|false|read-only|Auto generated system ID|
|»» manifest_id|string|false|read-only|Related Manifest ID|
|»» ordinal|integer|false|read-only|Ordinal of the stop in the manifest|
|»» type|string|false|read-only|Stop Type|
|»» schedule_start_at|string(date-time)|false|none|Scheduled time range (start)|
|»» schedule_end_at|string(date-time)|false|none|Scheduled time range (end)|
|»» org_name|string|false|none|Organization name|
|»» contact_name|string|false|none|Contact name|
|»» address_1|string|false|none|Address line 1|
|»» address_2|string|false|none|Address line 2|
|»» suite|string|false|none|Suite number|
|»» city|string|false|none|City|
|»» state|string|false|none|State / Province|
|»» country|string|false|none|Country (2 letter ISO)|
|»» postal|string|false|none|Postal / Zip code|
|»» phone|string|false|none|Phone number|
|»» phone_ext|string|false|none|Phone extension|
|»» email|string|false|none|Email|
|»» fax|string|false|none|Fax|
|»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|

#### Enumerated Values

|Property|Value|
|---|---|
|type|stop|
|type|start|
|type|end|
|type|terminal|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: manifests )
</aside>

## getManifestStopByID

<a id="opIdgetManifestStopByID"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/manifests/{manifestID}/stops/{stopID} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://platform.roserocket.com/v1/manifests/{manifestID}/stops/{stopID} HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://platform.roserocket.com/v1/manifests/{manifestID}/stops/{stopID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://platform.roserocket.com/v1/manifests/{manifestID}/stops/{stopID}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /manifests/{manifestID}/stops/{stopID}`

*Get manifest's stop by ID*

<h3 id="getmanifeststopbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|manifestID|path|string|true|ID of the manifest. It could also be the external ID of the manifest, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the manifest's external ID is __test123__ then the value of manifestID should be __ext:test1234__ or __external_id:test1234__.|
|stopID|path|string(uuid)|true|ID of the stop|

> Example responses

> 200 Response

```json
{
  "stop": {
    "id": "string",
    "manifest_id": "string",
    "ordinal": 0,
    "type": "stop",
    "schedule_start_at": "2019-02-21T15:32:17Z",
    "schedule_end_at": "2019-02-21T15:32:17Z",
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

<h3 id="getmanifeststopbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="getmanifeststopbyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» stop|[Stop](#schemastop)|false|none|Stop|
|»» id|string(uuid)|false|read-only|Auto generated system ID|
|»» manifest_id|string|false|read-only|Related Manifest ID|
|»» ordinal|integer|false|read-only|Ordinal of the stop in the manifest|
|»» type|string|false|read-only|Stop Type|
|»» schedule_start_at|string(date-time)|false|none|Scheduled time range (start)|
|»» schedule_end_at|string(date-time)|false|none|Scheduled time range (end)|
|»» org_name|string|false|none|Organization name|
|»» contact_name|string|false|none|Contact name|
|»» address_1|string|false|none|Address line 1|
|»» address_2|string|false|none|Address line 2|
|»» suite|string|false|none|Suite number|
|»» city|string|false|none|City|
|»» state|string|false|none|State / Province|
|»» country|string|false|none|Country (2 letter ISO)|
|»» postal|string|false|none|Postal / Zip code|
|»» phone|string|false|none|Phone number|
|»» phone_ext|string|false|none|Phone extension|
|»» email|string|false|none|Email|
|»» fax|string|false|none|Fax|
|»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|

#### Enumerated Values

|Property|Value|
|---|---|
|type|stop|
|type|start|
|type|end|
|type|terminal|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: manifests )
</aside>

## updateManifestStopScheduleByID

<a id="opIdupdateManifestStopScheduleByID"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/manifests/{manifestID}/stops/{stopID}/update_schedule \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
const fetch = require('node-fetch');
const inputBody = '{
  "schedule_start_at": "2019-02-21T15:32:17Z",
  "schedule_end_at": "2019-02-21T15:32:17Z"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
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
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://platform.roserocket.com/v1/manifests/{manifestID}/stops/{stopID}/update_schedule", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /manifests/{manifestID}/stops/{stopID}/update_schedule`

*Update manifest's stop schedule by ID*

> Body parameter

```json
{
  "schedule_start_at": "2019-02-21T15:32:17Z",
  "schedule_end_at": "2019-02-21T15:32:17Z"
}
```

<h3 id="updatemanifeststopschedulebyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|manifestID|path|string|true|ID of the manifest. It could also be the external ID of the manifest, but in order to use external ID it has to follow this format: __ext:{externalID}__ or __external_id:{externalID}__. So for example if the manifest's external ID is __test123__ then the value of manifestID should be __ext:test1234__ or __external_id:test1234__.|
|stopID|path|string(uuid)|true|ID of the stop|
|body|body|object|true|Stop object|
|» schedule_start_at|body|string(date-time)|false|Schedule time range (start)|
|» schedule_end_at|body|string(date-time)|false|Schedule time range (start)|

> Example responses

> 200 Response

```json
{
  "stop": {
    "id": "string",
    "manifest_id": "string",
    "ordinal": 0,
    "type": "stop",
    "schedule_start_at": "2019-02-21T15:32:17Z",
    "schedule_end_at": "2019-02-21T15:32:17Z",
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

<h3 id="updatemanifeststopschedulebyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="updatemanifeststopschedulebyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» stop|[Stop](#schemastop)|false|none|Stop|
|»» id|string(uuid)|false|read-only|Auto generated system ID|
|»» manifest_id|string|false|read-only|Related Manifest ID|
|»» ordinal|integer|false|read-only|Ordinal of the stop in the manifest|
|»» type|string|false|read-only|Stop Type|
|»» schedule_start_at|string(date-time)|false|none|Scheduled time range (start)|
|»» schedule_end_at|string(date-time)|false|none|Scheduled time range (end)|
|»» org_name|string|false|none|Organization name|
|»» contact_name|string|false|none|Contact name|
|»» address_1|string|false|none|Address line 1|
|»» address_2|string|false|none|Address line 2|
|»» suite|string|false|none|Suite number|
|»» city|string|false|none|City|
|»» state|string|false|none|State / Province|
|»» country|string|false|none|Country (2 letter ISO)|
|»» postal|string|false|none|Postal / Zip code|
|»» phone|string|false|none|Phone number|
|»» phone_ext|string|false|none|Phone extension|
|»» email|string|false|none|Email|
|»» fax|string|false|none|Fax|
|»» latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|»» longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|

#### Enumerated Values

|Property|Value|
|---|---|
|type|stop|
|type|start|
|type|end|
|type|terminal|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
roserocket_auth ( Scopes: manifests )
</aside>

<h1 id="rose-rocket-platform-rest-api-partner_carrier">partner_carrier</h1>

## searchPartnerCarriers

<a id="opIdsearchPartnerCarriers"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/partner_carriers \
  -H 'Accept: application/json'

```

```http
GET https://platform.roserocket.com/v1/partner_carriers HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/partner_carriers',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/partner_carriers',
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

result = RestClient.get 'https://platform.roserocket.com/v1/partner_carriers',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://platform.roserocket.com/v1/partner_carriers', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://platform.roserocket.com/v1/partner_carriers");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://platform.roserocket.com/v1/partner_carriers", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /partner_carriers`

*Search partner carriers*

<h3 id="searchpartnercarriers-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|search_term|query|string|false|Search term|
|offset|query|integer|false|Pagination offset|
|limit|query|integer|false|Pagination limit|

> Example responses

> 200 Response

```json
{
  "partner_carriers": [
    {
      "created_at": "2019-02-21T15:32:17Z",
      "updated_at": "2019-02-21T15:32:17Z",
      "id": "string",
      "org_id": "string",
      "qb_external_id": "string",
      "external_id": "string",
      "name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "fax": "string",
      "email": "string",
      "country": "string",
      "state": "string",
      "timezone": "string",
      "dispatch_contact_name": "string",
      "dispatch_contact_email": "string",
      "billing_contact_name": "string",
      "billing_contact_email": "string",
      "sales_contact_name": "string",
      "sales_contact_email": "string",
      "motor_carrier_id": "string",
      "dept_of_transportation_id": "string",
      "standard_carrier_alpha_code": "string",
      "provincial_operating_authority_num": "string"
    }
  ],
  "offset": 0,
  "limit": 0,
  "total": 0
}
```

<h3 id="searchpartnercarriers-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="searchpartnercarriers-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» partner_carriers|[[PartnerCarrier](#schemapartnercarrier)]|false|none|[A partner carrier]|
|»» created_at|string(date-time)|false|none|The timestamp for the creation of the partner carrier|
|»» updated_at|string(date-time)|false|none|The timestamp for the last update of the partner carrier|
|»» id|string(uuid)|false|none|none|
|»» org_id|string(uuid)|false|none|The uuid for the organization of the partner carrier|
|»» qb_external_id|string|false|none|The external identifier for the partner carrier in QBO|
|»» external_id|string|false|none|the external identifier for the partner carrier|
|»» name|string|false|none|The name of the partner carrier|
|»» address_1|string|false|none|The first address line of the partner carrier|
|»» address_2|string|false|none|The second address line of the partner carrier|
|»» suite|string|false|none|The suite of the partner carrier's address|
|»» city|string|false|none|The city of the partner carrier's address|
|»» postal|string|false|none|The postal code of the partner carrier's address|
|»» phone|string|false|none|The phone number of the partner carrier|
|»» phone_ext|string|false|none|The phone extension of the partner carrier|
|»» fax|string|false|none|The fax number of the partner carrier|
|»» email|string|false|none|The email address of the partner carrier|
|»» country|string|false|none|The country of the partner carrier|
|»» state|string|false|none|The state of the partner carrier|
|»» timezone|string|false|none|The timezone in which the partner carrier resides|
|»» dispatch_contact_name|string|false|none|The contact name for dispatches to partner carrier|
|»» dispatch_contact_email|string|false|none|The contact email for dispatches to partner carrier|
|»» billing_contact_name|string|false|none|The contact name for billing to partner carrier|
|»» billing_contact_email|string|false|none|The contact email for billing to partner carrier|
|»» sales_contact_name|string|false|none|The contact name for sales to partner carrier|
|»» sales_contact_email|string|false|none|The contact email for sales to partner carrier|
|»» motor_carrier_id|string|false|none|The motor carrier id of the partner carrier|
|»» dept_of_transportation_id|string|false|none|The partner carrier's department of transportation id|
|»» standard_carrier_alpha_code|string|false|none|The SCAC of the partner carrier|
|»» provincial_operating_authority_num|string|false|none|The provincial operating authority number for the partner carrier|
|» offset|integer|false|none|none|
|» limit|integer|false|none|none|
|» total|integer|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## createPartnerCarrier

<a id="opIdcreatePartnerCarrier"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://platform.roserocket.com/v1/partner_carriers \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST https://platform.roserocket.com/v1/partner_carriers HTTP/1.1
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
  url: 'https://platform.roserocket.com/v1/partner_carriers',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "created_at": "2019-02-21T15:32:17Z",
  "updated_at": "2019-02-21T15:32:17Z",
  "id": "string",
  "org_id": "string",
  "qb_external_id": "string",
  "external_id": "string",
  "name": "string",
  "address_1": "string",
  "address_2": "string",
  "suite": "string",
  "city": "string",
  "postal": "string",
  "phone": "string",
  "phone_ext": "string",
  "fax": "string",
  "email": "string",
  "country": "string",
  "state": "string",
  "timezone": "string",
  "dispatch_contact_name": "string",
  "dispatch_contact_email": "string",
  "billing_contact_name": "string",
  "billing_contact_email": "string",
  "sales_contact_name": "string",
  "sales_contact_email": "string",
  "motor_carrier_id": "string",
  "dept_of_transportation_id": "string",
  "standard_carrier_alpha_code": "string",
  "provincial_operating_authority_num": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/partner_carriers',
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

result = RestClient.post 'https://platform.roserocket.com/v1/partner_carriers',
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

r = requests.post('https://platform.roserocket.com/v1/partner_carriers', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://platform.roserocket.com/v1/partner_carriers");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://platform.roserocket.com/v1/partner_carriers", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /partner_carriers`

*Create a partner carrier*

> Body parameter

```json
{
  "created_at": "2019-02-21T15:32:17Z",
  "updated_at": "2019-02-21T15:32:17Z",
  "id": "string",
  "org_id": "string",
  "qb_external_id": "string",
  "external_id": "string",
  "name": "string",
  "address_1": "string",
  "address_2": "string",
  "suite": "string",
  "city": "string",
  "postal": "string",
  "phone": "string",
  "phone_ext": "string",
  "fax": "string",
  "email": "string",
  "country": "string",
  "state": "string",
  "timezone": "string",
  "dispatch_contact_name": "string",
  "dispatch_contact_email": "string",
  "billing_contact_name": "string",
  "billing_contact_email": "string",
  "sales_contact_name": "string",
  "sales_contact_email": "string",
  "motor_carrier_id": "string",
  "dept_of_transportation_id": "string",
  "standard_carrier_alpha_code": "string",
  "provincial_operating_authority_num": "string"
}
```

<h3 id="createpartnercarrier-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PartnerCarrier](#schemapartnercarrier)|true|New Partner Carrier object|

> Example responses

> 200 Response

```json
{
  "partner_carrier": {
    "created_at": "2019-02-21T15:32:17Z",
    "updated_at": "2019-02-21T15:32:17Z",
    "id": "string",
    "org_id": "string",
    "qb_external_id": "string",
    "external_id": "string",
    "name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "fax": "string",
    "email": "string",
    "country": "string",
    "state": "string",
    "timezone": "string",
    "dispatch_contact_name": "string",
    "dispatch_contact_email": "string",
    "billing_contact_name": "string",
    "billing_contact_email": "string",
    "sales_contact_name": "string",
    "sales_contact_email": "string",
    "motor_carrier_id": "string",
    "dept_of_transportation_id": "string",
    "standard_carrier_alpha_code": "string",
    "provincial_operating_authority_num": "string"
  }
}
```

<h3 id="createpartnercarrier-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="createpartnercarrier-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» partner_carrier|[PartnerCarrier](#schemapartnercarrier)|false|none|A partner carrier|
|»» created_at|string(date-time)|false|none|The timestamp for the creation of the partner carrier|
|»» updated_at|string(date-time)|false|none|The timestamp for the last update of the partner carrier|
|»» id|string(uuid)|false|none|none|
|»» org_id|string(uuid)|false|none|The uuid for the organization of the partner carrier|
|»» qb_external_id|string|false|none|The external identifier for the partner carrier in QBO|
|»» external_id|string|false|none|the external identifier for the partner carrier|
|»» name|string|false|none|The name of the partner carrier|
|»» address_1|string|false|none|The first address line of the partner carrier|
|»» address_2|string|false|none|The second address line of the partner carrier|
|»» suite|string|false|none|The suite of the partner carrier's address|
|»» city|string|false|none|The city of the partner carrier's address|
|»» postal|string|false|none|The postal code of the partner carrier's address|
|»» phone|string|false|none|The phone number of the partner carrier|
|»» phone_ext|string|false|none|The phone extension of the partner carrier|
|»» fax|string|false|none|The fax number of the partner carrier|
|»» email|string|false|none|The email address of the partner carrier|
|»» country|string|false|none|The country of the partner carrier|
|»» state|string|false|none|The state of the partner carrier|
|»» timezone|string|false|none|The timezone in which the partner carrier resides|
|»» dispatch_contact_name|string|false|none|The contact name for dispatches to partner carrier|
|»» dispatch_contact_email|string|false|none|The contact email for dispatches to partner carrier|
|»» billing_contact_name|string|false|none|The contact name for billing to partner carrier|
|»» billing_contact_email|string|false|none|The contact email for billing to partner carrier|
|»» sales_contact_name|string|false|none|The contact name for sales to partner carrier|
|»» sales_contact_email|string|false|none|The contact email for sales to partner carrier|
|»» motor_carrier_id|string|false|none|The motor carrier id of the partner carrier|
|»» dept_of_transportation_id|string|false|none|The partner carrier's department of transportation id|
|»» standard_carrier_alpha_code|string|false|none|The SCAC of the partner carrier|
|»» provincial_operating_authority_num|string|false|none|The provincial operating authority number for the partner carrier|

<aside class="success">
This operation does not require authentication
</aside>

## getPartnerCarrierByID

<a id="opIdgetPartnerCarrierByID"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://platform.roserocket.com/v1/partner_carriers/{partnerCarrierID} \
  -H 'Accept: application/json'

```

```http
GET https://platform.roserocket.com/v1/partner_carriers/{partnerCarrierID} HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/partner_carriers/{partnerCarrierID}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/partner_carriers/{partnerCarrierID}',
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

result = RestClient.get 'https://platform.roserocket.com/v1/partner_carriers/{partnerCarrierID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://platform.roserocket.com/v1/partner_carriers/{partnerCarrierID}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://platform.roserocket.com/v1/partner_carriers/{partnerCarrierID}");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://platform.roserocket.com/v1/partner_carriers/{partnerCarrierID}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /partner_carriers/{partnerCarrierID}`

*Get partner carrier by ID*

<h3 id="getpartnercarrierbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|partnerCarrierID|path|string(uuid)|true|ID of the partner carrier|

> Example responses

> 200 Response

```json
{
  "partner_carrier": {
    "created_at": "2019-02-21T15:32:17Z",
    "updated_at": "2019-02-21T15:32:17Z",
    "id": "string",
    "org_id": "string",
    "qb_external_id": "string",
    "external_id": "string",
    "name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "fax": "string",
    "email": "string",
    "country": "string",
    "state": "string",
    "timezone": "string",
    "dispatch_contact_name": "string",
    "dispatch_contact_email": "string",
    "billing_contact_name": "string",
    "billing_contact_email": "string",
    "sales_contact_name": "string",
    "sales_contact_email": "string",
    "motor_carrier_id": "string",
    "dept_of_transportation_id": "string",
    "standard_carrier_alpha_code": "string",
    "provincial_operating_authority_num": "string"
  },
  "services": [
    {
      "created_at": "2019-02-21T15:32:17Z",
      "updated_at": "2019-02-21T15:32:17Z",
      "id": "string",
      "org_id": "string",
      "carrier_app_id": "string",
      "tariff_id": "string",
      "name": "string",
      "is_active": true,
      "carrier_credential_json": "string",
      "min_markup": 0,
      "max_markup": 0,
      "default_markup": 0,
      "default_fuel_surcharge": 0,
      "currency_id": "string",
      "partner_carrier_id": "string",
      "service_type_id": "string",
      "service_type_display_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "fax": "string",
      "email": "string",
      "country": "string",
      "state": "string",
      "timezone": "string",
      "primary_contact_name": "string",
      "primary_contact_email": "string",
      "dispatch_contact_name": "string",
      "dispatch_contact_email": "string",
      "billing_contact_name": "string",
      "billing_contact_email": "string"
    }
  ]
}
```

<h3 id="getpartnercarrierbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="getpartnercarrierbyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» partner_carrier|[PartnerCarrier](#schemapartnercarrier)|false|none|A partner carrier|
|»» created_at|string(date-time)|false|none|The timestamp for the creation of the partner carrier|
|»» updated_at|string(date-time)|false|none|The timestamp for the last update of the partner carrier|
|»» id|string(uuid)|false|none|none|
|»» org_id|string(uuid)|false|none|The uuid for the organization of the partner carrier|
|»» qb_external_id|string|false|none|The external identifier for the partner carrier in QBO|
|»» external_id|string|false|none|the external identifier for the partner carrier|
|»» name|string|false|none|The name of the partner carrier|
|»» address_1|string|false|none|The first address line of the partner carrier|
|»» address_2|string|false|none|The second address line of the partner carrier|
|»» suite|string|false|none|The suite of the partner carrier's address|
|»» city|string|false|none|The city of the partner carrier's address|
|»» postal|string|false|none|The postal code of the partner carrier's address|
|»» phone|string|false|none|The phone number of the partner carrier|
|»» phone_ext|string|false|none|The phone extension of the partner carrier|
|»» fax|string|false|none|The fax number of the partner carrier|
|»» email|string|false|none|The email address of the partner carrier|
|»» country|string|false|none|The country of the partner carrier|
|»» state|string|false|none|The state of the partner carrier|
|»» timezone|string|false|none|The timezone in which the partner carrier resides|
|»» dispatch_contact_name|string|false|none|The contact name for dispatches to partner carrier|
|»» dispatch_contact_email|string|false|none|The contact email for dispatches to partner carrier|
|»» billing_contact_name|string|false|none|The contact name for billing to partner carrier|
|»» billing_contact_email|string|false|none|The contact email for billing to partner carrier|
|»» sales_contact_name|string|false|none|The contact name for sales to partner carrier|
|»» sales_contact_email|string|false|none|The contact email for sales to partner carrier|
|»» motor_carrier_id|string|false|none|The motor carrier id of the partner carrier|
|»» dept_of_transportation_id|string|false|none|The partner carrier's department of transportation id|
|»» standard_carrier_alpha_code|string|false|none|The SCAC of the partner carrier|
|»» provincial_operating_authority_num|string|false|none|The provincial operating authority number for the partner carrier|
|» services|[[Service](#schemaservice)]|false|none|[A service offered by a carrier]|
|»» created_at|string(date-time)|false|none|The timestamp for the creation of the service|
|»» updated_at|string(date-time)|false|none|The timestamp for the last update of the service|
|»» id|string(uuid)|false|none|none|
|»» org_id|string(uuid)|false|none|The uuid for the organization of the service|
|»» carrier_app_id|string|false|none|The id of the carrier app associated with the service|
|»» tariff_id|string|false|none|The id of the tariff associated with the service|
|»» name|string|false|none|The name of the service|
|»» is_active|boolean|false|none|Whether or not the service is active|
|»» carrier_credential_json|string|false|none|The unique json credential for the service|
|»» min_markup|number|false|none|The minimum markup of the service|
|»» max_markup|number|false|none|The maximum markup of the service|
|»» default_markup|number|false|none|The default markup of the service|
|»» default_fuel_surcharge|number|false|none|The default fuel surcharge of the service|
|»» currency_id|string|false|none|The type of currency of the service|
|»» partner_carrier_id|string(uuid,)|false|none|The ID of the partner carrier associated with the service|
|»» service_type_id|string|false|none|The id of the service's type|
|»» service_type_display_name|string|false|none|The display name for the service's type|
|»» address_1|string|false|none|The first address line of the service|
|»» address_2|string|false|none|The second address line of the service|
|»» suite|string|false|none|The suite of the service's address|
|»» city|string|false|none|The city of the service's address|
|»» postal|string|false|none|The postal code of the service's address|
|»» phone|string|false|none|The phone number of the service|
|»» phone_ext|string|false|none|The phone extension of the service|
|»» fax|string|false|none|The fax number of the service|
|»» email|string|false|none|The email address of the service|
|»» country|string|false|none|The country of the service|
|»» state|string|false|none|The state of the service|
|»» timezone|string|false|none|The timezone in which the service resides|
|»» primary_contact_name|string|false|none|The name of the service's primary contact|
|»» primary_contact_email|string|false|none|The email of the service's primary contact|
|»» dispatch_contact_name|string|false|none|The name of the service's dispatch contact|
|»» dispatch_contact_email|string|false|none|The email of the service's dispatch contact|
|»» billing_contact_name|string|false|none|The name of the service's billing contact|
|»» billing_contact_email|string|false|none|The email of the service's billing contact|

<aside class="success">
This operation does not require authentication
</aside>

## updatePartnerCarrierByID

<a id="opIdupdatePartnerCarrierByID"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT https://platform.roserocket.com/v1/partner_carriers/{partnerCarrierID} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT https://platform.roserocket.com/v1/partner_carriers/{partnerCarrierID} HTTP/1.1
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
  url: 'https://platform.roserocket.com/v1/partner_carriers/{partnerCarrierID}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "created_at": "2019-02-21T15:32:17Z",
  "updated_at": "2019-02-21T15:32:17Z",
  "id": "string",
  "org_id": "string",
  "qb_external_id": "string",
  "external_id": "string",
  "name": "string",
  "address_1": "string",
  "address_2": "string",
  "suite": "string",
  "city": "string",
  "postal": "string",
  "phone": "string",
  "phone_ext": "string",
  "fax": "string",
  "email": "string",
  "country": "string",
  "state": "string",
  "timezone": "string",
  "dispatch_contact_name": "string",
  "dispatch_contact_email": "string",
  "billing_contact_name": "string",
  "billing_contact_email": "string",
  "sales_contact_name": "string",
  "sales_contact_email": "string",
  "motor_carrier_id": "string",
  "dept_of_transportation_id": "string",
  "standard_carrier_alpha_code": "string",
  "provincial_operating_authority_num": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/partner_carriers/{partnerCarrierID}',
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

result = RestClient.put 'https://platform.roserocket.com/v1/partner_carriers/{partnerCarrierID}',
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

r = requests.put('https://platform.roserocket.com/v1/partner_carriers/{partnerCarrierID}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://platform.roserocket.com/v1/partner_carriers/{partnerCarrierID}");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://platform.roserocket.com/v1/partner_carriers/{partnerCarrierID}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /partner_carriers/{partnerCarrierID}`

*Update partner carrier by ID*

> Body parameter

```json
{
  "created_at": "2019-02-21T15:32:17Z",
  "updated_at": "2019-02-21T15:32:17Z",
  "id": "string",
  "org_id": "string",
  "qb_external_id": "string",
  "external_id": "string",
  "name": "string",
  "address_1": "string",
  "address_2": "string",
  "suite": "string",
  "city": "string",
  "postal": "string",
  "phone": "string",
  "phone_ext": "string",
  "fax": "string",
  "email": "string",
  "country": "string",
  "state": "string",
  "timezone": "string",
  "dispatch_contact_name": "string",
  "dispatch_contact_email": "string",
  "billing_contact_name": "string",
  "billing_contact_email": "string",
  "sales_contact_name": "string",
  "sales_contact_email": "string",
  "motor_carrier_id": "string",
  "dept_of_transportation_id": "string",
  "standard_carrier_alpha_code": "string",
  "provincial_operating_authority_num": "string"
}
```

<h3 id="updatepartnercarrierbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|partnerCarrierID|path|string(uuid)|true|ID of the partner carrier|
|body|body|[PartnerCarrier](#schemapartnercarrier)|true|partner Carrier object|

> Example responses

> 200 Response

```json
{
  "partner_carrier": {
    "created_at": "2019-02-21T15:32:17Z",
    "updated_at": "2019-02-21T15:32:17Z",
    "id": "string",
    "org_id": "string",
    "qb_external_id": "string",
    "external_id": "string",
    "name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "fax": "string",
    "email": "string",
    "country": "string",
    "state": "string",
    "timezone": "string",
    "dispatch_contact_name": "string",
    "dispatch_contact_email": "string",
    "billing_contact_name": "string",
    "billing_contact_email": "string",
    "sales_contact_name": "string",
    "sales_contact_email": "string",
    "motor_carrier_id": "string",
    "dept_of_transportation_id": "string",
    "standard_carrier_alpha_code": "string",
    "provincial_operating_authority_num": "string"
  }
}
```

<h3 id="updatepartnercarrierbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="updatepartnercarrierbyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» partner_carrier|[PartnerCarrier](#schemapartnercarrier)|false|none|A partner carrier|
|»» created_at|string(date-time)|false|none|The timestamp for the creation of the partner carrier|
|»» updated_at|string(date-time)|false|none|The timestamp for the last update of the partner carrier|
|»» id|string(uuid)|false|none|none|
|»» org_id|string(uuid)|false|none|The uuid for the organization of the partner carrier|
|»» qb_external_id|string|false|none|The external identifier for the partner carrier in QBO|
|»» external_id|string|false|none|the external identifier for the partner carrier|
|»» name|string|false|none|The name of the partner carrier|
|»» address_1|string|false|none|The first address line of the partner carrier|
|»» address_2|string|false|none|The second address line of the partner carrier|
|»» suite|string|false|none|The suite of the partner carrier's address|
|»» city|string|false|none|The city of the partner carrier's address|
|»» postal|string|false|none|The postal code of the partner carrier's address|
|»» phone|string|false|none|The phone number of the partner carrier|
|»» phone_ext|string|false|none|The phone extension of the partner carrier|
|»» fax|string|false|none|The fax number of the partner carrier|
|»» email|string|false|none|The email address of the partner carrier|
|»» country|string|false|none|The country of the partner carrier|
|»» state|string|false|none|The state of the partner carrier|
|»» timezone|string|false|none|The timezone in which the partner carrier resides|
|»» dispatch_contact_name|string|false|none|The contact name for dispatches to partner carrier|
|»» dispatch_contact_email|string|false|none|The contact email for dispatches to partner carrier|
|»» billing_contact_name|string|false|none|The contact name for billing to partner carrier|
|»» billing_contact_email|string|false|none|The contact email for billing to partner carrier|
|»» sales_contact_name|string|false|none|The contact name for sales to partner carrier|
|»» sales_contact_email|string|false|none|The contact email for sales to partner carrier|
|»» motor_carrier_id|string|false|none|The motor carrier id of the partner carrier|
|»» dept_of_transportation_id|string|false|none|The partner carrier's department of transportation id|
|»» standard_carrier_alpha_code|string|false|none|The SCAC of the partner carrier|
|»» provincial_operating_authority_num|string|false|none|The provincial operating authority number for the partner carrier|

<aside class="success">
This operation does not require authentication
</aside>

## deletePartnerCarrierByID

<a id="opIddeletePartnerCarrierByID"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE https://platform.roserocket.com/v1/partner_carriers/{partnerCarrierID} \
  -H 'Accept: application/json'

```

```http
DELETE https://platform.roserocket.com/v1/partner_carriers/{partnerCarrierID} HTTP/1.1
Host: platform.roserocket.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://platform.roserocket.com/v1/partner_carriers/{partnerCarrierID}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://platform.roserocket.com/v1/partner_carriers/{partnerCarrierID}',
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

result = RestClient.delete 'https://platform.roserocket.com/v1/partner_carriers/{partnerCarrierID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('https://platform.roserocket.com/v1/partner_carriers/{partnerCarrierID}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://platform.roserocket.com/v1/partner_carriers/{partnerCarrierID}");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://platform.roserocket.com/v1/partner_carriers/{partnerCarrierID}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /partner_carriers/{partnerCarrierID}`

*Delete partner carrier by ID*

<h3 id="deletepartnercarrierbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|partnerCarrierID|path|string(uuid)|true|ID of the partner carrier|

> Example responses

> 200 Response

```json
{
  "partner_carrier": {
    "created_at": "2019-02-21T15:32:17Z",
    "updated_at": "2019-02-21T15:32:17Z",
    "id": "string",
    "org_id": "string",
    "qb_external_id": "string",
    "external_id": "string",
    "name": "string",
    "address_1": "string",
    "address_2": "string",
    "suite": "string",
    "city": "string",
    "postal": "string",
    "phone": "string",
    "phone_ext": "string",
    "fax": "string",
    "email": "string",
    "country": "string",
    "state": "string",
    "timezone": "string",
    "dispatch_contact_name": "string",
    "dispatch_contact_email": "string",
    "billing_contact_name": "string",
    "billing_contact_email": "string",
    "sales_contact_name": "string",
    "sales_contact_email": "string",
    "motor_carrier_id": "string",
    "dept_of_transportation_id": "string",
    "standard_carrier_alpha_code": "string",
    "provincial_operating_authority_num": "string"
  },
  "services": [
    {
      "created_at": "2019-02-21T15:32:17Z",
      "updated_at": "2019-02-21T15:32:17Z",
      "id": "string",
      "org_id": "string",
      "carrier_app_id": "string",
      "tariff_id": "string",
      "name": "string",
      "is_active": true,
      "carrier_credential_json": "string",
      "min_markup": 0,
      "max_markup": 0,
      "default_markup": 0,
      "default_fuel_surcharge": 0,
      "currency_id": "string",
      "partner_carrier_id": "string",
      "service_type_id": "string",
      "service_type_display_name": "string",
      "address_1": "string",
      "address_2": "string",
      "suite": "string",
      "city": "string",
      "postal": "string",
      "phone": "string",
      "phone_ext": "string",
      "fax": "string",
      "email": "string",
      "country": "string",
      "state": "string",
      "timezone": "string",
      "primary_contact_name": "string",
      "primary_contact_email": "string",
      "dispatch_contact_name": "string",
      "dispatch_contact_email": "string",
      "billing_contact_name": "string",
      "billing_contact_email": "string"
    }
  ]
}
```

<h3 id="deletepartnercarrierbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ApiError](#schemaapierror)|

<h3 id="deletepartnercarrierbyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» partner_carrier|[PartnerCarrier](#schemapartnercarrier)|false|none|A partner carrier|
|»» created_at|string(date-time)|false|none|The timestamp for the creation of the partner carrier|
|»» updated_at|string(date-time)|false|none|The timestamp for the last update of the partner carrier|
|»» id|string(uuid)|false|none|none|
|»» org_id|string(uuid)|false|none|The uuid for the organization of the partner carrier|
|»» qb_external_id|string|false|none|The external identifier for the partner carrier in QBO|
|»» external_id|string|false|none|the external identifier for the partner carrier|
|»» name|string|false|none|The name of the partner carrier|
|»» address_1|string|false|none|The first address line of the partner carrier|
|»» address_2|string|false|none|The second address line of the partner carrier|
|»» suite|string|false|none|The suite of the partner carrier's address|
|»» city|string|false|none|The city of the partner carrier's address|
|»» postal|string|false|none|The postal code of the partner carrier's address|
|»» phone|string|false|none|The phone number of the partner carrier|
|»» phone_ext|string|false|none|The phone extension of the partner carrier|
|»» fax|string|false|none|The fax number of the partner carrier|
|»» email|string|false|none|The email address of the partner carrier|
|»» country|string|false|none|The country of the partner carrier|
|»» state|string|false|none|The state of the partner carrier|
|»» timezone|string|false|none|The timezone in which the partner carrier resides|
|»» dispatch_contact_name|string|false|none|The contact name for dispatches to partner carrier|
|»» dispatch_contact_email|string|false|none|The contact email for dispatches to partner carrier|
|»» billing_contact_name|string|false|none|The contact name for billing to partner carrier|
|»» billing_contact_email|string|false|none|The contact email for billing to partner carrier|
|»» sales_contact_name|string|false|none|The contact name for sales to partner carrier|
|»» sales_contact_email|string|false|none|The contact email for sales to partner carrier|
|»» motor_carrier_id|string|false|none|The motor carrier id of the partner carrier|
|»» dept_of_transportation_id|string|false|none|The partner carrier's department of transportation id|
|»» standard_carrier_alpha_code|string|false|none|The SCAC of the partner carrier|
|»» provincial_operating_authority_num|string|false|none|The provincial operating authority number for the partner carrier|
|» services|[[Service](#schemaservice)]|false|none|[A service offered by a carrier]|
|»» created_at|string(date-time)|false|none|The timestamp for the creation of the service|
|»» updated_at|string(date-time)|false|none|The timestamp for the last update of the service|
|»» id|string(uuid)|false|none|none|
|»» org_id|string(uuid)|false|none|The uuid for the organization of the service|
|»» carrier_app_id|string|false|none|The id of the carrier app associated with the service|
|»» tariff_id|string|false|none|The id of the tariff associated with the service|
|»» name|string|false|none|The name of the service|
|»» is_active|boolean|false|none|Whether or not the service is active|
|»» carrier_credential_json|string|false|none|The unique json credential for the service|
|»» min_markup|number|false|none|The minimum markup of the service|
|»» max_markup|number|false|none|The maximum markup of the service|
|»» default_markup|number|false|none|The default markup of the service|
|»» default_fuel_surcharge|number|false|none|The default fuel surcharge of the service|
|»» currency_id|string|false|none|The type of currency of the service|
|»» partner_carrier_id|string(uuid,)|false|none|The ID of the partner carrier associated with the service|
|»» service_type_id|string|false|none|The id of the service's type|
|»» service_type_display_name|string|false|none|The display name for the service's type|
|»» address_1|string|false|none|The first address line of the service|
|»» address_2|string|false|none|The second address line of the service|
|»» suite|string|false|none|The suite of the service's address|
|»» city|string|false|none|The city of the service's address|
|»» postal|string|false|none|The postal code of the service's address|
|»» phone|string|false|none|The phone number of the service|
|»» phone_ext|string|false|none|The phone extension of the service|
|»» fax|string|false|none|The fax number of the service|
|»» email|string|false|none|The email address of the service|
|»» country|string|false|none|The country of the service|
|»» state|string|false|none|The state of the service|
|»» timezone|string|false|none|The timezone in which the service resides|
|»» primary_contact_name|string|false|none|The name of the service's primary contact|
|»» primary_contact_email|string|false|none|The email of the service's primary contact|
|»» dispatch_contact_name|string|false|none|The name of the service's dispatch contact|
|»» dispatch_contact_email|string|false|none|The email of the service's dispatch contact|
|»» billing_contact_name|string|false|none|The name of the service's billing contact|
|»» billing_contact_email|string|false|none|The email of the service's billing contact|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocSorder">Order</h2>

<a id="schemaorder"></a>

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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
  "pickup_start_at": "2019-02-21T15:32:17Z",
  "pickup_end_at": "2019-02-21T15:32:17Z",
  "pickup_appt_start_at": "2019-02-21T15:32:17Z",
  "pickup_appt_end_at": "2019-02-21T15:32:17Z",
  "delivery_start_at": "2019-02-21T15:32:17Z",
  "delivery_end_at": "2019-02-21T15:32:17Z",
  "delivery_appt_start_at": "2019-02-21T15:32:17Z",
  "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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

*Customer's order*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|read-only|Auto generated system ID|
|sequence_id|integer|false|read-only|Auto generated sequence ID per customer|
|external_id|string|false|none|External ID for mapping the order to an external system. This field value can be _null_|
|public_id|string|false|read-only|Auto generated human readable ID|
|customer|[OrderCustomer](#schemaordercustomer)|false|none|Customer|
|origin|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|destination|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|billing|[OrderAddress](#schemaorderaddress)|true|none|Order address|
|status|string|false|read-only|Order Status|
|billing_option|string|false|none|Billing Option|
|notes|string|false|none|Notes that will appear on BOL|
|po_num|string|false|none|Purchase order numbers (if multiple use comma separated values)|
|tender_num|string|false|none|Tender number|
|ref_num|string|false|none|Reference number|
|custom_broker|string|false|none|Custom broker information|
|declared_value|number(float)|false|none|Declared value|
|declared_value_currency|string|false|none|Declared value currency|
|pickup_start_at|string(date-time)|false|none|Pickup time range (start)|
|pickup_end_at|string(date-time)|false|none|Pickup time range (end)|
|pickup_appt_start_at|string(date-time)|false|none|Pickup appointment time range (start). This field value can be _null_|
|pickup_appt_end_at|string(date-time)|false|none|Pickup appointment time range (end). This field value can be _null_|
|delivery_start_at|string(date-time)|false|none|Expected delivery time range (start). This field value can be _null_|
|delivery_end_at|string(date-time)|false|none|Expected delivery time range (end). This field value can be _null_|
|delivery_appt_start_at|string(date-time)|false|none|Delivery appointment time range (start). This field value can be _null_|
|delivery_appt_end_at|string(date-time)|false|none|Delivery appointment time range (end). This field value can be _null_|
|dim_type|string|false|none|Dimension type|
|commodities|[[Commodity](#schemacommodity)]|false|none|Commodities items|
|accessorials|[string]|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|new|
|status|saved|
|status|cancelled|
|status|quoting|
|status|quoted|
|status|no-quote|
|status|spot-quote-requested|
|status|pending-dispatch|
|status|dispatched|
|status|in-transit|
|status|delivered|
|status|archived|
|status|invoice-created|
|status|invoice-sent|
|status|invoice-paid|
|status|claim|
|status|draft-quick-quote|
|status|quick-quoting|
|status|quick-quoted|
|status|no-quick-quote|
|status|spot-qq-requested|
|status|pickup-request|
|status|rejected|
|billing_option|prepaid|
|billing_option|collect|
|billing_option|thirdparty|
|declared_value_currency|cad|
|declared_value_currency|usd|
|dim_type|ltl|
|dim_type|ftl|
|dim_type|volume|

<h2 id="tocSorderaddress">OrderAddress</h2>

<a id="schemaorderaddress"></a>

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
  "bus_hours_start_at": "2019-02-21T15:32:17Z",
  "bus_hours_end_at": "2019-02-21T15:32:17Z"
}

```

*Order address*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|address_book_id|string(uuid)|false|read-only|Auto generated address book id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_id, you must leave address_book_external_id empty.|
|address_book_external_id|string(uuid)|false|none|Address book external id. This field value can be _null_. Leave this field as null if you want to manually specify the address. If you want to populate the address using address_book_external_id, you must leave address_book_id empty.|
|org_name|string|false|none|Organization name|
|contact_name|string|false|none|Contact name|
|address_1|string|false|none|Address line 1|
|address_2|string|false|none|Address line 2|
|suite|string|false|none|Suite number|
|city|string|false|none|City|
|state|string|false|none|State / Province|
|country|string|false|none|Country (2 letter ISO)|
|postal|string|false|none|Postal / Zip code|
|phone|string|false|none|Phone number|
|phone_ext|string|false|none|Phone extension|
|email|string|false|none|Email|
|fax|string|false|none|Fax|
|latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|bus_hours_start_at|string(date-time)|false|none|Business hours range (start). This field value can be _null_|
|bus_hours_end_at|string(date-time)|false|none|Business hours range (end). This field value can be _null_|

<h2 id="tocSordercustomer">OrderCustomer</h2>

<a id="schemaordercustomer"></a>

```json
{
  "id": "string",
  "external_id": "string",
  "short_code": "string"
}

```

*Customer*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|read-only|Auto generated customer id|
|external_id|string|false|read-only|Customer external id. This field value can be _null_|
|short_code|string|false|read-only|Customer's short code|

<h2 id="tocScommodity">Commodity</h2>

<a id="schemacommodity"></a>

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

*Commodity item*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|read-only|Auto generated commodity id|
|measurement_unit|string|false|none|Measurement unit|
|weight_unit|string|false|none|Weight unit|
|freight_class|string|false|none|Freight class|
|commodity_type|string|false|none|Commodity type|
|commodity_type_other|string|false|none|If commodity type is set to _other_, then this field must have value|
|description|string|false|none|Description of the commodity|
|feet|number(float)|false|none|Total feet in length of the truck the commodity is occupying. This field must have value if order's dimension type is set to _ftl_|
|volume|number(float)|false|none|Total volume of the commodity item. This field must have value if order's dimension type is set to _volume_|
|length|number(float)|false|none|Length of the commodity|
|width|number(float)|false|none|Width of the commodity|
|height|number(float)|false|none|Height of the commodity|
|weight|number(float)|false|none|Weight of the commodity|
|nmfc|string|false|none|NMFC number|
|is_stackable|boolean|false|none|Is this commodity can be stacked?|
|quantity|integer|false|none|Quantity of the commodity|
|pieces|integer|false|none|Total number of pieces. This field value can be _null_|
|sku|string|false|none|SKU number|

#### Enumerated Values

|Property|Value|
|---|---|
|measurement_unit|inch|
|measurement_unit|cm|
|weight_unit|lb|
|weight_unit|kg|
|commodity_type|skid|
|commodity_type|other|

<h2 id="tocSleg">Leg</h2>

<a id="schemaleg"></a>

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
  "origin_start_at": "2019-02-21T15:32:17Z",
  "origin_end_at": "2019-02-21T15:32:17Z",
  "origin_appt_start_at": "2019-02-21T15:32:17Z",
  "origin_appt_end_at": "2019-02-21T15:32:17Z",
  "destination_start_at": "2019-02-21T15:32:17Z",
  "destination_end_at": "2019-02-21T15:32:17Z",
  "destination_appt_start_at": "2019-02-21T15:32:17Z",
  "destination_appt_end_at": "2019-02-21T15:32:17Z",
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
    "origin_arrived_at": "2019-02-21T15:32:17Z",
    "origin_in_at": "2019-02-21T15:32:17Z",
    "origin_pickedup_at": "2019-02-21T15:32:17Z",
    "origin_out_at": "2019-02-21T15:32:17Z",
    "destination_arrived_at": "2019-02-21T15:32:17Z",
    "destination_in_at": "2019-02-21T15:32:17Z",
    "destination_delivered_at": "2019-02-21T15:32:17Z",
    "destination_out_at": "2019-02-21T15:32:17Z"
  }
}

```

*Leg*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|read-only|Auto generated system ID|
|sequence_id|integer|false|read-only|Auto generated sequence ID per customer|
|version|integer|false|read-only|Auto generated version number (incremental)|
|external_id|string|false|none|External ID for mapping the leg to an external system. This field value can be _null_|
|public_id|string|false|read-only|Auto generated human readable ID|
|order_id|string|false|read-only|Related order ID|
|manifest_id|string|false|none|Related manifest ID (assigned). This field value can be _null_|
|origin_stop_id|string|false|read-only|Stop ID of the origin (only if this leg has been assigned to a manifest). This field value can be _null_|
|destination_stop_id|string|false|read-only|Stop ID of the destination (only if this leg has been assigned to a manifest). This field value can be _null_|
|origin|[LegAddress](#schemalegaddress)|false|none|Leg address|
|destination|[LegAddress](#schemalegaddress)|false|none|Leg address|
|status|string|false|read-only|Leg Status|
|origin_start_at|string(date-time)|false|none|Origin ready time range (start)|
|origin_end_at|string(date-time)|false|none|Origin ready time range (end)|
|origin_appt_start_at|string(date-time)|false|none|Origin appointment time range (start). This field value can be _null_|
|origin_appt_end_at|string(date-time)|false|none|Origin appointment time range (end). This field value can be _null_|
|destination_start_at|string(date-time)|false|none|Destination expected time range (start). This field value can be _null_|
|destination_end_at|string(date-time)|false|none|Destination expected time range (end). This field value can be _null_|
|destination_appt_start_at|string(date-time)|false|none|Destination appointment time range (start). This field value can be _null_|
|destination_appt_end_at|string(date-time)|false|none|Destination appointment time range (end). This field value can be _null_|
|commodities|[[Commodity](#schemacommodity)]|false|none|Commodities items|
|accessorials|[string]|false|none|none|
|history|[LegHistory](#schemaleghistory)|false|none|Historical timestamps of a leg|

#### Enumerated Values

|Property|Value|
|---|---|
|status|available|
|status|pending|
|status|dispatched|
|status|arrived_origin|
|status|in_origin|
|status|loaded|
|status|departed_origin|
|status|arrived_destination|
|status|in_destination|
|status|unloaded|
|status|departed_destination|
|status|cancelled|
|status|problem|

<h2 id="tocSlegaddress">LegAddress</h2>

<a id="schemalegaddress"></a>

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

*Leg address*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|terminal_id|string(uuid)|false|none|Related terminal ID. This field value can be _null_|
|org_name|string|false|none|Organization name|
|contact_name|string|false|none|Contact name|
|address_1|string|false|none|Address line 1|
|address_2|string|false|none|Address line 2|
|suite|string|false|none|Suite number|
|city|string|false|none|City|
|state|string|false|none|State / Province|
|country|string|false|none|Country (2 letter ISO)|
|postal|string|false|none|Postal / Zip code|
|phone|string|false|none|Phone number|
|phone_ext|string|false|none|Phone extension|
|email|string|false|none|Email|
|fax|string|false|none|Fax|
|latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|

<h2 id="tocSleghistory">LegHistory</h2>

<a id="schemaleghistory"></a>

```json
{
  "origin_arrived_at": "2019-02-21T15:32:17Z",
  "origin_in_at": "2019-02-21T15:32:17Z",
  "origin_pickedup_at": "2019-02-21T15:32:17Z",
  "origin_out_at": "2019-02-21T15:32:17Z",
  "destination_arrived_at": "2019-02-21T15:32:17Z",
  "destination_in_at": "2019-02-21T15:32:17Z",
  "destination_delivered_at": "2019-02-21T15:32:17Z",
  "destination_out_at": "2019-02-21T15:32:17Z"
}

```

*Historical timestamps of a leg*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|origin_arrived_at|string(date-time)|false|none|The timestamp of when the driver/partner arrived at origin|
|origin_in_at|string(date-time)|false|none|The timestamp of when the driver/partner in at origin|
|origin_pickedup_at|string(date-time)|false|none|The timestamp of when the driver/partner picked up at origin|
|origin_out_at|string(date-time)|false|none|The timestamp of when the driver/partner out at origin|
|destination_arrived_at|string(date-time)|false|none|The timestamp of when the driver/partner arrived at destination|
|destination_in_at|string(date-time)|false|none|The timestamp of when the driver/partner in at destination|
|destination_delivered_at|string(date-time)|false|none|The timestamp of when the driver/partner delievered up at destination|
|destination_out_at|string(date-time)|false|none|The timestamp of when the driver/partner out at destination|

<h2 id="tocSstop">Stop</h2>

<a id="schemastop"></a>

```json
{
  "id": "string",
  "manifest_id": "string",
  "ordinal": 0,
  "type": "stop",
  "schedule_start_at": "2019-02-21T15:32:17Z",
  "schedule_end_at": "2019-02-21T15:32:17Z",
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

*Stop*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|read-only|Auto generated system ID|
|manifest_id|string|false|read-only|Related Manifest ID|
|ordinal|integer|false|read-only|Ordinal of the stop in the manifest|
|type|string|false|read-only|Stop Type|
|schedule_start_at|string(date-time)|false|none|Scheduled time range (start)|
|schedule_end_at|string(date-time)|false|none|Scheduled time range (end)|
|org_name|string|false|none|Organization name|
|contact_name|string|false|none|Contact name|
|address_1|string|false|none|Address line 1|
|address_2|string|false|none|Address line 2|
|suite|string|false|none|Suite number|
|city|string|false|none|City|
|state|string|false|none|State / Province|
|country|string|false|none|Country (2 letter ISO)|
|postal|string|false|none|Postal / Zip code|
|phone|string|false|none|Phone number|
|phone_ext|string|false|none|Phone extension|
|email|string|false|none|Email|
|fax|string|false|none|Fax|
|latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|

#### Enumerated Values

|Property|Value|
|---|---|
|type|stop|
|type|start|
|type|end|
|type|terminal|

<h2 id="tocScustomer">Customer</h2>

<a id="schemacustomer"></a>

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

*Customer*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|read-only|Auto generated customner id|
|external_id|string|false|read-only|Customer external id. This field value can be _null_|
|short_code|string|false|read-only|Customer's short code|
|name|string|false|none|Organization name|
|address_1|string|false|none|Address line 1|
|address_2|string|false|none|Address line 2|
|suite|string|false|none|Suite number|
|city|string|false|none|City|
|state|string|false|none|State / Province|
|country|string|false|none|Country (2 letter ISO)|
|postal|string|false|none|Postal / Zip code|
|phone|string|false|none|Phone number|
|phone_ext|string|false|none|Phone extension|
|email|string|false|none|Email|
|fax|string|false|none|Fax|
|latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|default_billing_option|string|false|none|Billing Option|
|default_dim_type|string|false|none|Dimension type|
|default_order_notes|string|false|none|This notes will always show up as internal note everytime an order is created for this customer|
|currency|string|false|none|Currency used when doing billing/invoicing|
|is_active|boolean|false|none|Is customer active?|
|credit_limit|number(float)|false|none|Credit limit for this customer|
|credit_balance|number(float)|false|none|Credit balance for this customer|
|dispatch__contact_name|string|false|none|Dispatch contact name|
|dispatch_contact_phone|string|false|none|Dispatch contact phone|
|dispatch_contact_email|string|false|none|Dispatch contact email|
|billing_contact_name|string|false|none|Billing contact name|
|billing_contact_phone|string|false|none|Billing contact phone|
|billing_contact_email|string|false|none|Billing contact email|
|sales_contact_name|string|false|none|Sales contact name|
|sales_contact_phone|string|false|none|Sales contact phone|
|sales_contact_email|string|false|none|Sales contact email|
|management_contact_name|string|false|none|Management contact name|
|management_contact_phone|string|false|none|Management contact phone|
|management_contact_email|string|false|none|Management contact email|
|other_contact_name|string|false|none|Other contact name|
|other_contact_phone|string|false|none|Other contact phone|
|other_contact_email|string|false|none|Other contact email|

#### Enumerated Values

|Property|Value|
|---|---|
|default_billing_option|prepaid|
|default_billing_option|collect|
|default_billing_option|thirdparty|
|default_dim_type|ltl|
|default_dim_type|ftl|
|default_dim_type|volume|
|currency|cad|
|currency|usd|

<h2 id="tocSspotquote">SpotQuote</h2>

<a id="schemaspotquote"></a>

```json
{
  "notes": "string",
  "est_delivery_start_at": "2019-02-21T15:32:17Z",
  "est_delivery_end_at": "2019-02-21T15:32:17Z",
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

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|notes|string|false|none|Notes|
|est_delivery_start_at|string(date-time)|false|none|Estimated delivery time range (start). This field value can be _null_|
|est_delivery_end_at|string(date-time)|false|none|Estimated delivery time range (end). This field value can be _null_|
|freight_charge|number(float)|false|none|Freight charge|
|original_freight_charge|number(float)|false|none|Orginal freight charge. This field value can be _null_|
|fuel_charge|number(float)|false|none|Fuel charge|
|original_fuel_charge|number(float)|false|none|Orginal fuel charge. This field value can be _null_|
|accessorial_charges|[object]|false|none|Accessorials charges|
|» accessorial_id|string(uuid)|false|none|Accessorial id|
|» charge|number(float)|false|none|Accessorial charge|
|» original_charge|number(float)|false|none|Orginal accessorial charge. This field value can be _null_|

<h2 id="tocSquote">Quote</h2>

<a id="schemaquote"></a>

```json
{
  "id": "string",
  "order_id": "string",
  "currency": "cad",
  "customer_service_id": "string",
  "is_expired": true,
  "pickup_start_at": "2019-02-21T15:32:17Z",
  "pickup_end_at": "2019-02-21T15:32:17Z",
  "est_delivery_start_at": "2019-02-21T15:32:17Z",
  "est_delivery_end_at": "2019-02-21T15:32:17Z",
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

*Quote*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|read-only|Auto generated quote id|
|order_id|string(uuid)|false|none|Order id this quote is associated to|
|currency|string|false|none|Declared value currency|
|customer_service_id|string(uuid)|false|none|Customer's service of this quote generated from|
|is_expired|boolean|false|none|Is this quote has expired?|
|pickup_start_at|string(date-time)|false|none|Pickup time range (start)|
|pickup_end_at|string(date-time)|false|none|Pickup time range (end)|
|est_delivery_start_at|string(date-time)|false|none|Estimated delivery time range (start). This field value can be _null_|
|est_delivery_end_at|string(date-time)|false|none|Estimated delivery time range (end). This field value can be _null_|
|notes|string|false|none|Notes|
|error_message|string|false|none|Error message|
|status|string|false|none|Status|
|charges|object|false|none|none|
|» type|string(uuid)|false|none|Type|
|» quote_id|string(uuid)|false|read-only|Quote id this item is associated to|
|» description|string|false|none|Description|
|» quantity|integer|false|none|Unit quantity|
|» unit_price|integer|false|none|Unit price|
|» total|integer|false|none|Total|
|freight|number(float)|false|none|Freight charge|
|fuel|number(float)|false|none|Fuel charge|
|accessorials|number(float)|false|none|Accessorials charge|
|total|number(float)|false|none|Total charge|

#### Enumerated Values

|Property|Value|
|---|---|
|currency|cad|
|currency|usd|
|status|quote-success|
|status|quote-pending|
|status|quote-rejected|
|status|quote-error|
|status|dispatch-success|
|status|dispatch-pending|
|status|dispatch-rejected|
|status|dispatch-error|
|type|freight|
|type|freight-cwt|
|type|freight-cwt-min|
|type|freight-spot|
|type|freight-pallets|
|type|freight-pallets-min|
|type|accessorial|
|type|fuel|
|type|misc|

<h2 id="tocSapierror">ApiError</h2>

<a id="schemaapierror"></a>

```json
{
  "error_code": "string",
  "error_message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|error_code|string|false|none|Error code|
|error_message|string|false|none|Error message|

<h2 id="tocSmanifest">Manifest</h2>

<a id="schemamanifest"></a>

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
  "start_at": "2019-02-21T15:32:17Z",
  "status": "planning",
  "dispatched_at": "2019-02-21T15:32:17Z",
  "completed_at": "2019-02-21T15:32:17Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|Id of the manifest|
|nickname|string|false|none|The nickname for the manifest|
|org_id|string(uuid)|false|none|Id of the organization to which the manifest belongs|
|vehicle_id|string(uuid)|false|none|Id of the vehicle corresponding to the manifest|
|dispathcer_user_id|string(uuid)|false|none|Id of the dispatcher of the manifest|
|driver_user_id|string(uuid)|false|none|Id of the driver corresponding to the manifest|
|trailer_id|string(uuid)|false|none|Id of the trailer corresponding to the manifest|
|partner_carrier_id|string(uuid)|false|none|Id of the partner/carrier that corresponds to the manifest|
|partner_carrier_service_id|string(uuid)|false|none|Id of the partner/carrier service that corresponds to the manifest|
|sequential_id|string(uuid)|false|none|The manifest's sequential id|
|full_id|string(uuid)|false|none|The full id of the string|
|start_at|string(date-time)|false|none|The time at which the manifest was scheduled to start|
|status|string|false|none|The status of the manifest|
|dispatched_at|string(date-time)|false|none|The time at which the manifest was dispatched|
|completed_at|string(date-time)|false|none|The time at which the manifest was completed|

#### Enumerated Values

|Property|Value|
|---|---|
|status|planning|
|status|planned|
|status|cancelled|
|status|assigned|
|status|accepted|
|status|rejected|
|status|problem|
|status|completed|
|status|bill-created|
|status|bill-sent|
|status|bill-paid|

<h2 id="tocSmanifestevent">ManifestEvent</h2>

<a id="schemamanifestevent"></a>

```json
{
  "id": "string",
  "created_at": "2019-02-21T15:32:17Z",
  "updated_at": "2019-02-21T15:32:17Z",
  "user_id": "2019-02-21T15:32:17Z",
  "manifest_id": "string",
  "data": {
    "author": "string",
    "text": "string",
    "type": "notes"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|The id of the manifest event|
|created_at|string(date-time)|false|none|The time of the event's creation|
|updated_at|string(date-time)|false|none|The time the event was last updated|
|user_id|string(date-time)|false|none|The id of the user who created the event|
|manifest_id|string(uuid)|false|none|The id of the manifest for which the event belongs|
|data|object|false|none|none|
|» author|string|false|none|The name of the user who authored the event|
|» text|string|false|none|The contents of the message|
|» type|string|false|none|The type of manifest message|

#### Enumerated Values

|Property|Value|
|---|---|
|type|notes|

<h2 id="tocSmanifestpayment">ManifestPayment</h2>

<a id="schemamanifestpayment"></a>

```json
{
  "id": "string",
  "created_at": "2019-02-21T15:32:17Z",
  "updated_at": "2019-02-21T15:32:17Z",
  "created_by": "2019-02-21T15:32:17Z",
  "manifest_id": "string",
  "currency_id": "cad",
  "full_id": "string",
  "revision": 0,
  "send_to_email": "string",
  "cc_to_email": "string",
  "pay_to_company_name": "string",
  "pay_to_contact_name": "string",
  "pay_to_address_1": "string",
  "pay_to_address_2": "string",
  "pay_to_city": "string",
  "pay_to_state": "string",
  "pay_to_country": "string",
  "pay_to_timezone": "string",
  "notes": "string",
  "sub_total_amount": 0,
  "tax_amount": 0,
  "total_amount": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|The id of the manifest payment|
|created_at|string(date-time)|false|none|The time of the payment's creation|
|updated_at|string(date-time)|false|none|The time the payment was last updated|
|created_by|string(date-time)|false|none|The id of the user who created the payment|
|manifest_id|string(uuid)|false|none|The id of the manifest for which the payment belongs|
|currency_id|string|false|none|The currency of the payment|
|full_id|string|false|none|The full id of the payment. This includes the full_id of the payment's manifest|
|revision|integer|false|none|The revision number of the payment|
|send_to_email|string|false|none|The email of the recipient of the payment|
|cc_to_email|string|false|none|The email of the cc recipient of the payment|
|pay_to_company_name|string|false|none|The company name of the recipient of the payment|
|pay_to_contact_name|string|false|none|The contact name of the recipient of the payment|
|pay_to_address_1|string|false|none|Line 1 of the address of the recipient of payment|
|pay_to_address_2|string|false|none|Line 2 of the address of the recipient of payment|
|pay_to_city|string|false|none|The city of recipient of the payment|
|pay_to_state|string|false|none|The state/province of the recipient of the payment|
|pay_to_country|string|false|none|The country of the recipient of the payment|
|pay_to_timezone|string|false|none|The timezone of the recipient of the payment|
|notes|string|false|none|Notes on the payment|
|sub_total_amount|number|false|none|The subtotal of the payment|
|tax_amount|number|false|none|The total tax amount of the payment|
|total_amount|number|false|none|The total amount of the payment|

#### Enumerated Values

|Property|Value|
|---|---|
|currency_id|cad|
|currency_id|usd|

<h2 id="tocSmanifestpaymentitem">ManifestPaymentItem</h2>

<a id="schemamanifestpaymentitem"></a>

```json
{
  "id": "string",
  "created_at": "2019-02-21T15:32:17Z",
  "updated_at": "2019-02-21T15:32:17Z",
  "manifest_payment_id": "string",
  "bill_class": "misc",
  "unit_price": 0,
  "quantity": 0,
  "total_amount": 0,
  "description": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|The id of the manifest payment item|
|created_at|string(date-time)|false|none|The time of the payment item's creation|
|updated_at|string(date-time)|false|none|The time the payment item was last updated|
|manifest_payment_id|string(uuid)|false|none|The id of the manifest payment to which the payment belongs|
|bill_class|string|false|none|The bill class of payment item|
|unit_price|number|false|none|The per-unit price of the payment item|
|quantity|number|false|none|The quantity of the payment item|
|total_amount|number|false|none|The total amount of the payment item|
|description|string|false|none|A description of the payment item|

#### Enumerated Values

|Property|Value|
|---|---|
|bill_class|misc|
|bill_class|misc-deduction|
|bill_class|partner-freight|
|bill_class|partner-accessorial|
|bill_class|partner-fuel|
|bill_class|partner-misc|

<h2 id="tocSbulkordercreateresponse">BulkOrderCreateResponse</h2>

<a id="schemabulkordercreateresponse"></a>

```json
{
  "job_id": "string",
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|job_id|string(uuid)|false|none|The id of the bulk create job|
|message|string|false|none|Information about the status of the bulk job.|

<h2 id="tocSbulkorderemailresults">BulkOrderEmailResults</h2>

<a id="schemabulkorderemailresults"></a>

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
          "bus_hours_start_at": "2019-02-21T15:32:17Z",
          "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
          "bus_hours_start_at": "2019-02-21T15:32:17Z",
          "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
          "bus_hours_start_at": "2019-02-21T15:32:17Z",
          "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
        "pickup_start_at": "2019-02-21T15:32:17Z",
        "pickup_end_at": "2019-02-21T15:32:17Z",
        "pickup_appt_start_at": "2019-02-21T15:32:17Z",
        "pickup_appt_end_at": "2019-02-21T15:32:17Z",
        "delivery_start_at": "2019-02-21T15:32:17Z",
        "delivery_end_at": "2019-02-21T15:32:17Z",
        "delivery_appt_start_at": "2019-02-21T15:32:17Z",
        "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|results|[object]|false|none|The results of the bulk create job.|
|» order|[Order](#schemaorder)|false|none|Customer's order|
|» status|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|Imported|
|status|Failed|

<h2 id="tocSlegfilerequest">LegFileRequest</h2>

<a id="schemalegfilerequest"></a>

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

*A request to create a file/document for a leg*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|false|none|The type of leg file|
|url|string|false|none|The url location for the leg file|
|description|string|false|none|A description of the leg file|
|latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|metadata|object|false|none|Metadata object for the leg file|

#### Enumerated Values

|Property|Value|
|---|---|
|type|other|
|type|comm-invoice|
|type|pod|
|type|pop|
|type|pod-sig|
|type|pop-sig|
|type|carrier-invoice|
|type|smc|
|type|bol|

<h2 id="tocSlegfile">LegFile</h2>

<a id="schemalegfile"></a>

```json
{
  "id": "string",
  "created_at": "2019-02-21T15:32:17Z",
  "updated_at": "2019-02-21T15:32:17Z",
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

*The file for the leg*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|The uuid for the leg file|
|created_at|string(date-time)|false|none|The timestamp for the creation of the leg file|
|updated_at|string(date-time)|false|none|The timestamp for the last update of the leg file|
|org_id|string(uuid)|false|none|The uuid for the organization of the leg file|
|leg_id|string(uuid)|false|none|The uuid of the leg corresponding to the leg file|
|uploaded_by|string(uuid)|false|none|The uuid of the user who uploaded the leg file|
|uploaded_at|string(uuid)|false|none|The uuid|
|type|string|false|none|The type of leg file|
|url|string|false|none|The url location for the leg file|
|description|string|false|none|A description of the leg file|
|latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|metadata|object|false|none|Metadata object for the leg file|
|task_id|string(uuid)|false|none|The task id of the leg that corresponds to the leg file|

#### Enumerated Values

|Property|Value|
|---|---|
|type|other|
|type|comm-invoice|
|type|pod|
|type|pop|
|type|pod-sig|
|type|pop-sig|
|type|carrier-invoice|
|type|smc|
|type|bol|

<h2 id="tocSorderfilerequest">OrderFileRequest</h2>

<a id="schemaorderfilerequest"></a>

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

*A request to create a file/document for an order*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|false|none|The type of order file|
|url|string|false|none|The url location for the order file|
|description|string|false|none|A description of the order file|
|latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|metadata|object|false|none|Metadata object for the order file|

#### Enumerated Values

|Property|Value|
|---|---|
|type|other|
|type|comm-invoice|
|type|pod|
|type|pop|
|type|pod-sig|
|type|pop-sig|
|type|carrier-invoice|
|type|smc|
|type|bol|

<h2 id="tocSorderfile">OrderFile</h2>

<a id="schemaorderfile"></a>

```json
{
  "id": "string",
  "created_at": "2019-02-21T15:32:17Z",
  "updated_at": "2019-02-21T15:32:17Z",
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

*The file for the order*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|The uuid for the order file|
|created_at|string(date-time)|false|none|The timestamp for the creation of the order file|
|updated_at|string(date-time)|false|none|The timestamp for the last update of the order file|
|org_id|string(uuid)|false|none|The uuid for the organization of the order file|
|leg_id|string(uuid)|false|none|The uuid of the order corresponding to the order file|
|uploaded_by|string(uuid)|false|none|The uuid of the user who uploaded the order file|
|uploaded_at|string(uuid)|false|none|The uuid|
|type|string|false|none|The type of order file|
|url|string|false|none|The url location for the order file|
|description|string|false|none|A description of the order file|
|latitude|number(float)|false|none|Coordinate (latitude). This field value can be _null_|
|longitude|number(float)|false|none|Coordinate (longitude). This field value can be _null_|
|metadata|object|false|none|Metadata object for the order file|

#### Enumerated Values

|Property|Value|
|---|---|
|type|other|
|type|comm-invoice|
|type|pod|
|type|pop|
|type|pod-sig|
|type|pop-sig|
|type|carrier-invoice|
|type|smc|
|type|bol|

<h2 id="tocSorderandlegsresponse">OrderAndLegsResponse</h2>

<a id="schemaorderandlegsresponse"></a>

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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
      "bus_hours_start_at": "2019-02-21T15:32:17Z",
      "bus_hours_end_at": "2019-02-21T15:32:17Z"
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
    "pickup_start_at": "2019-02-21T15:32:17Z",
    "pickup_end_at": "2019-02-21T15:32:17Z",
    "pickup_appt_start_at": "2019-02-21T15:32:17Z",
    "pickup_appt_end_at": "2019-02-21T15:32:17Z",
    "delivery_start_at": "2019-02-21T15:32:17Z",
    "delivery_end_at": "2019-02-21T15:32:17Z",
    "delivery_appt_start_at": "2019-02-21T15:32:17Z",
    "delivery_appt_end_at": "2019-02-21T15:32:17Z",
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
      "origin_start_at": "2019-02-21T15:32:17Z",
      "origin_end_at": "2019-02-21T15:32:17Z",
      "origin_appt_start_at": "2019-02-21T15:32:17Z",
      "origin_appt_end_at": "2019-02-21T15:32:17Z",
      "destination_start_at": "2019-02-21T15:32:17Z",
      "destination_end_at": "2019-02-21T15:32:17Z",
      "destination_appt_start_at": "2019-02-21T15:32:17Z",
      "destination_appt_end_at": "2019-02-21T15:32:17Z",
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
        "origin_arrived_at": "2019-02-21T15:32:17Z",
        "origin_in_at": "2019-02-21T15:32:17Z",
        "origin_pickedup_at": "2019-02-21T15:32:17Z",
        "origin_out_at": "2019-02-21T15:32:17Z",
        "destination_arrived_at": "2019-02-21T15:32:17Z",
        "destination_in_at": "2019-02-21T15:32:17Z",
        "destination_delivered_at": "2019-02-21T15:32:17Z",
        "destination_out_at": "2019-02-21T15:32:17Z"
      }
    }
  ]
}

```

*An order with its corresponding legs*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|order|[Order](#schemaorder)|false|none|Customer's order|
|legs|[[Leg](#schemaleg)]|false|none|[Leg]|

<h2 id="tocSorderaddressreviserequest">OrderAddressReviseRequest</h2>

<a id="schemaorderaddressreviserequest"></a>

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
    "bus_hours_start_at": "2019-02-21T15:32:17Z",
    "bus_hours_end_at": "2019-02-21T15:32:17Z"
  }
}

```

*A request to change the origin or destination of an order*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|address|[OrderAddress](#schemaorderaddress)|false|none|Order address|

<h2 id="tocSorderauditevent">OrderAuditEvent</h2>

<a id="schemaorderauditevent"></a>

```json
{
  "id": "string",
  "created_at": "2019-02-21T15:32:17Z",
  "updated_at": "2019-02-21T15:32:17Z",
  "user_id": "string",
  "order_id": "string",
  "data": {}
}

```

*An order audit event*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|created_at|string(date-time)|false|none|The timestamp for the creation of the order file|
|updated_at|string(date-time)|false|none|The timestamp for the last update of the order file|
|user_id|string(uuid)|false|none|none|
|order_id|string(uuid)|false|none|none|
|data|object|false|none|none|

<h2 id="tocSservice">Service</h2>

<a id="schemaservice"></a>

```json
{
  "created_at": "2019-02-21T15:32:17Z",
  "updated_at": "2019-02-21T15:32:17Z",
  "id": "string",
  "org_id": "string",
  "carrier_app_id": "string",
  "tariff_id": "string",
  "name": "string",
  "is_active": true,
  "carrier_credential_json": "string",
  "min_markup": 0,
  "max_markup": 0,
  "default_markup": 0,
  "default_fuel_surcharge": 0,
  "currency_id": "string",
  "partner_carrier_id": "string",
  "service_type_id": "string",
  "service_type_display_name": "string",
  "address_1": "string",
  "address_2": "string",
  "suite": "string",
  "city": "string",
  "postal": "string",
  "phone": "string",
  "phone_ext": "string",
  "fax": "string",
  "email": "string",
  "country": "string",
  "state": "string",
  "timezone": "string",
  "primary_contact_name": "string",
  "primary_contact_email": "string",
  "dispatch_contact_name": "string",
  "dispatch_contact_email": "string",
  "billing_contact_name": "string",
  "billing_contact_email": "string"
}

```

*A service offered by a carrier*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|created_at|string(date-time)|false|none|The timestamp for the creation of the service|
|updated_at|string(date-time)|false|none|The timestamp for the last update of the service|
|id|string(uuid)|false|none|none|
|org_id|string(uuid)|false|none|The uuid for the organization of the service|
|carrier_app_id|string|false|none|The id of the carrier app associated with the service|
|tariff_id|string|false|none|The id of the tariff associated with the service|
|name|string|false|none|The name of the service|
|is_active|boolean|false|none|Whether or not the service is active|
|carrier_credential_json|string|false|none|The unique json credential for the service|
|min_markup|number|false|none|The minimum markup of the service|
|max_markup|number|false|none|The maximum markup of the service|
|default_markup|number|false|none|The default markup of the service|
|default_fuel_surcharge|number|false|none|The default fuel surcharge of the service|
|currency_id|string|false|none|The type of currency of the service|
|partner_carrier_id|string(uuid,)|false|none|The ID of the partner carrier associated with the service|
|service_type_id|string|false|none|The id of the service's type|
|service_type_display_name|string|false|none|The display name for the service's type|
|address_1|string|false|none|The first address line of the service|
|address_2|string|false|none|The second address line of the service|
|suite|string|false|none|The suite of the service's address|
|city|string|false|none|The city of the service's address|
|postal|string|false|none|The postal code of the service's address|
|phone|string|false|none|The phone number of the service|
|phone_ext|string|false|none|The phone extension of the service|
|fax|string|false|none|The fax number of the service|
|email|string|false|none|The email address of the service|
|country|string|false|none|The country of the service|
|state|string|false|none|The state of the service|
|timezone|string|false|none|The timezone in which the service resides|
|primary_contact_name|string|false|none|The name of the service's primary contact|
|primary_contact_email|string|false|none|The email of the service's primary contact|
|dispatch_contact_name|string|false|none|The name of the service's dispatch contact|
|dispatch_contact_email|string|false|none|The email of the service's dispatch contact|
|billing_contact_name|string|false|none|The name of the service's billing contact|
|billing_contact_email|string|false|none|The email of the service's billing contact|

<h2 id="tocSpartnercarrier">PartnerCarrier</h2>

<a id="schemapartnercarrier"></a>

```json
{
  "created_at": "2019-02-21T15:32:17Z",
  "updated_at": "2019-02-21T15:32:17Z",
  "id": "string",
  "org_id": "string",
  "qb_external_id": "string",
  "external_id": "string",
  "name": "string",
  "address_1": "string",
  "address_2": "string",
  "suite": "string",
  "city": "string",
  "postal": "string",
  "phone": "string",
  "phone_ext": "string",
  "fax": "string",
  "email": "string",
  "country": "string",
  "state": "string",
  "timezone": "string",
  "dispatch_contact_name": "string",
  "dispatch_contact_email": "string",
  "billing_contact_name": "string",
  "billing_contact_email": "string",
  "sales_contact_name": "string",
  "sales_contact_email": "string",
  "motor_carrier_id": "string",
  "dept_of_transportation_id": "string",
  "standard_carrier_alpha_code": "string",
  "provincial_operating_authority_num": "string"
}

```

*A partner carrier*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|created_at|string(date-time)|false|none|The timestamp for the creation of the partner carrier|
|updated_at|string(date-time)|false|none|The timestamp for the last update of the partner carrier|
|id|string(uuid)|false|none|none|
|org_id|string(uuid)|false|none|The uuid for the organization of the partner carrier|
|qb_external_id|string|false|none|The external identifier for the partner carrier in QBO|
|external_id|string|false|none|the external identifier for the partner carrier|
|name|string|false|none|The name of the partner carrier|
|address_1|string|false|none|The first address line of the partner carrier|
|address_2|string|false|none|The second address line of the partner carrier|
|suite|string|false|none|The suite of the partner carrier's address|
|city|string|false|none|The city of the partner carrier's address|
|postal|string|false|none|The postal code of the partner carrier's address|
|phone|string|false|none|The phone number of the partner carrier|
|phone_ext|string|false|none|The phone extension of the partner carrier|
|fax|string|false|none|The fax number of the partner carrier|
|email|string|false|none|The email address of the partner carrier|
|country|string|false|none|The country of the partner carrier|
|state|string|false|none|The state of the partner carrier|
|timezone|string|false|none|The timezone in which the partner carrier resides|
|dispatch_contact_name|string|false|none|The contact name for dispatches to partner carrier|
|dispatch_contact_email|string|false|none|The contact email for dispatches to partner carrier|
|billing_contact_name|string|false|none|The contact name for billing to partner carrier|
|billing_contact_email|string|false|none|The contact email for billing to partner carrier|
|sales_contact_name|string|false|none|The contact name for sales to partner carrier|
|sales_contact_email|string|false|none|The contact email for sales to partner carrier|
|motor_carrier_id|string|false|none|The motor carrier id of the partner carrier|
|dept_of_transportation_id|string|false|none|The partner carrier's department of transportation id|
|standard_carrier_alpha_code|string|false|none|The SCAC of the partner carrier|
|provincial_operating_authority_num|string|false|none|The provincial operating authority number for the partner carrier|

<h2 id="tocScommodityreviserequest">CommodityReviseRequest</h2>

<a id="schemacommodityreviserequest"></a>

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

*A request to change the commodities of an order/leg*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|commodities|[[Commodity](#schemacommodity)]|false|none|[Commodity item]|

<h2 id="tocSlegaddressreviserequest">LegAddressReviseRequest</h2>

<a id="schemalegaddressreviserequest"></a>

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

*A request to change the origin or destination of an leg*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|address|[LegAddress](#schemalegaddress)|false|none|Leg address|

