# Symfony : Validation

## Constraint Attributes

```php
use Symfony\Component\Validator\Constraints as Assert;

final class RegistrationData
{
    public function __construct(
        #[Assert\NotBlank]
        #[Assert\Email]
        public string $email = '',

        #[Assert\Length(min: 12)]
        public string $password = '',
    ) {
    }
}
```

## Validate Manually

```php
$violations = $validator->validate($data);

foreach ($violations as $violation) {
    printf('%s: %s%s', $violation->getPropertyPath(), $violation->getMessage(), PHP_EOL);
}
```

## Validation Groups

```php
#[Assert\NotBlank(groups: ['create'])]
public string $password = '';
```

## Inspect

```bash
php bin/console debug:validator App\Entity\User
```
