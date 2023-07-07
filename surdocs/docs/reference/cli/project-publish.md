# project publish

This page describes the `project publish` command, the command used to change visibility of Surreal Cloud projects.

### General description and syntax

`surdocs [global options] project publish [options] location`

Changes visibility of a project inside an organization which user must own. Expects an [access token](docs/cli/global-options#access-tokens "Access tokens") to be presented.

### Options

###### `location` (positional, required) - location of the project

Location of the project whose visibility needs to be changed, in format `<organization>/<project>`, where `<organization>` is a Surreal Cloud organization owned by user and `<project>` is an existing project within that documentation. 

###### `-h`, `--help` - show the help

Shows help regarding the command.

#### Scope group

One of the flags in this group must be presented. The flags are mutually exclusive.

###### `-p`, `--public` - make project public

Makes project public and available to the Internet.

###### `-r`, `--private` - make project private

Makes project private and available only to collaborators added by user. [project collaborator add](docs/cli/project-collaborator-add "Project collaborator add") can be used to add collaborators and [project collaborator list](docs/cli/project-collaborator-list "Project collaborator list") to list them.

Note that in order to make a project private, user's Surreal Cloud plan has to allow private hosting. Check out [Surreal Cloud](docs/surreal-cloud) page to find out which ones do allow that.

### Example

Make project `myproject` within an organization `myorganization` private.

```
surdocs project publish --private myorganization/myproject
```
