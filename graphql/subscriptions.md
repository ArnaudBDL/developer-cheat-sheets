# GraphQL : Subscriptions

```graphql
subscription OnOrderStatusChanged($orderId: ID!) {
  orderStatusChanged(orderId: $orderId) {
    id
    status
    updatedAt
  }
}
```

```text
Connect
Authenticate
Subscribe
Authorize the requested stream
Publish matching events
Deliver payloads
Handle reconnect and cleanup
```

Define transport, authentication refresh, authorization, reconnect, ordering and delivery behavior explicitly. Remove inactive subscriptions and bound fan-out costs.
