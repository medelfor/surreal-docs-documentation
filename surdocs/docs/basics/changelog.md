# What's new in Surreal Docs 1.1.1

Surreal Docs v1.1.1 brings pay-once-use-forever pricing option, a new command, ability to customize company logo, fixes of numerous bugs and a image rendering optimization.

Here's a detailed list of changes:

- **Pay-once-use-forever** pricing option (check out the [pricing](https://medelfor.com/products/surreal-docs#pricing) page);
- No Surreal Cloud subscription is now required to remove the watermarks;
- [register](docs/cli/register) command, use to activate your copy of the product;
- Ability to customize company logo;
- Up to 100% speed up of image rendering (controlled with [--image-threads](docs/cli/generate));
- Absolute paths in [surreal.json](docs/surreal-json) are no more;
- Other minor improvements.

### Fixed bugs

- Fix of the plugin's type (fixes [#20](https://github.com/medelfor/surreal-docs/issues/20));
- Fix of in-app advertisement erroneously stacking upon each other;
- Properties and functions internally created by UE for timelines are ignored now, not allowing the documentation to be contaminated with "garbage" and speeding up the generation process;
- Functions internally created by UE for latent functions are ignored as well;
- Component event bindings now have a readable as-in-editor title;
- Fix of erroneous crop of "Authority only" and "Cosmetic" functions;

### Contributors

**SirLich** and **PrimaryFantasty** contributed to the quality improvement of Surreal Docs software, in addition to our team. We thank them for their valuable contributions.
