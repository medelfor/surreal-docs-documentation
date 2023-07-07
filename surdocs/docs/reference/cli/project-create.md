# project create

This page describes the `project create` command, the command used to create Surreal Cloud projects.

### General description and syntax

`surdocs [global options] project create [options] location`

Creates a new project inside an organization which user must own. Automatically adds owner as collaborator. Expects an [access token](docs/cli/global-options#access-tokens "Access tokens") to be presented.

### Options

###### `location` (positional, required) - location of the project

Location of the project to create in format `<organization>/<project>`, where `<organization>` is a Surreal Cloud organization owned by user. `<project>` can consist of alphanumerical characters of any case, hyphens and underscores. Minimal length is one character, maximal - thirty two.

By default, a newly created project is public. You can change its visibility using [project publish](docs/cli/project-publish "Project publish").

###### `-h`, `--help` - show the help

Shows help regarding the command.

### Example

Create a new project `myproject` within an organization called `myorganization`.

```
surdocs project create myorganization/myproject
```
