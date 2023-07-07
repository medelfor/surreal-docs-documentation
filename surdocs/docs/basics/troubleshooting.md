# Troubleshooting

This page lists the most common problems encountered when using Surreal Docs and explains different support options available to the Surreal Docs users.

### The common problems

``error
title: "Can't open \`surdocs/surreal.json\`"
The problem means that Surreal Docs cannot open the documentation descriptor which should be placed in `surreal.json` file under `surdocs` directory which, in turn should be placed right in your Unreal Engine project root directory.

Most probably it happened because the `init` command wasn't executed. Another probable cause is removal or renaming of either the `surdocs` directory or `surreal.json` file.

You can find more info about the `init` command on the [init page](docs/cli/init "init description") of our [CLI reference](docs/cli "CLI reference").
``

``error
title: "Couldn't find editor binary at \<path>" or "CreateProcess failed: The system cannot find the path specified."
In most cases this problem is caused by the wrong Unreal Engine root specified in the `surreal.json` file. Please check the root in your `surreal.json`. More info on the syntax of `surreal.json` can be found in [surreal.json reference](docs/surreal-json "surreal.json reference").
``

``error
title: "No project file found"
The usual reason for this is trying to run the `init` command from a directory which isn't a Unreal Engine project root. The root directory must contain a `.uproject` file.

You can find more info about the `init` command on the [init page](docs/cli/init "init description").
``

``error
title: "UAT exited with code 6"
The most often reason of this error is a failed build during execution of the
`generate` command. Before starting generation Surreal Docs compiles your Unreal Engine project, so it would be able to run a commandlet. If the  build fails, Surreal Docs cannot continue its work.

Please take a look at the session's logs to find out why the project couldn't be compiled. Also try to compile it from within your IDE of choice.

The problem is unlikely to happen with Blueprint-only projects.
``

``error
title: "Integrity check failed"
Can happen for different reasons. In case you recently installed a new version of Surreal Docs over an old one already presented in the system, please do the following: navigate to `%ProgramFiles%/Medelfor/SurrealDocs` and remove everything presented inside, then install the new version of Surreal Docs again.
``

### The common installation problems

``error
title: Unable to download Html2png
Please check your internet connection and disk space. Disk must have at least 1GB free.
``

``error
title: Unable to extract Html2png
Please check your disk space. Disk must have at least 1GB free.
``

### Logs

You can find your Surreal Docs logs by the following path: `%appdata%/Medelfor/SurrealDocs/logs/`

### Support

If you believe there's something wrong with the tool, please create an
issue in the [Surreal Docs GitHub repository](https://github.com/medelfor/surreal-docs "Surreal Docs GitHub repository").

"Surreal Docs Crypto", "Surreal Docs XL" or "Surreal Docs Crypto
XL" licenses include Priority Customer Care plan. If you or your
organization own one of these licenses please contact us at
[support@medelfor.com](mailto:support@medelfor.com "Support email") with your
license ID and problem description, we will consider the issue a high-priority.

You can browse list of issues already being in work in our YouTrack
[here](https://issues.internal.medelfor.com/youtrack/issues?q=project:%20%7BSurreal%20Docs%7D "Surreal Docs WIP issues").
