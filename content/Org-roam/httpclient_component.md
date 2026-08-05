---
publish: true
title: HttpClient Component
created: 2020-11-12T14:04:48
modified: 2026-08-05T07:58:56.685Z
---

# HttpClient Component

# Syntax

use Symfony\Component\HttpClient\HttpClient;

$httpClient = HttpClient::create();
$response = \$httpClient->request('GET', 'https://api.github.com/repos/symfony/symfony-docs');

$statusCode = $response->getStatusCode();
// $statusCode = 200
$content = $response->getContent();
// returns the raw content returned by the server (JSON in this case)
// $content = '{"id":521583, "name":"symfony-docs", ...}'
$content = $response->toArray();
// transforms the response JSON content into a PHP array
// \$content = \['id' => 521583, 'name' => 'symfony-docs', ...]

// the response of this request will be a 403 HTTP error
$response = $httpClient->request('GET', 'https://httpbin.org/status/403');

// this code results in a Symfony\Component\HttpClient\Exception\ClientException
// because it doesn't check the status code of the response
$content = $response->getContent();

// do this instead
if (200 !== $response->getStatusCode()) {
    // handle the HTTP request error (e.g. retry the request)
} else {
    $content = \$response->getContent();
}
