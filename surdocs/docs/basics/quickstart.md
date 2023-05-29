# Quickstart

In order to start, please download and run the Surreal Docs installer. The latest version can be found on the [Releases](https://github.com/medelfor/surreal-docs/releases/ "Releases") page in Surreal Docs GitHub. More info about the installation process of Surreal Docs can be found on the [Installation and Requirements](docs/installation "Installation and Requirements") page.

Surreal Docs installer installs the Surreal Docs CLI, so you would be able
to run Surreal Docs from the command line.

In order to generate documentation for your Unreal Engine project, please open
a console/terminal of your choice (Windows CMD, PowerShell, etc.) and navigate to the
root directory[1] of your Unreal Engine project.

When done, please run the following command in your console:
```
surdocs init
```

It will invoke the initialization screen where you can set options of your project
and the documentation you are going to generate. Surreal Docs will detect and set most settings automatically, but you should review them and update if
necessary.

On the same screen you should choose the project modules for which you want to generate documentation.

After everything's finished, please click the "Done" button and wait until
Surreal Docs will set up your project.

Note that Surreal Docs changes the `.uproject` file, so before changing it,
the system makes a backup of the file and saves it in the same directory.

The `surdocs init` should be run at least once - on the initial setup of the project. You can always rerun `init` in order to reconfigure the project. More info about the `init` command can be found on the [init page](docs/cli/init "init description") of our [CLI reference](docs/cli "CLI reference").

If `surdocs init` has finished successfully, then please run the next command:

```
surdocs generate <output directory>
```

It will invoke the generation screen and start generating your documentation.
You will be able to observe the progress and will see error's details if
something goes wrong.

Note that the first time you run `surdocs generate` the generation will take some extra time, since Surreal Docs needs to compile the plugin it installs in order to link with Unreal Engine. More info about the `generate` command can be found on the [generate page](docs/cli/generate "generate description").

***
[1] The directory that contains the `.uproject` file.
