# token list

This page describes the `token list` command, the command used to list [access tokens](docs/cli/global-options#access-tokens "Access tokens") issued by user.

### General description and syntax

`surdocs [global options] token list`

This command will open system's default browser and will ask user to log in their Medelfor account. User must have an active Surreal Cloud, Surreal Cloud+ or Surreal Cloud Pro subscription in order to be able to issue access tokens. [token create](docs/cli/token-create "Token create command") command can be used to issue new access tokens.

### Options

###### `-h`, `--help` - show the help

Shows help regarding the command.

### Example

Issue an access token.

```
surdocs token list
```
