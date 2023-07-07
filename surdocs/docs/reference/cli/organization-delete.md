# organization delete

This page describes the `organization delete` command, the command used to delete Surreal Cloud organizations.

### General description and syntax

`surdocs [global options] organization delete [options] name`

Deletes the specified organization owned by user. Will ask user to confirm intention to execute deletion. Expects an [access token](docs/cli/global-options#access-tokens "Access tokens") to be presented.

### Options

###### `name` (positional, required) - location of the project

Name of Surreal Cloud organization owned by user. 

###### `-h`, `--help` - show the help

Shows help regarding the command.

###### `-y`, `--yes` - do not ask for confirmation

Confirms that deletion must be executed without prompting user.

### Examples

Delete organization `myorganization` without confirmation.

```
surdocs organization delete -y myorganization
```
