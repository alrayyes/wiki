---
publish: true
title: Console Signals
created: 2020-11-17T11:49:30
modified: 2026-08-05T07:58:56.676Z
---

# Console Signals

# Description

Symfony supports console signals\[fn:signals].

# Syntax

// ...
use Symfony\Component\Console\Command\SignalableCommandInterface;

class SignalCommand extends Command implements SignalableCommandInterface
{
// ...

```
protected function execute(InputInterface $input, OutputInterface $output): int
{
    // ...
}

public function getSubscribedSignals(): array
{
    // return here any of the constants defined by PCNTL extension
    // https://www.php.net/manual/en/pcntl.constants.php
    return [SIGINT, SIGTERM];
}

public function handleSignal(int $signal)
{
    if (SIGINT === $signal) {
        // ...
    }

    // ...
}
```

}

# Footnotes

\[fn:signals]https://en.wikipedia.org/wiki/Signal\_(IPC)
