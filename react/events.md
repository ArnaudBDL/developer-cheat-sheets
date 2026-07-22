# React : Events

## Event Handlers

```tsx
function SaveButton() {
  function handleClick(event: React.MouseEvent<HTMLButtonElement>) {
    event.preventDefault()
    save()
  }

  return <button onClick={handleClick}>Save</button>
}
```

## Form and Input Events

```tsx
function handleSubmit(event: React.FormEvent<HTMLFormElement>) {
  event.preventDefault()
}

function handleChange(event: React.ChangeEvent<HTMLInputElement>) {
  setValue(event.target.value)
}
```

## Passing Arguments

```tsx
<button onClick={() => removeItem(item.id)}>Delete</button>
```

## Rule

```text
Pass a function to an event prop. Do not call the function while rendering unless the returned function itself is the handler.
```

