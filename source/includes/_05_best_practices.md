# Best Practices

Before going live, test that your webhook is working properly. You can do so by sending dummy test events from the webhooks settings pane. Understand that as these are fake, test events, they will not map to real customers, invoices, charges, or other objects in your account.

If your webhook script performs complex logic, or makes network calls, it's possible the script would timeout before Rose Rocket sees its complete execution. For that reason, you may want to have your webhook endpoint immediately acknowledge receipt by returning a 2xx HTTP status code, and then perform the rest of its duties.

Webhook endpoints may occasionally receive the same event more than once. We advise you to guard against duplicated event receipts by making your event processing idempotent. One way of doing this is logging the events you've processed, and then not processing already-logged events. Additionally, we recommend verifying webhook signatures to confirm that received events are being sent from Rose Rocket.