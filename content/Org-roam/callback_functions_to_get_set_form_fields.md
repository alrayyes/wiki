---
publish: true
title: Callback Functions To Get/Set Form Fields
created: 2020-11-17T10:35:06
modified: 2026-08-05T07:58:56.673Z
---

# Callback Functions To Get/Set Form Fields

# Description

Use callback functions to get/set form fields. Data mapper is no longer needed when getter/setter methods don't directly correlate to property names.

# Syntax

// src/Form/Type/ProductType.php
namespace App\Form\Type;

use App\Entity\Person;
use Symfony\Component\Form\Extension\Core\Type\TextType;
use Symfony\Component\Form\FormBuilderInterface;
use Symfony\Component\Form\FormInterface;

class PersonType extends AbstractType
{
public function buildForm(FormBuilderInterface $builder, array $options)
{
$builder
            ->add('name', TextType::class, [
                'getter' => function (Person $person, FormInterface $form): string {
                    return $person->getUserData()->getFirstName();
},
'setter' => function (Person &$person, ?string $name, FormInterface $form): void {
                    $person->rename(\$name);
},
])

```
        // ...
    ;
}

// ...
```

}
