# project collaborator add

This page describes the `project collaborator add` command, the command used to add collaborators to Surreal Cloud projects.

### General description and syntax

`surdocs [global options] project collaborator add [options] location email`

Adds a new collaborator to a Surreal Cloud project. Useful when the project is private, since in that case only collaborators are able to access it. Expects an [access token](docs/cli/global-options#access-tokens "Access tokens") to be presented.

Collaborators cannot perform administrating actions like owner can. Collaborators can only view pages inside the project.

There are no limits on how many collaborators can be added to a project.

Owner of the organization is automatically added as collaborator into every project created within that organization.

### Options

###### `location` (positional, required) - location of the project

Location of the project where to add a new collaborator, in format `<organization>/<project>`, where `<organization>` is a Surreal Cloud organization owned by user and `<project>` is an existing project within that documentation. 

###### `email` (positional, required) - email of the Medelfor account the collaborator owns

Email of an existing Medelfor account owned by collaborator. Collaborator will need to log in into that account to access the project.

###### `-h`, `--help` - show the help

Shows help regarding the command.

### Example

Add collaborator with email `employee1@company.com` to the project `myproject` within an organization `myorganization`.

```
surdocs project collaborator add myorganization/myproject employee1@company.com
```
