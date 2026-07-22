# JavaScript : Events

## Listen and Remove

```javascript
function handleClick(event) {
  console.log(event.currentTarget);
}

button.addEventListener('click', handleClick);
button.removeEventListener('click', handleClick);
```

## Event Options

```javascript
element.addEventListener('click', handler, { once: true });
window.addEventListener('scroll', handler, { passive: true });
element.addEventListener('click', handler, { signal: controller.signal });
```

## Prevent and Stop

```javascript
form.addEventListener('submit', event => {
  event.preventDefault();
});

event.stopPropagation();
event.stopImmediatePropagation();
```

## Event Delegation

```javascript
list.addEventListener('click', event => {
  const button = event.target.closest('[data-action="delete"]');
  if (!button || !list.contains(button)) {
    return;
  }

  deleteItem(button.dataset.identifier);
});
```

## Custom Events

```javascript
const event = new CustomEvent('application:ready', {
  detail: { version: '1.0.0' },
});

document.dispatchEvent(event);
```
