---
publish: true
title: tempnam()
created: 2020-11-16T14:21:05
modified: 2026-08-05T07:58:56.716Z
---

# tempnam()

# Description

Like the PHP ~tempnam()~ function this method creates a file with a unique name in the given directory.

# Syntax

use Symfony\Component\Filesystem\Filesystem;

\$fs = new Filesystem();

$fs->tempnam('/tmp', 'report_');         // '/tmp/report_Um3nlH'
$fs->tempnam('/tmp', 'report\_', '.pdf'); // '/tmp/report\_Um3nlH.pdf'
