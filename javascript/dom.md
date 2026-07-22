# JavaScript : DOM

## Select Elements

```javascript
const application = document.querySelector('#application');
const buttons = document.querySelectorAll('[data-action]');
const form = document.getElementById('contact-form');
```

## Create and Insert

```javascript
const item = document.createElement('li');
item.textContent = 'New item';
item.classList.add('item');

list.append(item);
container.prepend(item);
reference.before(item);
```

## Attributes and Classes

```javascript
element.setAttribute('aria-expanded', 'true');
element.removeAttribute('hidden');
element.classList.toggle('active');
element.dataset.identifier = '42';
```

## Content

```javascript
element.textContent = 'Safe text';
const value = input.value;
```

Prefer `textContent` for untrusted text. Assigning untrusted content to `innerHTML` can create injection vulnerabilities.

## Remove and Replace

```javascript
element.remove();
oldElement.replaceWith(newElement);
container.replaceChildren(...children);
```
