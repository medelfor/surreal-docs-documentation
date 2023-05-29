# Generating documentation for Blueprint-only projects

Surreal Docs is able to generate documentation for Unreal Engine projects that do not contain any C++ code. In fact such generation will take much less time than the one where C++ is included. This page covers a few details related to the docs generation for Blueprint-only projects.

Blueprint-only generation is almost the same as the C++-included one. The only difference from the user's standpoint is the possible appearance of a window similar to the one shown below:

![UE Editor prompt](images/UeEditorPrompt.png "UE Editor prompt")

This prompt window can prevent docs generation to be called from a script, since it requires a user action. In order to turn it off, please add the code below to the configuration file located by the following path: `<project_root>/Saved/Config/WindowsEditor/EditorPerProjectUserSettings.ini`

```
[/Script/UnrealEd.EditorLoadingSavingSettings]
bForceCompilationAtStartup=True
```

During execution of the `init` command (about which you can read more on [its page](docs/cli/init "Init command")) Surreal Docs will automatically add these lines to the mentioned file. But if you encountered the window it means something went wrong and Surreal Docs wasn't able to patch the config.
