# Microservices : Principles

## Core Principles

```text
Organize services around business capabilities.
Keep services independently deployable.
Hide implementation details behind explicit contracts.
Give teams clear ownership from development through operations.
Automate build, test, deployment and recovery.
Design explicitly for network and dependency failures.
Own data within a defined service boundary.
```

## Decision Checklist

```text
Business capability
Independent lifecycle
Data ownership
Interface stability
Operational ownership
Scaling requirement
Failure isolation
Compliance boundary
```

Microservices add distributed-system and operational complexity. Use them when independent evolution, ownership or scaling solves a concrete problem.
