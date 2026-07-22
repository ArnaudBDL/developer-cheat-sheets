# Symfony : Deployment

## Production Environment

```dotenv
APP_ENV=prod
APP_DEBUG=0
```

Keep production secrets in environment variables or a dedicated secrets system, not in committed `.env` files.

## Install Dependencies

```bash
composer install \
  --no-dev \
  --prefer-dist \
  --no-interaction \
  --optimize-autoloader
```

## Database and Cache

```bash
APP_ENV=prod APP_DEBUG=0 php bin/console doctrine:migrations:migrate --no-interaction
APP_ENV=prod APP_DEBUG=0 php bin/console cache:clear
APP_ENV=prod APP_DEBUG=0 php bin/console cache:warmup
```

## Assets and Validation

```bash
php bin/console lint:container
php bin/console lint:yaml config/
php bin/console lint:twig templates/
php bin/console doctrine:schema:validate
php bin/phpunit
```

## Operations

```bash
php bin/console messenger:stop-workers
sudo systemctl reload php-fpm
sudo systemctl restart application-workers
```

## Deployment Checklist

- Point the web server document root to `public/`.
- Ensure `var/cache/` and `var/log/` are writable by the runtime user.
- Run migrations once per release under controlled locking.
- Restart long-running workers after releasing new code.
- Enable OPcache and production error logging.
- Verify health endpoints after deployment.
