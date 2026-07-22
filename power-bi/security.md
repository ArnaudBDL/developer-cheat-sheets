# Power BI : Security

## Security Layers

```text
Tenant settings
Capacity and workspace access
Item permissions
Semantic-model permissions
Row-level security
Object-level security
Source-system security
Gateway credentials
Sensitivity labels and data loss prevention controls
Auditing and monitoring
```

## RLS Workflow

```text
Define roles and DAX filters
Test roles in Desktop
Publish the semantic model
Assign users or groups to roles in the service
Use Test as role
Verify workspace roles do not bypass intended restrictions
```

RLS filters rows for model consumers, but it does not replace workspace governance or source authorization. According to Microsoft guidance, RLS applies to workspace Viewers, not Admins, Members or Contributors. Minimize sharing paths and test every audience.
