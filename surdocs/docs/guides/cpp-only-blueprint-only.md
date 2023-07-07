# Generating C++ documentation only or Blueprint documentation only

Sometimes there's no need to have both C++ API reference and Blueprint API reference in the documentation. This page provides details on how to disable generation of one reference to leave the other one. Both variants require manual editing of `surreal.json`.

``seealso
title: Note
This guide supposes that your project is already initialized. If it's not please first refer to [Quickstart](docs/quickstart "Quickstart").
``

### I want to disable C++ API reference

Please open `surdocs/surreal.json` and navigate to the part with `filters` and `cpp` inside it. After that remove all entries from the `include` array so this part of `surreal.json` would like this:
```
...
        "cpp": {
            "exclude": [],
            "include": []
        },
...
```

Then navigate to `contents` inside `surreal.json` and find the page which looks like this:
```
{
    "api": "cpp",
    "is_external": false,
    "is_pinned": false
}
```

Remove this whole entry from outer array to remove the sidebar link to C++ API reference.

Save the file and run the [generate](docs/cli/generate "Generate command") command as usual. You can find more info about structure of `surreal.json` in the [reference](docs/surreal-json "Surreal JSON reference").

### I want to disable Blueprint API reference

Please open `surdocs/surreal.json` and navigate to the part with `filters` and `native_modules` inside it. After that remove all entries from the `include` array so this part of `surreal.json` would like this:
```
...
        "native_modules": {
            "exclude": [],
            "include": []
        },
...
```

Then navigate to `contents` inside `surreal.json` and find the page which looks like this:
```
{
    "api": "blueprint",
    "is_external": false,
    "is_pinned": false
}
```

Remove this whole entry from outer array to remove the sidebar link to Blueprint API reference.

Save the file and run the [generate](docs/cli/generate "Generate command") command as usual. You can find more info about structure of `surreal.json` in the [reference](docs/surreal-json "Surreal JSON reference").

### Smart features

Note that in order to maximize quality and completeness of resulting documentation Surreal Docs sometimes uses information from native definitions when generating BP reference and vice-versa. So disabling generation of one reference may consequently disable some smart features in the remaining reference.
