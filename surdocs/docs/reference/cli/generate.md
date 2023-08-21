# generate

This page describes the `generate` command, the command used to start the docs generation.

### General description and syntax

```
surdocs [global options] generate [options] out
```

The command is expected to be called from the root of an Unreal Engine projects, i.e. in a directory that contains a `.uproject` file. The command requires current Surreal Docs project to be initialized, see the [init](docs/cli/init "Init command") command.

When being executed the first time, `generate` will start compilation of the project, since it needs to compile the plugin installed during `init`. Hence, the first time execution can take longer than usual.

``attention
Unreal Engine project must be compilable in order for Surreal Docs to generate the documentation. However that does not mean that the project must include C++, it can be a [Blueprint-only project](https://docs.medelfor.com/medelfor/surreal-docs/latest/en-US/docs/generate-docs-for-blueprint-only-projects "Generating documentation for Blueprint-only projects") as well.
``

### Options

###### `out` (positional, required) - output directory

The directory to dump the resulting documentation into. Will be created if it doesn't exist already. It's recommended to use an empty directory or a directory with already dumped documentation. It's not recommended to use the current directory as the `out` directory.

###### `-n`, `--non-rich` - disable interactive interface

Disables the rich interface, `generate` provides by default. Useful when the command is called out of a script, in the so-called "unattended" mode.

###### `-c`, `--clean` - purge out directory

Deletes everything in the specified `out` directory before starting to generate docs. Use with caution.

###### `-i`, `--image-threads` - count of image render instances

Default value is `2`.

Parallelize image rendering. Available options are `1`, `2`, `3` and `4`. `3` and `4` are experimental and may yield erroneous results. Use them with caution.

###### `-d`, `--deploy` - deploy documentation

Indicates that deploy is required and specifies where to deploy the documentation. Expects an [access token](docs/cli/global-options#access-tokens "Access tokens") to be presented. Expects value in format `<organization>/<project>`, where `<organization>` is a Surreal Cloud organization owned by access token's owner and `<project>` is an existent project within that organization.

Expects that in `surreal.json`, `version` field is filled with a [SemVer](https://semver.org/ "Semantic versioning")-compatible version. More info about `version` in [surreal.json reference](docs/surreal-json#code-version-code).

In case such version is already deployed and exists in the Cloud, before deployment the Cloud version will be purged and created anew.

###### `-h`, `--help` - show the help

Shows help regarding the command.

### Examples

Generate documentation and dump it in the `out` folder:

```
surdocs generate out
```

Generate documentation and deploy to `myproject` project of `myorg` organization:

```
surdocs generate out --deploy=myorg/myproject
```
