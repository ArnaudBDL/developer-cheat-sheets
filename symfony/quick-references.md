# Symfony : Quick References

## Project

```bash
symfony new my-project --webapp
symfony serve -d
symfony server:stop
php bin/console about
```

## Console

```bash
php bin/console list
php bin/console debug:router
php bin/console debug:container
php bin/console cache:clear
php bin/console lint:container
```

## Doctrine

```bash
php bin/console doctrine:database:create
php bin/console make:entity
php bin/console make:migration
php bin/console doctrine:migrations:migrate
php bin/console doctrine:schema:validate
```

## Tests

```bash
php bin/phpunit
php bin/phpunit --testsuite unit
php bin/phpunit --filter TestName
```
