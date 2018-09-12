# Types of events

## Order Created

Event Name: `order.created`

```json
{
    "event": "order.created",
    "order_id": "172dfbff-ebd9-4c9c-868c-cb79ef7775ed",
    "timestamp": "2018-01-01T00:00:00Z"
}
```

Occurs whenever an order is created.

## Order Updated

Event Name: `order.updated`

```json
{
    "event": "order.updated",
    "order_id": "172dfbff-ebd9-4c9c-868c-cb79ef7775ed",
    "timestamp": "2018-01-01T00:00:00Z"
}
```

Occurs whenever an order is updated.

## Order Deleted

Event Name: `order.deleted`

```json
{
    "event": "order.deleted",
    "order_id": "172dfbff-ebd9-4c9c-868c-cb79ef7775ed",
    "timestamp": "2018-01-01T00:00:00Z"
}
```

Occurs whenever an order is deleted.

## Order Status Updated

Event Name: `order.status_updated`

```json
{
    "event": "order.status_updated",
    "previous_status": "booked",
    "current_status": "dispatched",
    "order_id": "172dfbff-ebd9-4c9c-868c-cb79ef7775ed",
    "timestamp": "2018-01-01T00:00:00Z"
}
```

Occurs whenever an order status changed.

## Order Dispatched

Event Name: `order.dispatched`

```json
{
    "event": "order.dispatched",
    "order_id": "172dfbff-ebd9-4c9c-868c-cb79ef7775ed",
    "timestamp": "2018-01-01T00:00:00Z"
}
```

Occurs whenever an order is dispatched.

## Order Dispatched

Event Name: `order.dispatched`

```json
{
    "event": "order.dispatched",
    "order_id": "172dfbff-ebd9-4c9c-868c-cb79ef7775ed",
    "timestamp": "2018-01-01T00:00:00Z"
}
```

Occurs whenever an order is dispatched.

## Order Delivered

Event Name: `order.delivered`

```json
{
    "event": "order.delivered",
    "order_id": "172dfbff-ebd9-4c9c-868c-cb79ef7775ed",
    "timestamp": "2018-01-01T00:00:00Z"
}
```

Occurs whenever an order is delivered.

## Order In Transit

Event Name: `order.in_transit`

```json
{
    "event": "order.delivered",
    "order_id": "172dfbff-ebd9-4c9c-868c-cb79ef7775ed",
    "timestamp": "2018-01-01T00:00:00Z"
}
```

Occurs whenever an order's status changes to in-transit.

## Leg Created

Event Name: `leg.created`

```json
{
    "event": "leg.created",
    "leg_id": "dba74129-806a-4bec-b7d2-81a8e0e1ad35",
    "timestamp": "2018-06-08T13:51:14.649392Z"
}
```

Occurs whenever a leg is created.

## Leg Deleted

Event Name: `leg.deleted`

```json
{
    "event": "leg.deleted",
    "leg_id": "dba74129-806a-4bec-b7d2-81a8e0e1ad35",
    "timestamp": "2018-06-08T13:51:14.649392Z"
}
```

Occurs whenever a leg is deleted.

## Leg Dispatched

Event Name: `leg.dispatched`

```json
{
    "event": "leg.dispatched",
    "leg_id": "dba74129-806a-4bec-b7d2-81a8e0e1ad35",
    "timestamp": "2018-06-08T13:51:14.649392Z"
}
```

Occurs whenever a leg is dispatched.

## Leg Loaded

Event Name: `leg.loaded`

```json
{
    "event": "leg.loaded",
    "leg_id": "dba74129-806a-4bec-b7d2-81a8e0e1ad35",
    "timestamp": "2018-06-08T13:51:14.649392Z"
}
```

Occurs whenever a leg is loaded.

## Leg Unloaded

Event Name: `leg.unloaded`

```json
{
    "event": "leg.unloaded",
    "leg_id": "dba74129-806a-4bec-b7d2-81a8e0e1ad35",
    "timestamp": "2018-06-08T13:51:14.649392Z"
}
```

Occurs whenever a leg is unloaded.

## Manifest Completed

Event Name: `manifest.completed`

```json
{
    "event": "manifest.completed",
    "manifest_id": "dba74129-806a-4bec-b7d2-81a8e0e1ad35",
    "timestamp": "2018-06-08T13:51:14.649392Z"
}
```

Occurs whenever a manifest completed.

## Manifest Assigned

Event Name: `manifest.assigned`

```json
{
    "event": "manifest.assigned",
    "manifest_id": "dba74129-806a-4bec-b7d2-81a8e0e1ad35",
    "timestamp": "2018-06-08T13:51:14.649392Z"
}
```

Occurs whenever a manifest is assigned.
