# Global options

This page describes what global options are available when using Surreal Docs CLI.

### Telemetry

###### `--no-tele` - disable telemetry

Disables telemetry until the current command finishes execution. When running the next command, one still needs to provide the CLI with this parameter if they wish to continue work with disabled telemetry.

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

### Access tokens

Access tokens are tokens issued by Surreal Cloud in order to access its resources on your behalf. To use access tokens, and consequently to use commands and options dependent on access tokens, you need to own an active subscription to Surreal Cloud, Surreal Cloud+ or Surreal Cloud Pro. You can find more info about our clouds on [Surreal Cloud](https://medelfor.com/products/surreal-cloud "Surreal Cloud") page.

Three following flags are mutually-exclusive. If none of them is presented then Surreal Docs first tries to load a token from the system's vault, then from the environment.

To issue an access token use the [token create](docs/cli/token-create "Token create command") command.

###### `--token-vault` - load an access token from the system's vault

Tries to load the token from the system's vault. Fails if it's not presented there.

Token can be saved into the system's vault using [auth](docs/cli/auth "Auth command") command. To save access tokens in the vault is the recommended way to store tokens. 

###### `--token-env` - load an access token from the environment variable

Tries to load the token from `SURDOCS_TOKEN` environment variable. Fails if it's not presented there.

###### `--token-stdin` - load an access token from the standard input

Tries to load the token from the CLI's standard input. Fails if it's not presented there.

You can pass a token into the CLI's standard input in different ways, e.g. like that:

```
echo "cld_XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX" | surdocs --token-stdin project list
```

It's not recommended to use this variant, since command line's history most probably will store the command and the access token what cannot be considered secure.

Secure way to do that would be to manually save your token in a file, and then using `cat` or a similar command, output the token the from file into the Surreal Docs CLI.

### Miscellaneous

###### `-h`, `--help` - show the help

Shows help regarding the CLI usage.

###### `-v`, `--version` - show Surreal Docs version

Prints out the current Surreal Docs version.
