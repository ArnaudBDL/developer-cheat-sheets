# Gitignore Template

Use this template to create a root `.gitignore` file. Remove sections that do not apply to the project.

## Template

```gitignore
# Operating systems
.DS_Store
.AppleDouble
.LSOverride
Thumbs.db
Desktop.ini
$RECYCLE.BIN/

# Editors and IDEs
.idea/
.vscode/*
!.vscode/extensions.json
!.vscode/settings.json
!.vscode/tasks.json
!.vscode/launch.json
*.swp
*.swo
*~

# Environment and secrets
.env
.env.*
!.env.example
*.pem
*.key
*.p12
*.pfx
secrets/

# Logs and runtime files
*.log
logs/
*.pid
*.pid.lock
*.seed

# Temporary files
.tmp/
tmp/
temp/
.cache/

# Build and distribution
build/
dist/
out/
artifacts/
coverage/

# Dependencies
node_modules/
vendor/

# JavaScript and TypeScript
.npm/
.pnpm-store/
.yarn/cache/
.yarn/install-state.gz
*.tsbuildinfo

# Python
__pycache__/
*.py[cod]
*.pyd
.pytest_cache/
.mypy_cache/
.ruff_cache/
.venv/
venv/

# Java
*.class
.gradle/
target/

# .NET
bin/
obj/
TestResults/
*.user
*.suo

# Go
*.test
*.out
coverage.out

# PHP and Symfony
.phpunit.result.cache
.phpunit.cache/
var/cache/
var/log/

# Docker local overrides
docker-compose.override.yml
compose.override.yaml

# Databases and local data
*.sqlite
*.sqlite3
*.db
*.db-journal
*.db-shm
*.db-wal
data/

# Terraform
.terraform/
*.tfstate
*.tfstate.*
crash.log
crash.*.log
*.tfvars
*.tfvars.json
!*.tfvars.example
.terraformrc
terraform.rc

# Generated documentation
site/

# Project-specific generated files
{{PROJECT_SPECIFIC_IGNORES}}
```

## Required Replacement

```text
{{PROJECT_SPECIFIC_IGNORES}}
```

Replace the placeholder with project-specific patterns or remove the final section.

## Rules

- Ignore generated, reproducible, local, confidential, and machine-specific files.
- Do not ignore source code, migrations, lock files, or required project configuration.
- Keep dependency lock files committed unless the ecosystem convention explicitly requires otherwise.
- Keep `.env.example` committed and ensure it contains no real secrets.
- Review broad patterns such as `data/`, `build/`, `dist/`, and `vendor/` before retaining them.
- Do not rely on `.gitignore` to remove files already tracked by Git.
- To stop tracking an ignored file while preserving the local copy, use `git rm --cached <path>`.
- Validate changes with `git status --ignored` and `git check-ignore -v <path>`.
