# Global options

This page describes what global options are available when using Surreal Docs CLI.

### Telemetry

#### `--no-tele` - disable telemetry

Disables telemetry until the current command finishes execution. When running the next common one still needs to provide the CLI with this parameter if they wish to continue work with disabled telemetry.

Example:

```
surdocs --no-tele generate out
```

When enabled, telemetry collects and sends us anonymized usage data what is governed by Surreal Docs EULA that can be found in the `LICENSE` file in the repository or by on the Medelfor's website: [Surreal Docs EULA](https://medelfor.com/eula/surreal-cloud "Surreal Docs EULA"). We do not collect and send any logs, however we store them in your system.

``seealso
title:Note
Note that by letting Surreal Docs collect anonymized usage data
you help the development process a lot.
``
