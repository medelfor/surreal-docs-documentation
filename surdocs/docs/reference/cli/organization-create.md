# organization create

This page describes the `organization create` command, the command used to create Surreal Cloud organizations.

### General description and syntax

`surdocs [global options] organization create name`

Creates a new organization with user as its owner. Expects an [access token](docs/cli/global-options#access-tokens "Access tokens") to be presented.

### Options

###### `name` (positional, required) - name of the organization

Name of the organization to create. Can consist of alphanumerical characters of any case, hyphens and underscores. Minimal length is one character, maximal - thirty two.

###### `-h`, `--help` - show the help

Shows help regarding the command.

### Example

Create a new organization called `myorganization`.

```
surdocs organization create myorganization
```
