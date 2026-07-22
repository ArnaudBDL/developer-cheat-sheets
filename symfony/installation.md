# Symfony : Installation

## Symfony CLI

```bash
symfony check:requirements
symfony new application --webapp
cd application
symfony server:start -d
symfony open:local
symfony server:stop
```

## Composer

```bash
composer create-project symfony/skeleton application
cd application
composer require webapp
```

## Verify

```bash
php bin/console about
php bin/console list
composer validate
composer check-platform-reqs
symfony check:security
```

## Environment

```dotenv
APP_ENV=dev
APP_SECRET=change-me
```

Use `.env.local` for local overrides that must not be committed.
