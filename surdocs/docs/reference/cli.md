# CLI reference

Surreal Docs CLI allows user to interact with Surreal Docs and Surreal Cloud using a commandline such as PowerShell or Windows CMD.

``attention
We strongly discourage usage of `git bash` terminal as it does not support several features vital for Surreal Docs in order to operate correctly.
``

Contents:
 - [Global options](docs/cli/global-options "Global options") - describes what global options are available when using Surreal Docs CLI;
 - [init](docs/cli/init "Init command") command - the command initializing/reconfiguring the Surreal Docs project.
 - [generate](docs/cli/generate "Generate command") command - the command used to generate the documentation;
 - [migrate](docs/cli/migrate "Migrate command") command - the command used to migrate surreal projects from old versions to new ones;
 - [auth](docs/cli/auth "Auth command") command - the command used to save [access tokens](docs/cli/global-options#access-tokens "Access tokens") in the system's vault;
 - [token create](docs/cli/token-create "Token create command") command - the command used to issue Surreal Cloud [access tokens](docs/cli/global-options#access-tokens "Access tokens");
 - [token list](docs/cli/token-list "Token list command") command - the command used to list [access tokens](docs/cli/global-options#access-tokens "Access tokens") issued by user;
 - [quota list](docs/cli/quota-list "Quota list command") command - the command used to show usage of Surreal Cloud resources constrained by a quota;
 - [organization create](docs/cli/organization-create "Organization create command") command - the command used to create Surreal Cloud organizations;
 - [organization delete](docs/cli/organization-delete "Organization delete command") command - the command used to delete Surreal Cloud organizations;
 - [organization list](docs/cli/organization-list "Organization list command") command - the command used to list Surreal Cloud organizations;
 - [project announce](docs/cli/project-announce "Project announce command") command - the command used to set a project-wide announcement;
 - [project collaborator add](docs/cli/project-collaborator-add "Project collaborator add command") command - the command used to add collaborators to Surreal Cloud projects;
 - [project collaborator delete](docs/cli/project-collaborator-delete "Project collaborator delete command") command - the command used to delete collaborators from Surreal Cloud projects;
 - [project collaborator list](docs/cli/project-collaborator-list "Project collaborator list command") command - the command used to list collaborators in Surreal Cloud projects;
 - [project create](docs/cli/project-create "Project create command") command - the command used to create Surreal Cloud projects;
 - [project delete](docs/cli/project-delete "Project delete command") command - the command used to generate the documentation;
 - [project list](docs/cli/project-list "Project list command") command - the command used to list Surreal Cloud projects;
 - [project publish](docs/cli/project-publish "Project publish command") command - the command used to change visibility of Surreal Cloud projects;

``contents
cli/global-options
cli/init
cli/generate
cli/migrate
cli/auth
cli/token-create
cli/token-list
cli/quota-list
cli/organization-create
cli/organization-delete
cli/organization-list
cli/project-announce
cli/project-collaborator-add
cli/project-collaborator-delete
cli/project-collaborator-list
cli/project-create
cli/project-delete
cli/project-list
cli/project-publish
``
