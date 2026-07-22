# Symfony : Doctrine

## Install and Configure

```bash
composer require symfony/orm-pack
composer require --dev symfony/maker-bundle
```

```dotenv
DATABASE_URL="postgresql://app:password@127.0.0.1:5432/app?serverVersion=17&charset=utf8"
```

## Entity

```php
use Doctrine\ORM\Mapping as ORM;

#[ORM\Entity]
final class Article
{
    #[ORM\Id]
    #[ORM\GeneratedValue]
    #[ORM\Column]
    private ?int $id = null;

    #[ORM\Column(length: 255)]
    private string $title;
}
```

## Database and Migrations

```bash
php bin/console doctrine:database:create
php bin/console make:entity
php bin/console make:migration
php bin/console doctrine:migrations:migrate
php bin/console doctrine:migrations:status
php bin/console doctrine:schema:validate
```

## Persist

```php
$entityManager->persist($article);
$entityManager->flush();
```

## Query

```php
$article = $repository->find($id);
$articles = $repository->findBy(['published' => true], ['createdAt' => 'DESC']);
```
