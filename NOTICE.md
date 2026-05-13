# NOTICE — amalgame-logging

## Authorship

Copyright 2026 Bastien Mouget. The Amalgame facade code in this
repository is original work — see `facade.am` and the
`amalgame.toml` manifest.

This package is part of the Amalgame ecosystem
([github.com/amalgame-lang/Amalgame](https://github.com/amalgame-lang/Amalgame)).
It was extracted from amc's bundled `src/stdlib/logging.am`
during the framework split (post-v0.7.5).

## License

Licensed under the Apache License, Version 2.0 — see `LICENSE`.

## Third-party content

None. The facade is 100% pure-Amalgame. A top-level `@c { … }`
block holds process-wide state globals (min level, optional file
handle) and the libc `<stdio.h>` / `<time.h>` includes needed for
formatted stderr output and UTC timestamp formatting.
