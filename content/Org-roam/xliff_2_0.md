---
publish: true
title: XLIFF 2.0
created: 2020-11-09T14:29:07
modified: 2026-08-05T07:58:56.722Z
---

# XLIFF 2.0

# Introduction

From \[Symfony 4.0]\(Symfony 4.0) XLIFF support has been added.

# Syntax

<?xml version="1.0" encoding="utf-8"?>

<xliff xmlns="urn:oasis:names:tc:xliff:document:2.0" version="2.0"
    srcLang="fr-FR" trgLang="en-US"> <file id="messages.en_US"> <unit id="LCa0a2j"> <notes> <note category="state">new</note> <note category="approved">true</note> <note category="section" priority="1">user login</note> </notes> <segment> <source>original-content</source> <target>translated-content</target> </segment> </unit> </file> </xliff>

$catalogue = new MessageCatalogue('en_US');
$catalogue->add(\[
'original-content' => 'translated-content',
]);
\$catalogue->setMetadata('original-content', \['notes' => \[
\['category' => 'state', 'content' => 'new'],
\['category' => 'approved', 'content' => 'true'],
\['category' => 'section', 'content' => 'user login', 'priority' => '1'],
]]);

$dumper = new XliffFileDumper();
$dumper->formatCatalogue(\$catalogue, 'messages', \[
'default\_locale' => 'fr\_FR',
'xliff\_version' => '2.0'
]);
