# Responding to a webhook

To acknowledge receipt of a webhook, your endpoint should return a 2xx HTTP status code. Any other information returned in the request headers or request body is ignored. All response codes outside this range, including 3xx codes, will indicate to Rose Rocket that you did not receive the webhook. This does mean that a URL redirection or a "Not Modified" response will be treated as a failure.

If a webhook is not successfully received for any reason, Rose Rocket will not try to send the webhook, though you can use the [API](http://www.roserocket.com/api/docs) to reconcile your data with any missed events.

When viewing a specific event information through the Dashboard, you can check how many times we've attempted to send an event to an endpoint by clicking on that endpoint URL in the Webhook details section. This will show you the latest response we received from your endpoint, along with a list of all attempted webhooks and the respective HTTP status codes we received.