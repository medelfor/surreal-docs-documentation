# project delete

This page describes the `generate` command, the command used to start the docs generation.

### General description and syntax

`surdocs [global options] generate [options] out`

The command is expected to be called from the root of an Unreal Engine projects, i.e. in a directory that contains a `.uproject` file. The command requires current Surreal Docs project to be initialized, see the [init](docs/cli/init "Init command") command.

When being executed the first time, `generate` will start compilation of the project, since it needs to compile the plugin installed during `init`. Hence, the first time execution can take longer than usual.

``attention
Unreal Engine project must be compilable in order for Surreal Docs to generate the documentation. However that does not mean that the project must include C++, it can be a [Blueprint-only project](https://docs.medelfor.com/medelfor/surreal-docs/latest/en-US/docs/generate-docs-for-blueprint-only-projects "Generating documentation for Blueprint-only projects") as well.
``

### Options

#### `out` (positional, required)

The directory to dump the resulting documentation into. Will be created if doesn't exist. It's recommended to use an empty directory or a directory with already dumped documentation. It's not recommended to use the current directory as the `out` directory.

#### `-n`, `--non-rich` - disable interactive interface

Disables the rich interface, `generate` provides by default. Useful when the command is called out of a script, in the so-called "unattended" mode.

#### `-h`, `--help` - show the help

Shows help regarding the command.

### Example

Generate documentation and dump it in the `out` folder:

```
surdocs generate out
```
