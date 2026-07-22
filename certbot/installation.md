# Certbot : Installation

## Prerequisites

```text
A registered domain name
DNS records pointing to the target server
Administrative access to the server
A reachable validation path for the selected ACME challenge
```

## Verify Installation

```bash
certbot --version
certbot --help
certbot plugins
```

## Installation Methods

```text
Snap package
Operating-system package
Docker
Python package in a controlled environment
Hosting-provider integration
```

Use the official Certbot instruction generator for the exact operating system and web server. Avoid the deprecated `certbot-auto` installer. After installation, verify that automatic renewal is configured by the selected package or deployment method.
