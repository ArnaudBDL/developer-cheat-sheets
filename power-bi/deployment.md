# Power BI : Deployment

## Lifecycle

```text
Develop
Validate
Test
Approve
Deploy
Configure environment-specific connections
Refresh and smoke test
Publish or update the app
Monitor
Rollback if required
```

## Production Checklist

```text
Connection strings and parameters
Gateway and drivers
Credentials
Scheduled refresh
Workspace roles
RLS role membership
Sensitivity labels
Owners and contacts
App audience
Rollback artifacts
```

Deployment pipelines can promote supported content across development, test and production stages. Keep previous deliverables recoverable, validate environment bindings after deployment, and separate deployment approval from content authorship where governance requires it.
