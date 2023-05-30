# Surreal Markdown reference

Surreal Markdown is a feature-rich dialect of Markdown. This page describes additional features Surreal Markdown (hereinafter Surreal MD) introduces. This page does not cover the vanilla Markdown, for a reference on Markdown, please refer to [Markdown Guide](https://www.markdownguide.org/basic-syntax/ "Markdown Guide").

### General information

Surreal Markdown is a superset of Markdown, with some features borrowed from GitHub-flavored markdown, including tables and strikethrough elements and some authored completely by us such as any Surreal Block.

No HTML is allowed inside Surreal Markdown.

### Extensions to Markdown

#### Tables

Surreal Markdown introduces tables in the most common syntax, as seen e.g. in GitHub Flavored Markdown. 

A typical table can be created with the following syntax:
```
| First Header  | Second Header |
| ------------- | ------------- |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |
```
The result is as follows:

| First Header  | Second Header |
| ------------- | ------------- |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |

The width of cells doesn't have to be aligned, they can freely vary in width, e.g.:
```
| Command | Description |
| --- | --- |
| Value 1 | Short description |
| Val 2 | A very very very very very very long one |
```
What produces the following result:

| Command | Description |
| --- | --- |
| Value 1 | Short description |
| Val 2 | A very very very very very very long one |

Markdown styling can freely be used inside the table cells, but not Surreal Blocks, e.g.:
```
| First Header  |
| ------------- |
| **Content** Cell  |
| Content _Cell_  |
```
What gives:

| First Header  |
| ------------- |
| **Content** Cell  |
| Content _Cell_  |

Finally, content inside cells can be aligned. Take a look at the following example:
```
| Left-aligned | Center-aligned | Right-aligned |
| :---         |     :---:      |          ---: |
| A            | B              | C             |
| A            | B              | C             |
```
What yields the following result:

| Left-aligned | Center-aligned | Right-aligned |
| :---         |     :---:      |          ---: |
| A            | B              | C             |
| A            | B              | C             |

If a pipe needs to be placed inside a table's cell, it should be prepended with a backslash as such `\|`.

#### Strikethrough

In order to cross-out a piece of text, the following syntax should be used:

```
Lorem ~~ipsum~~ dolor sit amet
```

What renders as: Lorem ~~ipsum~~ dolor sit amet

#### Auto-links

When using Markdown's links and images or Surreal MD's Figure Block, it's necessary to provide them with URL of the page a link is referencing or an image a figure shows. If such page is not external, i.e. is located inside the documentation, then it's not necessary to provide the full URL to it.

In the following cases the URL can be substantially shortened:
 - When URL leads to a user-provided Markdown page in this documentation, in such case the URL can be shortened to `docs/<path-to-page-as-defined-by-contents>`. Check [Contents Block](#contents "Contents Block") documentation to find out more on how it defines internal paths in the documentation;
 - When URL leads to a page of C++ API reference or Blueprint API reference, then it can be shortened to `api/cpp/<path-to-page>` and `api/blueprint/<path-to-page>` respectively;
 - When URL leads to one of this documentation's images, the URL can be shortened to `<images root>/<path-to-image-as-in-filesystem>`, where `<images root>` is the value defined in the `images_root` of `surreal.json`, about which you can read more in [its reference](docs/surreal-json "surreal.json reference").

#### Surreal Blocks

The power of Surreal Markdown is lies in use of Surreal Blocks - structures introduced specifically for Surreal Docs.

The general syntax of a Surreal Block is as follows:

```
``<name>
<param1>:<value1>
<param2>:<value2>
<content>
``
```

As seen in the snipper, Surreal Blocks have names, may have parameters with values and may have the main content. A Surreal Block must be separated from other text with \`\` and new lines. Order of parameters doesn't matter. Most of Surreal Blocks can include other Surreal Blocks and Markdown, as can values of some of their parameters.

Surreal Blocks are processed before any Markdown, except for the code block. Surreal Blocks cannot be used as inline Markdown.

Let's cover all available Surreal Blocks.

##### Spoiler

Surreal Block name: `spoiler`

Main content purpose: main content becomes content of the spoiler, can contain Surreal MD, can contain other Surreal Blocks.

| Parameter  | Type     | Default Value | Explanation                              | Is Required | Supports Markdown in its value |
|------------|----------|---------------|------------------------------------------|-------------|--------------------------------|
| `title`    | string   |               | The title of spoiler                     | No          | Yes                            |
| `opened`   | boolean | `false`       | Whether the spoiler is opened by default | No          | N/A                            |

This Block allows one to hide some content under a spoiler.

Example of a spoiler:
```
``spoiler
title: Spoiler made possible by `Surreal MD`
Content to hide
``
```
It gives the following result:
``spoiler
title: Spoiler made possible by `Surreal MD`
Content to hide
``

##### Figure

Surreal Block name: `figure`

Main content purpose: becomes figure's caption, can contain Surreal MD, cannot contain other Surreal Blocks.

Figure Block allows to integrate a figure in a Surreal MD page.

| Parameter | Type    | Default Value | Explanation                                                                                                        | Is Required | Supports Markdown in its value |
|-----------|---------|---------------|--------------------------------------------------------------------------------------------------------------------|-------------|--------------------------------|
| `url`     | string  |               | Url of the image to show                                                                                           | Yes         | No                             |
| `align`   | custom | `default`     | Alignment of the figure. The behaviour similar to the CSS' `float`. Possible value are `left`, `right`, `default`. | No          | N/A                            |

Example of a figure:
```
``figure
float: left
url: images/SurrealDocs.png
Figure's caption
``

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec non dolor tortor. Nulla tempor elit dolor. Vivamus felis justo, vulputate ac scelerisque quis, laoreet sed ipsum. Suspendisse vel lacus nec leo imperdiet pharetra id sit amet velit. Ut et magna dignissim, posuere mi eu, convallis mi. In quis erat sit amet justo pulvinar euismod eget eu libero. In quis erat sit amet justo pulvinar euismod eget eu libero. In quis erat sit amet justo pulvinar euismod eget eu libero. In quis erat sit amet justo pulvinar euismod eget eu libero. Aenean aliquet fermentum eros, in viverra tellus pellentesque dictum. Duis aliquet erat sem, a euismod purus viverra non. Praesent vehicula ex vitae neque ultrices rhoncus. Sed faucibus lorem justo, in fermentum turpis vulputate non. Proin et lorem tempor, sodales metus quis, efficitur augue.
```

What yields:

``figure
align: left
url: images/SurrealDocs.png
Figure's caption
``

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec non dolor tortor. Nulla tempor elit dolor. Vivamus felis justo, vulputate ac scelerisque quis, laoreet sed ipsum. Suspendisse vel lacus nec leo imperdiet pharetra id sit amet velit. Ut et magna dignissim, posuere mi eu, convallis mi. In quis erat sit amet justo pulvinar euismod eget eu libero. In quis erat sit amet justo pulvinar euismod eget eu libero. In quis erat sit amet justo pulvinar euismod eget eu libero. In quis erat sit amet justo pulvinar euismod eget eu libero. Aenean aliquet fermentum eros, in viverra tellus pellentesque dictum. Duis aliquet erat sem, a euismod purus viverra non. Praesent vehicula ex vitae neque ultrices rhoncus. Sed faucibus lorem justo, in fermentum turpis vulputate non. Proin et lorem tempor, sodales metus quis, efficitur augue.

##### Tabs

Surreal Block name: `tabs`

Main content purpose: can only contain `page` Blocks.

Tabs Block allows to create a block of content divided between several tabs.

##### Page

Surreal Block name: `page`

Main content purpose: becomes content of a respective page inside the Tabs Block, can contain Surreal MD, can contain other Surreal Blocks.

Page Block creates a page inside the Tabs Block. Can only be placed inside a Tabs Block.

| Parameter | Type    | Default Value | Explanation                 | Is Required | Supports Markdown in its value |
|-----------|---------|--------------|-----------------------------|-------------|--------------------------------|
| `title`   | string  |        | Title of the resulting page | No          | Yes                            |

Example of a Tabs block with pages:
```
``tabs
``page
title: Page 1
Some content for
the page 1
``
``page
title: Page 2
Some content for
the page 2
``
``
```

What gives:

``tabs
``page
title: Page 1
Some content for
the page 1
``
``page
title: Page 2
Some content for
the page 2
``
``

##### Contents

Surreal Block name: `contents`

Main content purpose: list of URLs of subpages, cannot contain Surreal MD, cannot contain other Surreal Blocks.

Contents Block forms structure of your documentation by defining what pages must be considered as subpages of the current page (parent page). Each line inside the main content represent a path to the source file of a subpage file without the extension. Path is relative to the file of the parent page.

| Parameter   | Type    | Default Value | Explanation                                                                               | Is Required | Supports Markdown in its value |
|-------------|---------|---------------|-------------------------------------------------------------------------------------------|-------------|--------------------------------|
| `expand` | boolean | `false`       | Whether to replace the parent page with the list of subpages, when rendering the sidebar. | No          | No                             |

Example of a Contents block with pages:
```
``contents
cli/global-options
cli/init
cli/generate
``
```

What result that gives you can find in the sidebar, under "CLI reference" section. CLI reference page contains contents exactly the same.

Remember that not a directory structure of your source files but Contents Block defines URLs of your pages in the documentation.

##### Admonition Blocks

Surreal Blocks names: `admonition` | `caution` | `topic` | `warning` | `danger` | `attention` | `error` | `hint` | `tip` | `important` | `note` | `seealso` | `todo`

Main content purpose: becomes content of the admonition element, can contain Surreal MD, can contain other Surreal Blocks.

Family of Admonition Blocks allows to highlight role of page content's part. For example make a note or write a warning message. All blocks in the family support the same set of parameters, as below:

| Parameter | Type    | Default Value | Explanation             | Is Required | Supports Markdown in its value |
|-----------|---------|--------------|-------------------------|-------------|--------------------------------|
| `title`   | string  |        | Title of the admonition | No          | Yes                            |

Example of all possible admonition blocks:
```
``admonition
Admonition Block
``
``caution
Caution Block
``
``topic
Topic Block
``
``warning
Warning Block
``
``danger
Danger Block
``
``attention
Attention Block
``
``error
Error Block
``
``hint
Hint Block
``
``tip
Tip Block
``
``important
Important Block
``
``note
Note Block
``
``seealso
See Also Block
``
``todo
ToDo Block
``
```

``caution
Caution Block
``
``warning
Warning Block
``
``danger
Danger Block
``
``attention
Attention Block
``
``error
Error Block
``
``hint
Hint Block
``
``tip
Tip Block
``
``important
Important Block
``
``note
Note Block
``
``seealso
See Also Block
``
``admonition
Admonition Block
``
``topic
Topic Block
``
``todo
ToDo Block
``
