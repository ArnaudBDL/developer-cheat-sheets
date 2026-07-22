# Power BI : Workspaces

## Workspace Roles

```text
Admin
Member
Contributor
Viewer
```

## Workspace Design

```text
Ownership and support contact
Development lifecycle stage
Audience and sensitivity
Capacity assignment
Naming and retention
App distribution
Source-control and deployment process
```

## Rules

- Grant the least privileged workspace role.
- Use Viewer for consumers who should remain subject to RLS.
- Separate development, test and production when lifecycle control requires it.
- Avoid using workspace membership as a substitute for model-level design.
- Review owners and inactive content.
- Document who can publish, certify, share and administer gateway connections.
