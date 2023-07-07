# quota list

This page describes the `quota list` command, the command used to list usage of Surreal Cloud resources constrained by a quota.

### General description and syntax

`surdocs [global options] quota list`

Expects an [access token](docs/cli/global-options#access-tokens "Access tokens") to be presented.  Prints out the list of all limited resources available to the token's owner and the current level of their consumption. 

The following resources can be on quota:

| Name | Description                                             |
|------|---------------------------------------------------------|
| `MAX_ORGANIZATIONS`  | Maximal amount of organizations user can own            |
| `MAX_DOCUMENT_SIZE`  | Maximal size of a single document stored in the Cloud   |
| `MAX_TOTAL_SIZE`   | Maximal total size of all documents stored in the Cloud |

Specific constraint of each resource depends on your Surreal Cloud type and other factors. You can get some insight on what some resource limitations are on the [Surreal Cloud](docs/surreal-cloud#three-versions-of-surreal-cloud "Different types of Surreal Cloud") page.

### Options

###### `-h`, `--help` - show the help

Shows help regarding the command.

### Example

List user's quota.

```
surdocs quota list
```
