# Microservices : Service Boundaries

## Boundary Signals

```text
Business capability
Domain subdomain
Bounded context
Independent language and rules
Distinct data ownership
Separate scaling profile
Separate security or compliance boundary
Independent release cadence
```

## Good Boundary

```text
Orders Service
  Owns order lifecycle and order data
  Exposes order commands, queries and events
  Does not expose its database tables
```

## Warning Signs

- Services must be deployed together.
- One request requires a long chain of synchronous calls.
- Multiple services write directly to the same tables.
- Business rules are duplicated across services.
- Boundaries follow technical layers rather than domain capabilities.
- A change routinely modifies many service contracts.

Start with domain boundaries, then validate them against ownership, data, transactions and operational behavior.
