# project announce

This page describes the `project announce` command, the command used to set a project-wide announcement.

### General description and syntax

`surdocs [global options] project announce [options] location`

Announces user-provided text on every page of a project inside an organization which user must own. Expects an [access token](docs/cli/global-options#access-tokens "Access tokens") to be presented.

### Options

###### `location` (positional, required) - location of the project

Location of the project where to make an announcement, in format `<organization>/<project>`, where `<organization>` is a Surreal Cloud organization owned by user and `<project>` is an existing project within that documentation. 

###### `-h`, `--help` - show the help

Shows help regarding the command.

#### Announcement group

One of the flags in this group must be presented. The flags are mutually exclusive.

###### `-c`, `--clear` - remove announcement

Clears the announcement.

###### `announcement` (positional) - text of announcement

Arbitrary text to announce.

### Example

Announce that "Version 1.10 will be released 20 August 2023" on every page of project `myproject` within an organization `myorganization`.

```
surdocs project announce myorganization/myproject "Version 1.10 will be released 20 August 2023"
```
