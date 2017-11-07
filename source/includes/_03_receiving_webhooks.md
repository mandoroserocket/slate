# Receiving Webhooks

```ruby
require "json"

# Using Sinatra
post "/my/webhook/url" do
  # Retrieve the request's body and parse it as JSON
  event_json = JSON.parse(request.body.read)

  # Do something with event_json

  status 200
end
```

```python
import json
from django.http import HttpResponse

# Using Django
def my_webhook_view(request):
  # Retrieve the request's body and parse it as JSON
  event_json = json.loads(request.body)

  # Do something with event_json

  return HttpResponse(status=200)
```

```php
// Retrieve the request's body and parse it as JSON
$input = @file_get_contents("php://input");
$event_json = json_decode($input);

// Do something with $event_json

http_response_code(200); // PHP 5.4 or greater
```

```java
// Using Spark framework (http://sparkjava.com)
public Object handle(Request request, Response response) {
  // Retrieve the request's body and parse it as JSON
  Event eventJson = APIResource.GSON.fromJson(request.body(), Event.class);

  // Do something with eventJson

  response.status(200);
  return "";
}
```

```javascript
// Using Express
app.post("/my/webhook/url", function(request, response) {
  // Retrieve the request's body and parse it as JSON
  var event_json = JSON.parse(request.body);

  // Do something with event_json

  response.send(200);
});
```

Creating a webhoook endpoint on your server is no different from creating any page on your website. With PHP, you might create a new .php file on your server; with a framework like Sinatra, you would add a new route with the desired URL.

Webhook data is sent as JSON in the POST request body. The full event details are included and can be used directly, after parsing the JSON into an Event object