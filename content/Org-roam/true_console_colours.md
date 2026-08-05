---
publish: true
title: True Console Colours
created: 2020-11-17T10:08:55
modified: 2026-08-05T10:26:50.519Z
---

# True Console Colours

# Description

The console supports 24-bit colours.

# Syntax

// using a predefined style
\$output->writeln('<info>... contents ...\</>');

// custom style using basic colors
\$output->writeln('\<fg=green;bg=blue>... contents ...\</>');

// custom style using true colors
\$output->writeln('\<fg=#00ff00;bg=#00f>... contents ...\</>');

use Symfony\Component\Console\Color;

$color = new Color('#00ff00', '#00f');
echo $color->apply('... contents ...');

// you can mix basic and true colors
\$color = new Color('red', '#00f');

// the third optional argument defines the styles
\$color = new Color('#000', '#fff', \['underscore', 'reverse']);
