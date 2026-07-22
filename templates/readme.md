# README Template

Use this template to create the root `README.md` of a software project.

## Template

```markdown
# {{PROJECT_NAME}}

{{PROJECT_DESCRIPTION}}

## Status

{{PROJECT_STATUS}}

## Features

- {{FEATURE_1}}
- {{FEATURE_2}}
- {{FEATURE_3}}

## Requirements

- {{REQUIREMENT_1}}
- {{REQUIREMENT_2}}
- {{REQUIREMENT_3}}

## Installation

```bash
{{INSTALL_COMMANDS}}
```

## Configuration

Copy the example environment file and update the required values:

```bash
cp .env.example .env
```

| Variable | Required | Default | Description |
|---|---:|---|---|
| `{{VARIABLE_NAME}}` | Yes | None | {{VARIABLE_DESCRIPTION}} |

Never commit credentials, tokens, private keys, or production secrets.

## Usage

```bash
{{RUN_COMMANDS}}
```

## Development

```bash
{{DEVELOPMENT_COMMANDS}}
```

## Testing

```bash
{{TEST_COMMANDS}}
```

## Quality Checks

```bash
{{QUALITY_COMMANDS}}
```

## Build

```bash
{{BUILD_COMMANDS}}
```

## Docker

Start the development environment:

```bash
docker compose up --build
```

Stop the environment:

```bash
docker compose down
```

Remove containers and project volumes:

```bash
docker compose down --volumes
```

## Project Structure

```text
{{PROJECT_STRUCTURE}}
```

## Architecture

{{ARCHITECTURE_DESCRIPTION}}

## Documentation

- [Architecture](docs/architecture.md)
- [Development](docs/development.md)
- [Deployment](docs/deployment.md)

Remove links to documents that do not exist.

## Deployment

{{DEPLOYMENT_DESCRIPTION}}

## Security

Report security issues through {{SECURITY_CONTACT_OR_PROCESS}}.

Do not disclose unresolved vulnerabilities in public issues.

## Contributing

1. Create a branch from the default branch.
2. Implement one focused change.
3. Add or update tests and documentation.
4. Run the complete validation workflow.
5. Open a pull request with a clear description.

## License

{{LICENSE_NAME}}. See [LICENSE](LICENSE).
```

## Required Replacements

```text
{{PROJECT_NAME}}
{{PROJECT_DESCRIPTION}}
{{PROJECT_STATUS}}
{{FEATURE_1}}
{{FEATURE_2}}
{{FEATURE_3}}
{{REQUIREMENT_1}}
{{REQUIREMENT_2}}
{{REQUIREMENT_3}}
{{INSTALL_COMMANDS}}
{{VARIABLE_NAME}}
{{VARIABLE_DESCRIPTION}}
{{RUN_COMMANDS}}
{{DEVELOPMENT_COMMANDS}}
{{TEST_COMMANDS}}
{{QUALITY_COMMANDS}}
{{BUILD_COMMANDS}}
{{PROJECT_STRUCTURE}}
{{ARCHITECTURE_DESCRIPTION}}
{{DEPLOYMENT_DESCRIPTION}}
{{SECURITY_CONTACT_OR_PROCESS}}
{{LICENSE_NAME}}
```

## Rules

- Remove unused sections instead of leaving empty headings.
- Do not keep unresolved placeholders in the generated `README.md`.
- Keep commands directly executable from the repository root.
- Document the supported runtime and tool versions.
- Keep installation, development, testing, and deployment instructions distinct.
- Do not include secrets or real credentials in examples.
- Update the README whenever commands, environment variables, or project structure change.
