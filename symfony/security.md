# Symfony : Security

## Security Configuration

```yaml
security:
  password_hashers:
    Symfony\Component\Security\Core\User\PasswordAuthenticatedUserInterface: auto

  providers:
    app_user_provider:
      entity:
        class: App\Entity\User
        property: email

  firewalls:
    dev:
      pattern: ^/(_(profiler|wdt)|css|images|js)/
      security: false
    main:
      lazy: true
      provider: app_user_provider
      form_login:
        login_path: app_login
        check_path: app_login
      logout:
        path: app_logout

  access_control:
    - { path: ^/admin, roles: ROLE_ADMIN }
```

## Authorization

```php
$this->denyAccessUnlessGranted('ROLE_ADMIN');
$this->denyAccessUnlessGranted('edit', $article);
```

## CSRF

```twig
<input type="hidden" name="_token" value="{{ csrf_token('delete' ~ article.id) }}">
```

## Inspect

```bash
php bin/console debug:firewall
php bin/console security:hash-password
symfony check:security
```
