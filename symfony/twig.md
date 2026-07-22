# Symfony : Twig

## Render a Template

```php
return $this->render('article/show.html.twig', [
    'article' => $article,
]);
```

## Template

```twig
{% extends 'base.html.twig' %}

{% block title %}{{ article.title }}{% endblock %}

{% block body %}
  <h1>{{ article.title }}</h1>

  {% if article.published %}
    <p>{{ article.content|nl2br }}</p>
  {% endif %}
{% endblock %}
```

## URLs and Assets

```twig
<a href="{{ path('article_show', {id: article.id}) }}">Open</a>
<img src="{{ asset('images/logo.svg') }}" alt="Logo">
```

## Validate and Debug

```bash
php bin/console lint:twig templates/
php bin/console debug:twig
```
