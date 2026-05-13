# amalgame-logging

Pure-Amalgame logging facade for [Amalgame](https://github.com/amalgame-lang/Amalgame).
Four levels (**Debug** / **Info** / **Warn** / **Error**) emitted to
stderr with a UTC ISO 8601 timestamp + fixed-width label, plus an
optional file sink.

Originally bundled in amc's `src/stdlib/logging.am`; extracted into
this external package as part of the framework split (post-v0.7.5).

## Install

```bash
amc package add logging                  # via the curated index
amc package add github.com/amalgame-lang/amalgame-logging@v0.1.0
```

Requires **amc 0.7.7+** for the facade pre-compile + cross-class
forward decl fix.

## Surface

```amalgame
import Amalgame.Logging

class Program {
    public static void Main() {
        Log.SetMinLevel("info")        // "debug" | "info" | "warn" | "error"
        Log.SetFile("/tmp/app.log")    // optional file sink (append)

        Log.Debug("won't print at info level")
        Log.Info("starting")
        Log.Warn("watch out")
        Log.Error("boom")

        Log.SetFile("")                // unset the file sink
    }
}
```

Each line is formatted as `<ISO8601-UTC> [LEVEL] message` and goes
to **stderr** (plus the file sink if set). Level names are
case-insensitive on the first letter — `"DEBUG"`, `"debug"`,
`"Debug"` all map to the same code.

## Tests

```bash
./tests/run_tests.sh /path/to/amc
```

## License

Apache-2.0 — see `LICENSE`. No vendored third-party code.
