# REST : Principles

## Architectural Constraints

```text
Client-Server
Stateless
Cacheable
Uniform Interface
Layered System
Code on Demand, optional
```

## Uniform Interface

```text
Resources are identified by URIs.
Resources are manipulated through representations.
Messages are self-descriptive.
Hypermedia can guide application state.
```

## Rules

- Model business concepts as resources rather than remote procedure names.
- Keep each request self-contained.
- Use HTTP semantics consistently.
- Expose cache behavior explicitly.
- Separate client concerns from server implementation.
- Design representations and transitions for evolution.
- Treat REST as an architectural style, not merely JSON transported over HTTP.
