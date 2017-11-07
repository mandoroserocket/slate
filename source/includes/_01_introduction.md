# Webhooks

Use webhooks to be notified about events that happen in your Rose Rocket instance.

Webhooks lets you register a URL that we will notify anytime an event happens in your account. When the event occurs—for example, when an order is made for a customer, Rose Rocket creates an `Event` object. This object contains all the relevant information about what just happened, including the type of event and the data associated with that event. Rose Rocket then sends the Event object to any URLs in your account's webhooks settings via an HTTP POST request.

<aside class="notice">
An event is an occurrence, such as an order being created, an order changed its status, or an invoice being created. Each occurrence has a corresponding Event object.
</aside>

<aside class="notice">
Webhook endpoints are URLs defined by users to which Rose Rocket sends events. A single event may be sent to many webhook endpoints.
</aside>