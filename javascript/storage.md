# JavaScript : Storage

## localStorage

```javascript
localStorage.setItem('theme', 'dark');
const theme = localStorage.getItem('theme');
localStorage.removeItem('theme');
localStorage.clear();
```

## Store Structured Data

```javascript
const preferences = { theme: 'dark', compact: true };
localStorage.setItem('preferences', JSON.stringify(preferences));

const stored = localStorage.getItem('preferences');
const restored = stored ? JSON.parse(stored) : {};
```

## sessionStorage

```javascript
sessionStorage.setItem('current-step', '2');
const currentStep = sessionStorage.getItem('current-step');
```

## Storage Event

```javascript
window.addEventListener('storage', event => {
  console.log(event.key, event.oldValue, event.newValue);
});
```

## Security Rules

- Do not store passwords, access tokens or other sensitive secrets in web storage.
- Treat stored values as untrusted input when reading them back.
- Handle missing values and malformed JSON.
- Clear application-owned data during logout when appropriate.
