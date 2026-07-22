# GitHub Actions : Reusable Workflows

## Called Workflow

```yaml
name: Reusable deployment

on:
  workflow_call:
    inputs:
      environment:
        required: true
        type: string
    secrets:
      deployment-token:
        required: true

jobs:
  deploy:
    runs-on: ubuntu-latest
    environment: ${{ inputs.environment }}
    steps:
      - env:
          TOKEN: ${{ secrets.deployment-token }}
        run: ./deploy.sh
```

## Caller Workflow

```yaml
jobs:
  deploy:
    uses: ./.github/workflows/reusable-deploy.yml
    with:
      environment: production
    secrets:
      deployment-token: ${{ secrets.DEPLOYMENT_TOKEN }}
```

## Cross-Repository Call

```yaml
jobs:
  deploy:
    uses: organization/automation/.github/workflows/deploy.yml@v1
    with:
      environment: production
    secrets: inherit
```

## Workflow Outputs

```yaml
on:
  workflow_call:
    outputs:
      version:
        value: ${{ jobs.build.outputs.version }}
```

Pin reusable workflows to a controlled tag or commit SHA according to the organization’s trust requirements.
