# Supported operating systems and Unreal Engine versions

Surreal Docs is intended to be used with 64-bit Windows systems, Windows 10 in particular. There's no Linux version available at the moment, and none is being planned.

Surreal Docs supports the following Unreal Engine versions:

| Unreal Engine version | Support [1]    |
|-----------------------|----------------|
| 4.27                  | Yes            |
| 5.0                   | Yes            |
| 5.1                   | Yes            |
| 5.2                   | On the way [2] |

***

[1] For a detailed list of supported and unsupported UE-features, please refer
to [Support of Unreal Engine features](docs/ue-features-support) page.

[2] ETA is June 2023 ([SD-1166](https://issues.internal.medelfor.com/youtrack/issue/SD-1166/Support-of-5.2-UE "SD-1166"))

### Support of custom Unreal Engine builds

Surreal Docs can be used with custom source-builds of Unreal Engine. When running [init](docs/cli/init "init command") for the first time Surreal Docs will automatically determine the root directory of your custom build in the following cases:
- When your project is located in a subdirectory of the custom-built engine;
- When your `.uproject` has a registered association in the `EngineAssociation` field.

In case the root wasn't properly detected you can choose the appropriate version manually right on the `init` screen. In case there's no proper root shown in the list, please select any version (or none), finish the initialization and manually add the root of desired UE version in the `surreal.json` file. More information on how to do it you can find in the [surreal.json reference](docs/surreal-json "surreal.json reference").
