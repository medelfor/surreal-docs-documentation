# project delete

This page describes the `project delete` command, the command used to delete Surreal Cloud projects.

### General description and syntax

`surdocs [global options] project delete [options] location`

Deletes the whole project; all versions, but keeps the project; a specific version. Will ask user to confirm intention to execute deletion. Expects an [access token](docs/cli/global-options#access-tokens "Access tokens") to be presented.

If neither `--version` nor `--versions-only` is presented, then deletes the project completely.

### Options

###### `location` (positional, required) - location of the project

Location of the project where to perform deletion, in format `<organization>/<project>`, where `<organization>` is a Surreal Cloud organization owned by user and `<project>` is an existing project within that documentation. 

###### `-h`, `--help` - show the help

Shows help regarding the command.

###### `-y`, `--yes` - do not ask for confirmation

Confirms that deletion must be executed without prompting user.

###### `-v`, `--version` - specific version which must be deleted

Deletes only this specific version from the project. Mutually exclusive with `--versions-only`.

###### `-i`, `--versions-only` - delete all versions from the project but keep the project

Delete all versions from the project but do not delete the project itself.

### Examples

Delete version `1.1.0` of project `myproject` within an organization `myorganization`.

```
surdocs project delete --version=1.1.0 myorganization/myproject
```

Delete all versions in project `myproject` within an organization `myorganization` keeping the project.

```
surdocs project delete --versions-only myorganization/myproject
```

Delete the project `myproject` within an organization `myorganization` completely.

```
surdocs project delete myorganization/myproject
```
