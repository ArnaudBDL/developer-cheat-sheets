# Copilot Studio : Agent Flows

## Purpose

```text
Flows automate repeatable processes and integrate applications and services.
They can run independently or be exposed to an agent as a tool and return results.
```

## Flow Design

```text
Trigger
Validated inputs
Business steps
Connections
Conditions
Human review where needed
Structured outputs
Failure handling
Monitoring
```

Make flows idempotent when retries are possible. Keep connection references portable, avoid returning excessive data to the agent, and define timeouts and long-running behavior so the conversation can report progress or failure accurately.
