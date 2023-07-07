# Installation and requirements

The latest version of Surreal Docs is `1.1.0`

We publish releases of new Surreal Docs versions on the "Releases" page in 
[our GitHub](https://github.com/medelfor/surreal-docs/releases/ "Releases").

To install Surreal Docs please download the latest installer from our website and run it. The installer will do everything necessary to set up Surreal Docs on your system.

In case you have a Surreal Docs project created with a previous version of Surreal Docs, you'll need to migrate it. Luckily Surreal Docs CLI makes it easy.

In order to migrate a project please navigate to the root directory of that project (where `.uproject` is located) and run the following command:
```
surdocs migrate
```
It'll take all actions necessary to ensure your Surreal project will work with the newly installed version of Surreal Docs. You can read more about the command on the [migrate](docs/cli/migrate "Migrate command") page.

``attention
title: Troubleshooting installation
In case something goes wrong during installation, please refer to the [troubleshooting](docs/troubleshooting) page to find advice on how to address it.
``

``seealso
title: Visual Studio
Note also that in order to work Surreal Docs requires Microsoft Visual Studio to be installed on your machine.

For instructions on how to install Visual Studio to use it with Unreal Engine, please refer to [this page](https://docs.unrealengine.com/5.2/en-US/setting-up-visual-studio-development-environment-for-cplusplus-projects-in-unreal-engine/ "Installation of Visual Studio") of the Epic Games' documentation.
``
