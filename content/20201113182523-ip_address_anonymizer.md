---
id: 8a367c4d-c104-41ff-953b-23d5d154028f
title: IP Address Anonymizer
---

# Description

Removes last byte for IPV4 addresses and last 8 bytes for IPV6

# Syntax

``` php
use Symfony\Component\HttpFoundation\IpUtils;

$ipv4 = '123.234.235.236';
$anonymousIpv4 = IPUtils::anonymize($ipv4);
// $anonymousIpv4 = '123.234.235.0'

$ipv6 = '2a01:198:603:10:396e:4789:8e99:890f';
$anonymousIpv6 = IPUtils::anonymize($ipv6);
// $anonymousIpv6 = '2a01:198:603:10::'
```
