# Symfony : Forms

## Form Type

```php
namespace App\Form;

use App\Entity\Article;
use Symfony\Component\Form\AbstractType;
use Symfony\Component\Form\Extension\Core\Type\SubmitType;
use Symfony\Component\Form\FormBuilderInterface;
use Symfony\Component\OptionsResolver\OptionsResolver;

final class ArticleType extends AbstractType
{
    public function buildForm(FormBuilderInterface $builder, array $options): void
    {
        $builder
            ->add('title')
            ->add('content')
            ->add('save', SubmitType::class);
    }

    public function configureOptions(OptionsResolver $resolver): void
    {
        $resolver->setDefaults(['data_class' => Article::class]);
    }
}
```

## Handle Submission

```php
$form = $this->createForm(ArticleType::class, $article);
$form->handleRequest($request);

if ($form->isSubmitted() && $form->isValid()) {
    $entityManager->persist($article);
    $entityManager->flush();

    return $this->redirectToRoute('article_show', ['id' => $article->getId()]);
}

return $this->render('article/form.html.twig', ['form' => $form]);
```

## Twig

```twig
{{ form_start(form) }}
{{ form_widget(form) }}
{{ form_end(form) }}
```
