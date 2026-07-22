# PHP : Security

## Input Validation

```php
$email = filter_input(INPUT_POST, 'email', FILTER_VALIDATE_EMAIL);
if ($email === false || $email === null) {
    throw new InvalidArgumentException('Invalid email');
}
```

## Output Escaping

```php
echo htmlspecialchars($value, ENT_QUOTES | ENT_SUBSTITUTE, 'UTF-8');
```

Escape output for its destination context, such as HTML, attributes, JavaScript, URLs or SQL.

## Prepared Statements

```php
$statement = $pdo->prepare('SELECT * FROM users WHERE email = :email');
$statement->execute(['email' => $email]);
$user = $statement->fetch(PDO::FETCH_ASSOC);
```

## Passwords

```php
$hash = password_hash($password, PASSWORD_DEFAULT);
$valid = password_verify($password, $hash);

if (password_needs_rehash($hash, PASSWORD_DEFAULT)) {
    $hash = password_hash($password, PASSWORD_DEFAULT);
}
```

## Sessions and Cookies

```php
session_set_cookie_params([
    'secure' => true,
    'httponly' => true,
    'samesite' => 'Lax',
]);
session_start();
session_regenerate_id(true);
```

## Operational Checklist

- Keep PHP, extensions and dependencies updated.
- Run `composer audit` and review dependency changes.
- Keep secrets outside source control and the document root.
- Disable detailed error display in production and log errors securely.
- Validate uploaded files by size, content and destination.
- Use CSRF tokens for state-changing browser requests.
- Restrict filesystem permissions and executable functions according to the runtime context.
