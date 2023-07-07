# init

This page describes the `init` command, the command used to initialize or reconfigure current Surreal Docs project.

### General description and syntax

```
surdocs [global options] init [options]
```

The command is expected to be called from the root of an Unreal Engine projects, i.e. in a directory that contains a `.uproject` file. The command is always called in the interactive mode and hence cannot be called from a script. It's required to call the `init` at least once, since no other command can be called until the project is initialized.

When called the first time, `init` starts initialization, second and more - the reconfiguration. During initialization Surreal Docs patches your project files, installs a UE-plugin to connect to the Engine, setups basic documentation and generates the main config `surdocs/surreal.json` based on the info you provide during the initialization.

``seealso
title:Note
When reconfiguring (calling `init` the second+ time) all the changes manually made in the `surreal.json` will be preserved.
``

During initialization/reconfiguration `init` offers you to set several settings vital for docs generation. Most settings will be set automatically, but you're advised to review and update them if they're incorrect.

When all setting set as desired, please press the big "Done" button and wait until Surreal Docs finishes initialization.

``seealso
title:Note
The startup of `init` can take some time if the project is big and contains a lot of modules.
``

### Settings on the `init` screen

| Section | Property                              | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|---------|---------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     | Engine                                | Root of the engine used in the project. Will offer all locally installed versions of UE, from launcher or manually. If no proper version is present in this panel, please set the desired root path manually in `surreal.json` after finishing initialization. More info on the syntax of `surreal.json` can be found in [surreal.json reference](docs/surreal-json "surreal.json reference").                                                                     |
|      | Target                                | The target to use when compiling your project. The list will be empty if the Unreal Engine projects is Blueprint-only. If the project contains C++, it's recommended to select the usual target used to build and run the project. Only `*Editor` targets should be selected for Surreal Docs to work correctly. More info on why Surreal Docs needs to compile your project can be found on the page of [generate](docs/cli/generate "Generate command") command. |
|      | Configuration                         | The configuration to use when compiling your project. Any can be chosen if the project is Blueprint-only. If the project contains C++, then it's recommended to choose the configuration typically used to build the project.                                                                                                                                                                                                                                      |
| Export     | Export private members                | Whether the private entities (e.g. variables, fields, methods, functions) should be exported to the documentation.                                                                                                                                                                                                                                                                                                                                                 |
| Export     | Modules to export                     | The modules (in definition of Unreal Engine) to render in the documentation. It's recommended to select only relevant modules. The modules that belong to a plugin will be prefixed with "[Plugin]".                                                                                                                                                                                                                                                               |
| Project     | Name                                  | Name of the project as will appear in the resulting documentation.                                                                                                                                                                                                                                                                                                                                                                                                 |
| Project     | Version                               | Version of the project as will appear in the resulting documentation.                                                                                                                                                                                                                                                                                                                                                                                              |
| Project     | Organization                          | Organization developing the project as will appear in the resulting documentation.                                                                                                                                                                                                                                                                                                                                                                                 |
| Project     | If I report a bug, contact me back at | Any contact mean with which we can contact you in case you send us logs through the CLI. Examples include `name.name@example.com`, `Person at Twitter`, `u/CoolGuy`. Note that there's no particular format for this field. Please leave the field empty if you don't want us to contact you back regarding reported logs.                                                                                                                                         |

### Options

###### `-h`, `--help` - show the help

Shows help regarding the command.

### Example

Start initialization:

```
surdocs init
```
