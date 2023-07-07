# project list

This page describes the `project list` command, the command used to list Surreal Cloud projects.

### General description and syntax

`surdocs [global options] project list [options] organization`

Prints out list of projects in a Surreal Cloud organization which user must own. Expects an [access token](docs/cli/global-options#access-tokens "Access tokens") to be presented.

### Options

###### `organization` (positional, required) - organization whose projects to list

Name of a user-owned organization to load the projects from.

###### `-h`, `--help` - show the help

Shows help regarding the command.

### Example

List all projects within `myorganization` organization.

```
surdocs project list myorganization
```
