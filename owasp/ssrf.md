# OWASP : SSRF

In OWASP Top 10:2025, Server-Side Request Forgery is included in Broken Access Control. This dedicated sheet remains useful for implementation and review.

## Risky Features

```text
URL preview
Webhook delivery
Remote import
Image or document fetch
Proxy endpoints
Cloud metadata access
Callback validation
```

## Controls

- Avoid accepting arbitrary destinations when a fixed integration is possible.
- Allowlist schemes, hosts and ports for known integrations.
- Resolve and validate destinations before connection.
- Block loopback, link-local, private, reserved and metadata addresses unless explicitly required.
- Revalidate every redirect target or disable redirects.
- Restrict outbound network access at the infrastructure layer.
- Use dedicated egress proxies and DNS controls for sensitive workloads.
- Apply timeouts, response-size limits and content-type validation.
- Do not return raw upstream responses or network errors to clients.

## Review Checklist

```text
URL parsing
DNS resolution
Redirects
IPv4 and IPv6
Alternative address representations
Internal hostnames
Cloud metadata endpoints
Outbound firewall rules
Timeouts and size limits
Response handling
```
