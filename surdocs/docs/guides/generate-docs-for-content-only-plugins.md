# Generating documentation for content-only UE-plugins

Surreal Docs can generate documentation for Unreal Engine plugins consisting only of content as well as [plugins with sources](docs/generate-docs-for-plugins "Generate docs for plugins").

There's one simple additional step you need to take before starting to generate docs for content-only plugins. 

``seealso
title: Note
This guide supposes that your project is already initialized. If it's not please first refer to [Quickstart](docs/quickstart "Quickstart").
``

Please open `surdocs/surreal.json` and navigate to the part with `filters` and `content` inside it. Then just add the name of your plugin into the `include` array. Note that the name should be surrounded with slashes, e.g. for plugin named `MyPlugin` the entry should look like `/MyPlugin/`.

When done this part of `surreal.json` should look like this:
```
...
    "filters": {
        "content": {
            "exclude": [],
            "include": [
                "/Game/",
                "/MyPlugin/"
            ]
        },
...
```

Save the file and run the [generate](docs/cli/generate "Generate command") command as usual. You can find more info about structure of `surreal.json` in the [reference](docs/surreal-json "Surreal JSON reference").
