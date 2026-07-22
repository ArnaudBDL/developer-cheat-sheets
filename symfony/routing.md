# Symfony : Routing

## Attribute Route

```php
use Symfony\Component\HttpFoundation\Response;
use Symfony\Component\Routing\Attribute\Route;

#[Route('/articles/{id}', name: 'article_show', methods: ['GET'])]
public function show(int $id): Response
{
    return new Response((string) $id);
}
```

## Route Requirements

```php
#[Route(
    '/articles/{page}',
    name: 'article_list',
    requirements: ['page' => '\d+'],
    defaults: ['page' => 1],
)]
```

## Generate URLs

```php
$url = $this->generateUrl('article_show', ['id' => 42]);
return $this->redirectToRoute('article_show', ['id' => 42]);
```

## Inspect Routes

```bash
php bin/console debug:router
php bin/console debug:router article_show
php bin/console router:match /articles/42
php bin/console lint:yaml config/routes/
```
