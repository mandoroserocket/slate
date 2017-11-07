# Configuring

Webhooks are configured in the [webhooks settings](http://roserocket.com/app/webhooks) section of the Settings. Clicking Add endpoint reveals a form to add a new URL for receiving webhooks.

You can enter any URL you'd like to have events sent to, but this should be a dedicated page on your server, coded per the instructions below. The mode determines whether test events or live events are sent to this URL; if you want to send both live and test events to the same URL, you need to create two separate settings. You may add as many URLs as you like, and basic access authentication is supported.

You can also choose to be notified of all event types, or only specific ones.

<aside class="notice">
Common webhook mistakes: The two most common mistakes with webhooks are providing the wrong URL in the Dashboard and the webhook endpoint not returning a 200 status code.
</aside>