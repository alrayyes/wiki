---
publish: true
title: Symfony UUID Component
created: 2020-11-16T13:18:15
modified: 2026-08-05T10:26:50.518Z
---

# Symfony UUID Component

# Description

Generate UUIDS\[fn:uuids] and ULIDS\[fn:ulids]

# Syntax

use Symfony\Component\Uid\Uuid;
use Symfony\Component\Uid\Ulid;

// generating a random UUID type 4 (all UUID types are supported)
\$uuid = Uuid::v4();

// generating a UUID Type 6 (which is not part of the standard, but it's
// supported by the component because it's popular enough)
\$uuid = Uuid::v6();

// generating a ULID (there's only one type of them)
\$ulid = new Ulid();

// checking if some UUID is null
use Symfony\Component\Uid\NilUuid;
if (\$uuid instanceof NilUuid) {
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
\$ulid->toRfc4122(); // string(36) "0171069d-593d-97d3-8b3e-23d06de5b308"

# Normalization

- \[UUID Normalizer]\(UUID Normalizer)

# Footnotes

\[fn:ulids]https://github.com/ulid/spec
\[fn:uuids]https://en.wikipedia.org/wiki/Universally\_unique\_identifier
