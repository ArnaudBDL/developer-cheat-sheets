# Symfony : Controllers

## Controller

```php
namespace App\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\AbstractController;
use Symfony\Component\HttpFoundation\JsonResponse;
use Symfony\Component\Routing\Attribute\Route;

final class HealthController extends AbstractController
{
    #[Route('/health', name: 'health', methods: ['GET'])]
    public function __invoke(): JsonResponse
    {
        return $this->json(['status' => 'ok']);
    }
}
```

## Request and Response

```php
use Symfony\Component\HttpFoundation\Request;
use Symfony\Component\HttpFoundation\Response;

public function index(Request $request): Response
{
    $query = $request->query->getString('query');

    return $this->render('search/index.html.twig', ['query' => $query]);
}
```

## Common Responses

```php
return $this->json($data);
return $this->redirectToRoute('home');
return $this->file($path);
throw $this->createNotFoundException();
```
