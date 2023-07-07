# surreal.json reference

`surreal.json` is the main configuration file, users of Surreal Docs work with. It describes the Surreal Docs project and contains vital for its work settings. `surreal.json` is always located under `surdocs` directory which must be located directly in an Unreal Engine project root (where a `.uproject` file is).

This page describes options available in the `surreal.json`. There's no optional settings in `surreal.json` all of them must be presented in the file, however values of some of them can be left blank.

``spoiler
title: An example of `surreal.json`
```
{
    "contact_me_at": "dev@medelfor.com",
    "contents": [
        {
            "pages": [
                {
                    "page": "index"
                },
                {
                    "pinned": true,
                    "page": "docs/basics/quickstart"
                }
            ],
            "title": "Getting started"
        },
        {
            "pages": [
                {
                    "page": "docs/basics/quickstart"
                },
                {
                    "page": "docs/basics/os-and-ue-support"
                },
                {
                    "page": "docs/basics/installation"
                },
                {
                    "page": "docs/basics/ue-features-support"
                },
                {
                    "page": "docs/basics/troubleshooting"
                }
            ],
            "title": "Basics"
        },
        {
            "pages": [
                {
                    "page": "docs/guides/generate-docs-for-blueprint-only-projects"
                },
                {
                    "page": "docs/guides/generate-docs-for-plugins"
                }
            ],
            "title": "Guides"
        },
        {
            "pages": [
                {
                    "page": "docs/reference/cli"
                },
                {
                    "page": "docs/reference/surreal-json"
                },
                {
                    "page": "docs/reference/surreal-md"
                },
                {
                    "page": "docs/reference/tags"
                }
            ],
            "title": "Reference"
        },
        {
            "pages": [
                {
                    "is_external": true,
                    "page": "https://medelfor.com",
                    "title": "Medelfor"
                },
                {
                    "is_external": true,
                    "page": "https://store.medelfor.com",
                    "title": "Medelfor Store"
                }
            ],
            "title": "Medelfor"
        },
        {
            "pages": [
                {
                    "is_external": true,
                    "page": "https://github.com/medelfor/surreal-docs",
                    "title": "Surreal Docs on GitHub"
                },
                {
                    "is_external": true,
                    "page": "https://twitter.com/medelfor",
                    "title": "Follow us on Twitter"
                },
                {
                    "is_external": true,
                    "page": "https://linkedin.com/company/medelfor",
                    "title": "Follow us on LinkedIn"
                }
            ],
            "title": "Socials"
        }
    ],
    "copyright": "Copyright © 2023, Medelfor, Limited",
    "docs_title": "Documentation",
    "filters": {
        "content": {
            "exclude": [],
            "include": []
        },
        "cpp": {
            "exclude": [],
            "include": []
        },
        "do_export_private": false,
        "native_modules": {
            "exclude": [],
            "include": []
        }
    },
    "images_root": "images",
    "language": "en-US",
    "logo": "SurrealDocs.png",
    "master": "docs/index",
    "name": "Surreal Docs",
    "organization": "Medelfor, Limited",
    "tag": "public preview",
    "ue": {
        "configuration": "Debug",
        "root": "C:\\Program Files\\Epic Games\\UE_5.1",
        "target": ""
    },
    "url": "surrealdocs.com",
    "version": "1.0.1"
}
```
``

### General settings

#### `copyright`

| Type        | Can be blank |
|-------------|--------------|
| `string`    | Yes          |

Full copyright notice, e.g. "Copyright © 2023, My Company". If left blank, in the documentation the copyright will be generated based on the organization name. 

#### `contact_me_at`

| Type        | Can be blank |
|-------------|--------------|
| `string`    | Yes          |

Any contact mean with which we can contact you in case you send us logs through the CLI. Examples include `name.name@example.com`, `Person at Twitter`, `u/CoolGuy`. Note that there's no particular format for this field. Please leave the field empty if you don't want us to contact you back regarding reported logs.

#### `docs_title`

| Type        | Can be blank |
|-------------|--------------|
| `string`    | Yes          |

Name of the most high-level breadcrumb for custom user-provided pages in the documentation.

#### `language`

| Type        | Can be blank | Allowed values |
|-------------|--------------|----------------|
| `string`    | No           | `en-US`        |

At the moment Surreal Docs doesn't support multi-language documentation. The only valid value of this setting is `en-US`.

#### `logo`

| Type        | Can be blank |
|-------------|--------------|
| `string`    | Yes          |

Path to the documentation logo as in the filesystem, relative to the `images_root` (see [images_root](#images_root "images_root description")).

#### `name`

| Type        | Can be blank |
|-------------|--------------|
| `string`    | Yes          |

Name of the project for which the documentation is generated. Will be used in the header and titles of the pages.

#### `organization`

| Type        | Can be blank |
|-------------|--------------|
| `string`    | Yes          |

Name of the organization, the project belongs to.

#### `tag`

| Type        | Can be blank | Allowed values                                            |
|-------------|--------------|-----------------------------------------------------------|
| `string`    | Yes          | Recommended to use semver-valid "pre-release-identifiers" |

Version tag ("pre-release identifier" in terms of Semantic Versioning), e.g. `public-preview` or `beta`. Will be shown in the header of the documentation.

It's strongly recommended to use Semantic Versioning-compatible tags. You can read more about Semantic Versioning on their [website](https://semver.org/ "Semantic Versioning Homepage").

#### `url`

| Type        | Can be blank |
|-------------|--------------|
| `string`    | Yes          |

URL leading to the project's web-page.

#### `version`

| Type        | Can be blank | Allowed values                          |
|-------------|--------------|-----------------------------------------|
| `string`    | Yes          | Recommended to use semver-valid version |

Current version of the project. It's strongly recommended to use Semantic Versioning. You can read more about Semantic Versioning on its [website](https://semver.org/ "Semantic Versioning Homepage").

### Content settings

#### `contents`

| Type                        | Can be blank |
|-----------------------------|--------------|
| `array` of `object` (Group) | Yes          |

Describes the basic structure of the documentation as seen in the sidebar. Consists of Group objects.

##### \<Group>.`pages`

| Type                       | Can be blank |
|----------------------------|--------------|
| `array` of `object` (Page) | Yes          |

Lists the highest level pages forming this group. The order matters and will be reflected in the sidebar. Consists of Page objects.

###### \<Group>.`pages`.\<Page>.`page`

| Type     | Can be blank | Allowed values                                                                                                                                                            |
|----------|--------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `string` | No           | A valid URL, including an auto-link URL. You can find more info about auto-links in [Surreal Markdown reference](docs/surreal-md#auto-links "Surreal Markdown reference") |

An URL that leads to the designated page.

###### \<Group>.`pages`.\<Page>.`title`

| Type     | Can be blank   |
|----------|----------------|
| `string` | Yes            |

Title to show in the sidebar for this page.

###### \<Group>.`pages`.\<Page>.`is_external`

| Type   | Can be blank |
|--------|--------------|
| `bool` | N/A          |

Whether the page is an external to the documentation. Will add little arrow on the side of page's title.

###### \<Group>.`pages`.\<Page>.`api`

| Type     | Can be blank                      | Allowed values             |
|----------|-----------------------------------|----------------------------|
| `string` | No, but can be omitted completely | One of: `cpp`, `blueprint` |

Generates a link to either C++ API reference or Blueprint API reference, depending on the value. This setting can be omitted, but if presented no other settings[1] of Page object can be presented, in other words if presented `api` must be the only setting in the Page object.

***

[1] Except for the `pinned` setting

###### \<Group>.`pages`.\<Page>.`pinned`

| Type   | Can be blank |
|--------|--------------|
| `bool` | N/A          |

Whether this page should be considered an alias of the actual page.

If the `contents` contains two or more pages with the same URL, it's recommended that all of them should have `pinned` being equal `true`, except for only one (the canonical page). In such case all the pinned pages will be displayed with little pins on their sides, and they will lead to the canonical page. No additional pages will be created during generation.

##### \<Group>.`title`

| Type     | Can be blank   |
|----------|----------------|
| `string` | Yes            |

Title of the sidebar section generated from this Group.

#### `images_root`

| Type        | Can be blank | Allowed values                                                                                                                                |
|-------------|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| `string`    | No           | A valid path (as in filesystem) to the directory containing all the images used in the documentation. Page must be relative to `surreal.json` |

The path to the directory where all documentation's images are stored. It's not allowed to reference images outside this directory.

#### `master`

| Type        | Can be blank | Allowed values                                                                                              |
|-------------|--------------|-------------------------------------------------------------------------------------------------------------|
| `string`    | No           | A valid URL, including an auto-link URL. You can find more info about auto-links in [Surreal Markdown reference](docs/surreal-md#auto-links "Surreal Markdown reference") |

The path to the main documentation page.

### Export settings

#### `filters.content.include`

| Type                | Can be empty | Allowed values                                                            |
|---------------------|--------------|---------------------------------------------------------------------------|
| `array` of `string` | Yes          | List of directories inside `Content`. Each one should start with `/Game/` |

List of Content directories from where to export Blueprint entities. Include `/Game/` to export everything. 

#### `filters.content.exclude`

``attention
title: No support
This option is not implemented yet
``

#### `filters.cpp.include`

| Type                | Can be empty | Allowed values                                                         |
|---------------------|--------------|------------------------------------------------------------------------|
| `array` of `string` | Yes          | List of absolute[1] paths to directories where to look for C++ sources |

List of directories where to search for C++ entities that should be included in the resulting documentation.

`filters.cpp` and `filter.native_modules` are not strictly dependent on each other and emptying one of them can be used to generate documentation of only one type: BP reference or C++ reference. You can find more info on [Generate docs for C++ only or Blueprint only](docs/cpp-only-blueprint-only "Generate docs for C++ only or Blueprint only") page.

#### `filters.cpp.exclude`


| Type                | Can be empty | Allowed values                                                             |
|---------------------|--------------|----------------------------------------------------------------------------|
| `array` of `string` | Yes          | List of absolute[1] paths to directories where not to look for C++ sources |

List of directories containing C++ entities that should be excluded from the resulting documentation.

`filters.cpp` and `filter.native_modules` are not strictly dependent on each other and emptying one of them can be used to generate documentation of only one type: BP reference or C++ reference. You can find more info on [Generate docs for C++ only or Blueprint only](docs/cpp-only-blueprint-only "Generate docs for C++ only or Blueprint only") page.

***

[1] Absolute paths are ~~the bad choice we made~~ a temporary measure, we're working on fixing it.

#### `filters.native_modules.include`

| Type                | Can be empty | Allowed values                   |
|---------------------|--------------|----------------------------------|
| `array` of `string` | Yes          | List of native modules to export |

List of names of native modules that need to be exported. The name of a module is the `<name>` part when using standard Unreal Engine format `/Script/<name>.Entity`.

`filters.cpp` and `filter.native_modules` are not strictly dependent on each other and emptying one of them can be used to generate documentation of only one type: BP reference or C++ reference. You can find more info on [Generate docs for C++ only or Blueprint only](docs/cpp-only-blueprint-only "Generate docs for C++ only or Blueprint only") page.

#### `filters.native_modules.exclude`

``attention
title: No support
This option is not implemented yet
``

#### `filters.do_export_private`

| Type      | Can be empty | Allowed values                                                   |
|-----------|--------------|------------------------------------------------------------------|
| `boolean` | N/A          | `true` if private entities should be exported, `false` otherwise |

Whether to export private entities, such as private fields, properties, functions, methods, inner classes, enums or structs.

### Unreal Engine settings

#### `ue.configuration`

| Type        | Can be blank | Allowed values                                                  |
|-------------|--------------|-----------------------------------------------------------------|
| `string`    | No           | One of: `Debug`, `DebugGame`, `Development`, `Shipping`, `Test` |

The configuration to compile the Unreal Engine project with. More info on why Surreal Docs needs to compile your project, please refer to the [generate](docs/cli/generate "generate command") command page.

#### `ue.root`

| Type        | Can be blank | Allowed values                                                                                                                                                                                                                                        |
|-------------|--------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `string`    | No           | A valid Unreal Engine root directory of one of the supported versions or a custom build based on one of those versions. Find more about supported versions on the [Supported operating systems and Unreal Engine versions](docs/os-and-ue-support "Supported operating systems and Unreal Engine versions") |

An absolute path to the root of Unreal Engine used for this project. The Engine's root always contains an `Engine` directory. 

#### `ue.target`

| Type        | Can be blank | Allowed values                                                                                         |
|-------------|--------------|--------------------------------------------------------------------------------------------------------|
| `string`    | No           | Empty for Blueprint-only projects. A valid target for Unreal Engine projects that contain C++ sources. |

A target to build when compiling and running the project.
