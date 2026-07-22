# Model Context Protocol : Sampling

## Concept

```text
An MCP server can ask the connected client to obtain a model-generated message.
The client retains control over model access and user approval policy.
```

## Flow

```text
Server prepares a sampling request
Client validates capability and policy
Client may request user approval
Client selects and invokes an available model
Client returns the generated result
Server continues its workflow
```

## Controls

- Bound token, latency and cost budgets.
- Preserve user visibility into what context is sent.
- Do not send credentials or hidden server secrets to the model.
- Treat sampled output as untrusted until validated.
- Prevent recursive or unbounded sampling loops.
- Log sampling purpose, outcome and correlation data without sensitive content.
- Deny sampling when the client has not negotiated or permitted it.
