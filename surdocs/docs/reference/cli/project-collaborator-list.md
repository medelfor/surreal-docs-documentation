# project collaborator list

This page describes the `project collaborator list` command, the command used to list collaborators in Surreal Cloud projects.

### General description and syntax

`surdocs [global options] project collaborator list [options] location`

Lists all collaborators in a Surreal Cloud project. Expects an [access token](docs/cli/global-options#access-tokens "Access tokens") to be presented.

### Options

###### `location` (positional, required) - location of the project

Location of the project where to load collaborators from, in format `<organization>/<project>`, where `<organization>` is a Surreal Cloud organization owned by user and `<project>` is an existing project within that documentation. 

###### `-h`, `--help` - show the help

Shows help regarding the command.

### Example

List collaborators in the project `myproject` of organization `myorganization`.

```
surdocs project collaborator list myorganization/myproject
```
