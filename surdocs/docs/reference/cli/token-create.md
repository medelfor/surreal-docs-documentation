# token create

This page describes the `token create` command, the command used to issue Surreal Cloud [access tokens](docs/cli/global-options#access-tokens "Access tokens").

### General description and syntax

`surdocs [global options] token create`

This command will open system's default browser and will ask user to log in their Medelfor account. User must have an active Surreal Cloud, Surreal Cloud+ or Surreal Cloud Pro subscription in order to be able to issue access tokens. [token list](docs/cli/token-list "Token list command") command can be used to list tokens already issued by user. 

### Options

###### `-h`, `--help` - show the help

Shows help regarding the command.

### Example

Issue an access token.

```
surdocs token create
```
