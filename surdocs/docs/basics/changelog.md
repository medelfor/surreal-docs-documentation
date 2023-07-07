# What's new in Surreal Docs 1.1.0

Surreal Docs v1.1.0 brings full-fledged support of Surreal Cloud (incl. Surreal Cloud+ and Surreal Cloud Pro), reduced prices, project migration means, less installation dependencies, improved user workflow, fixes of numerous bugs and a significant discount.

Here's a detailed list of changes:

- **Full integration of Surreal Cloud**, Surreal Cloud+ and Surreal Cloud Pro: Surreal Docs CLI now enables user to easily access and manage Surreal Cloud resources such as organizations, projects, collaborators, tokens and quotas, and most importantly it allows to easily deploy the documentation to Surreal Cloud using updated [generate](docs/cli/generate "Generate command") command. You can find more info on these pages:
  - [Explanation](docs/surreal-cloud "Surreal Cloud") why one would need Surreal Cloud;
  - Updated [generate](docs/cli/generate "Generate command") command;
  - [auth](docs/cli/auth "Auth command") command;
  - [organization create](docs/cli/organization-create "Organization create command") command;
  - [organization delete](docs/cli/organization-delete "Organization delete command") command;
  - [organization list](docs/cli/organization-list "Organization list command") command;
  - [project announce](docs/cli/project-announce "Project announce command") command;
  - [project publish](docs/cli/project-publish "Project publish command") command;
  - [project create](docs/cli/project-create "Project create command") command;
  - [project delete](docs/cli/project-delete "Project delete command") command;
  - [project list](docs/cli/project-list "Project list command") command;
  - [project collaborator add](docs/cli/project-collaborator-add "Project collaborator add command") command;
  - [project collaborator delete](docs/cli/project-collaborator-delete "Project collaborator delete command") command;
  - [project collaborator list](docs/cli/project-collaborator-list "Project collaborator list command") command;
  - [quota list](docs/cli/quota-list "Quota list command") command;
  - [token create](docs/cli/token-create "Token create command") command;
  - [token list](docs/cli/token-list "Token list command") command;
- **Reduced prices** on all Medelfor products. Check out our [Store](https://store.medelfor.com "Medelfor Store") to find out more;
- A new `migrate` command that allows to convert an old Surreal project into a new one, automatically updating everything necessary. We recommend to use it after every Surreal Docs update. More info at [migrate](docs/cli/migrate "Migrate command") command page;
- NodeJS is no longer an installation dependency. We got rid of it so users would not have to contaminate their systems with it and so the installation process would be more reliable and robust;
- Surreal Docs does not change `.uproject` file anymore ([Issue #5](https://github.com/medelfor/surreal-docs/issues/5));
- Everything what can be overriden in Blueprints is now exported ([Issue #14](https://github.com/medelfor/surreal-docs/issues/14));
- Meet **25% discount** exclusively for our customers located in RCEP countries, which include: Australia, Brunei, Cambodia, China, India, Indonesia, Japan, South Korea, Laos, Malaysia, Myanmar, New Zealand, Philippines, Singapore, Thailand, Vietnam. Claim your discount on our [website](https://medelfor.com "Medelfor website").

### Fixed bugs

- Management of modules in [init](docs/cli/init "Init command") command is fully functional now ([Issue #13](https://github.com/medelfor/surreal-docs/issues/13));
- No more `SEGFAULT` when generator encounters a bad reference in a doc comment ([Issue #15](https://github.com/medelfor/surreal-docs/issues/15));
- Timestamp on the generated HTML pages now properly reflects time when the page was created ([Issue #9](https://github.com/medelfor/surreal-docs/issues/9));
- Classes derived from  `UDeveloperSettings`, `USubsystem`, `UBlueprintFunctionLibrary` are always exported now ([Issue #11](https://github.com/medelfor/surreal-docs/issues/11));
- Installation of Surreal Docs is now system-wide, while logs and cache is separate for each of users ([Issue #8](https://github.com/medelfor/surreal-docs/issues/8));
- Abstract classes are always exported now;
- Interfaces and their methods/functions are now properly matched with their counterparts.

### Contributors

Along with our team there were two persons who contributed to improve quality of Surreal Docs software: **SirLich** and **PrimaryFantasty**. Thank you!
