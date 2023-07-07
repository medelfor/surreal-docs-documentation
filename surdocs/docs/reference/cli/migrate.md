# migrate

This page describes the `migrate` command, the command used to migrate surreal projects from old versions to new ones.

### General description and syntax

`surdocs [global options] migrate`

The command is expected to be called from the root of an Unreal Engine projects, i.e. in a directory that contains a `.uproject` file. The command requires current Surreal Docs project to be initialized, see the [init](docs/cli/init "Init command") command.

This command does not require any input from the user. When finished it'll output the list of actions taken to upgrade the project.

It is strictly recommended to call this command after every Surreal Docs update installed.

### Options

###### `-h`, `--help` - show the help

Shows help regarding the command.

### Example

Migrate a surreal project.

```
surdocs migrate
```
