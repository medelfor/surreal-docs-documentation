# auth

This page describes the `auth` command, the command used to save [access tokens](docs/cli/global-options#access-tokens "Access tokens") in the system's vault.

### General description and syntax

`surdocs [global options] auth`

Expects a valid access token to be presented in the standard input.

When a valid token is saved in the vault, execution of other commands dependent on a token does not require user to provide a token, since it will be automatically loaded from the vault.

### Options

###### `-h`, `--help` - show the help

Shows help regarding the command.

### Example

Print out the access token to the CLI's standard input and save it in the vault.

```
echo "cld_XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX" | surdocs auth
```

Note that this is not strictly safe. For a more secure variant refer to the [Access tokens](docs/cli/global-options#access-tokens "Access tokens") section.
