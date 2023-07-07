# Generating documentation for content-only UE-plugins

Surreal Docs can generate documentation for Unreal Engine plugins as well. The most common application for this is when the project requiring documentation is itself a plugin. This page describes the steps necessary to generate documentation for a plugin.

### Step 1: select plugin modules during `init`

``figure
align:right
url: images/ExportPlugin.png
The modules marked with "[Plugin]" belong to a plugin
``
In order to do that you need to run the `init` command in your project's root directory. It doesn't matter whether the `init` was already called for this project or not. 

After you started the `init` command, using the "Modules to export" list select all the modules that belong to your plugin and deselect all that do not. The modules originating from a plugin and not from your project will be prefixed with "[Plugin]" as seen on the image.

You can find more info about the `init` command on the [init page](docs/cli/init "init description") of our [CLI reference](docs/cli "CLI reference").

### Step 2: remove `/Game/` from `surreal.json`

Upon successful initialization, please navigate to the `surdocs` folder inside your project and open the `surreal.json` file. Find the following part there:
```
...
"filters": {
    "content": {
        "exclude": [],
        "include": [
            "/Game/"
        ]
    }
...
```
and remove the `/Game/` entry, so the `include` array inside the `content` object would be empty. Save your changes.

``seealso
title:Note
More info on the syntax of `surreal.json` can be found in [surreal.json reference](docs/surreal-json "surreal.json reference").
``

Now all the necessary steps are taken and what's left is to simply run the `generate` command as usual:
```
surdocs generate <out directory>
```
``seealso
title:Note
More info about the `generate` command can be found on the [generate page](docs/cli/generate "generate description").
``
