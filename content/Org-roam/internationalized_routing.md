---
publish: true
title: Internationalized Routing
created: 2020-11-10T15:45:48
modified: 2026-08-05T07:58:56.686Z
---

# Internationalized Routing

# Introduction

Since \[Symfony 4.1]\(Symfony 4.1) support for internationalized routes was added.

# Syntax

contact:
controller: App\Controller\ContactController::send
path:
en: /send-us-an-email
nl: /stuur-ons-een-email

use Symfony\Component\Routing\Annotation\Route;

class ContactController
{
/\*\*
\* @Route({
\*     "en": "/send-us-an-email",
\*     "nl": "/stuur-ons-een-email"
\* }, name="contact")
\*/
public function send()
{
// ...
}
}

/\*\* @var UrlGeneratorInterface $urlGenerator */
// uses the current request locale
$url = \$urlGenerator->generate('contact');

// ignores the current request locale and generates '/stuur-ons-een-email'
$url = $urlGenerator->generate('contact', \['\_locale' => 'nl']);
// this would also work, but it's not recommended:
// $url = $urlGenerator->generate('contact.nl');

# config/routes/annotations.yaml

site:
resource: '../src/Controller/'
type: annotation
prefix:
en: '/site'
es: '/sitio'

class DefaultController extends Controller
{
/\*\*
\* @Route({"en": "/contact", "es": "/contacto"}, name="contact")
\*/
public function contact()
{
// ...
}

```
/**
 * @Route("/page/{slug}", name="page")
 */
public function page($slug)
{
    // ...
}
```

}
