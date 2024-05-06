---
id: 1a128c92-4b0d-4a5a-88e8-fcd59eff2e8e
title: Symfony UUID Component
---

# Description

Generate UUIDS[^1] and ULIDS[^2]

# Syntax

``` php
use Symfony\Component\Uid\Uuid;
use Symfony\Component\Uid\Ulid;

// generating a random UUID type 4 (all UUID types are supported)
$uuid = Uuid::v4();

// generating a UUID Type 6 (which is not part of the standard, but it's
// supported by the component because it's popular enough)
$uuid = Uuid::v6();

// generating a ULID (there's only one type of them)
$ulid = new Ulid();
```

``` php
// checking if some UUID is null
use Symfony\Component\Uid\NilUuid;
if ($uuid instanceof NilUuid) {
    // ...
}

// comparing UUIDs
$uuid1 = Uuid::v1();
$uuid4 = Uuid::v4();
$uuid1->equals($uuid4); // false

// converting to different formats
$ulid = Ulid::fromString('01E439TP9XJZ9RPFH3T1PYBCR8');
$ulid->toBinary();  // string(16) "..." (binary contents can't be printed)
$ulid->toBase32();  // string(26) "01E439TP9XJZ9RPFH3T1PYBCR8"
$ulid->toBase58();  // string(22) "1BKocMc5BnrVcuq2ti4Eqm"
$ulid->toRfc4122(); // string(36) "0171069d-593d-97d3-8b3e-23d06de5b308"
```

# Normalization

-   [UUID Normalizer](20201117103957-uuid_normalizer)

# Footnotes

[^1]: <https://en.wikipedia.org/wiki/Universally_unique_identifier>

[^2]: <https://github.com/ulid/spec>
