# register

This page describes the `register` command, the command used to activate a paid copy of Surreal Docs.

### General description and syntax

`surdocs [global options] register`

Execution of the command will open a browser window inviting to log in into a 
Medelfor account. In order for activation to be successful the logged-in user should
have a valid license that includes "Surreal Docs" product.

After successful activation upon next docs generation all watermarks and
free-version-warnings will disappear. Ability to change project logo and 
company logo will be activated.

Note that during docs generation the machine must have access to the Internet, 
otherwise your copy of the software won't be considered activated even if it was
previously activated.

A paid Surreal Docs license can be acquired in the [Store](https://store.medelfor.com "Medelfor Store").

### Options

###### `-h`, `--help` - show the help

Shows help regarding the command.

### Example

Activate Surreal Docs.

```
surdocs register
```
