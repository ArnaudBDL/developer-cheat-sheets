# Copilot : Agents

## Agent Components

```text
Purpose and scope
Instructions
Knowledge sources
Tools and actions
Triggers
Authentication
Channels
Observability
Evaluation
Ownership and lifecycle
```

## Design Checklist

- Define a narrow goal and target users.
- Specify what the agent must not do.
- Minimize knowledge and tool access.
- Validate tool parameters and outputs.
- Require approval for consequential operations.
- Log actions and preserve attribution.
- Test expected, ambiguous and adversarial requests.
- Assign an owner, review date and retirement process.

## Agent Test Cases

```text
Expected task
Missing context
Conflicting sources
Unauthorized source
Unauthorized action
Prompt injection in retrieved content
Tool timeout or malformed result
Duplicate action request
Sensitive output request
Human escalation
```
