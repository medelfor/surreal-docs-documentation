# project collaborator delete

This page describes the `project collaborator delete` command, the command used to delete collaborators from Surreal Cloud projects.

### General description and syntax

`surdocs [global options] project collaborator delete [options] location email`

Deletes a collaborator from a Surreal Cloud project, consequently denying them access to the project. Will ask user to confirm intention to execute deletion. Expects an [access token](docs/cli/global-options#access-tokens "Access tokens") to be presented.

Owner of the organization (which is always a collaborator) cannot be deleted from the project.

### Options

###### `location` (positional, required) - location of the project

Location of the project where to delete a collaborator from, in format `<organization>/<project>`, where `<organization>` is a Surreal Cloud organization owned by user and `<project>` is an existing project within that documentation. 

###### `email` (positional, required) - email of the Medelfor account the collaborator owns

Email of Medelfor account owned by collaborator.

###### `-y`, `--yes` - do not ask for confirmation

Confirms that deletion must be executed without prompting user.

###### `-h`, `--help` - show the help

Shows help regarding the command.

### Example

Delete collaborator with email `employee1@company.com` from the project `myproject` of organization `myorganization`.

```
surdocs project collaborator delete myorganization/myproject employee1@company.com
```
