# Tags reference

This pages describes what documentation tags are available for use in the documentation comments of C++ entities and the tooltips and descriptions of Blueprint ones.

### Common structure of a documentation piece

A usual comment with documentation for a C++ entity may look like the following. As the general rule of thumb the documenting comment should precede any U-macro.
```
/**
 * @brief Brief description
 *
 * Main description,
 * several lines
 *
 * @param Param1 Description
 * @return Return value description
 * @see Some reference
 */
UCLASS(BlueprintEntity)
class K1_API SuperWeapon : public UObject {
...
```

When commenting Blueprints main rules are the same, but comment markers are dropped:
```
@brief Brief description

Main description,
several lines

@param Param1 Description
@return Return value description
@see Some reference
```

``note
In the resulting documentation a Blueprint-entity that was defined in C++ will have the documentation provided in code for its C++ entity, but with all references to C++ entities replaced on the references to the corresponding Blueprint-entities if applicable. 

For instance if the C++ comment of a `UCLASS` contains a reference to one of its Blueprint-callable `UFUNCTION`s then in the description of this class in the Blueprint API reference, the reference to this function won't lead to the function in the C++ API reference but instead will lead to the corresponding function in the Blueprint reference. However in C++ reference, the reference will lead to the C++ function.

This way Surreal Docs enables user to provide two partially different documentations, with each one being adapted to its context but both being made out of the same text.
``

### What can be documented?

Basically any C++-defined entity (reflection-exposed or vanilla), including classes, structures, enumerations, interfaces, delegates and events, enumeration elements, functions, methods, variables and fields. Event the module classes located in `.Build.cs` can be documented and their documentation will be shown as the documentation of the respective modules.

Speaking about Blueprints, anything that have a "Description" or a "Tooltip" (sometimes they are called "Name") field can be documented.

You can find more info about documentable Unreal Engine features on the ["Support of the Unreal Engine features"](docs/ue-features-support "Support of the Unreal Engine features") page.


### General tags

List of general-purpose tags. There are no required tags, however it's recommended that at least the main description should be provided for each entity.

Required parameters of tags are embraced in angle brackets, e.g.: `<name>`, the optional ones in square brackets, as such: `[description]`.

#### Main description

Main description is a positional part of a documentation piece, and should be separated from the rest of the piece by one blank line on the top and the bottom. Can span several lines.

Example:
```
@brief Short description

Main description,
very long

@return Return description
```

#### @brief

Syntax: `@brief [description]`, must be placed on a separate line

Brief description of an entity which ends with the end of line. It's recommended to keep it concise and to the point.

It's recommended to always provide a `@brief` description.

Example of a `@brief`:
```
@brief Brief description until the end of line

Here goes the main description, brief
has already ended.
```

#### @return

Syntax: `@return [description]`, must be placed on a separate line

Describes the return value of a method or function. Can span several lines.

It's recommended to always provide a `@return` description if method or function returns a value.

Example of a `@return`:
```
Blows a jetpack.

@return `true` if the jetpack was successfuly blown, `false` otherwise
```

#### @param
Syntax: `@param <name> [description]`, must be placed on a separate line

Gives description `[description]` to a parameter `<name>`. If necessary `<name>` can be surrounded with double quotes. It can be useful in case of a Blueprint parameter with a space in its name. Description goes until the end of line.

It's recommended to always provide a `@param` for each parameter.

Example of a `@param`:
```
Launches the rocket.

@param "Rocket Destination" The destination to launch the rocket to
```

#### @see
Syntax: `@see <reference>`, must be placed on a separate line

Provides a standalone reference to a related entity. The entity is determined by the `<reference>` which can be the name of the referenced entity, qualified or not or a path to it. `<reference>` can be enclosed in double quotes if it contains spaces.

If there's need to provide several `@see` elements, they should be placed each on a separate line.

For the allowed syntax of `<reference>` and mechanism of referencing, please refer to the [@ref](#@ref "@ref tag").

It's recommended to provide a few `@see` elements to the entities related to the one being described, so the reader would have more context.

Example of a `@see`:
```
Does something

@return Some description
@see Function1()
@see Enum::Element
```

#### @since
Syntax: `@since <version>`, must be placed on a separate line

States the version the entity being described was introduced in.

It's recommended to always provide a `@since` if the entity wasn't introduced in the initial version of the software.

#### @deprecated
Syntax: `@deprecated [description]`, must be placed on a separate line

Marks entity as deprecated and provides an optional description. It's recommended to always provide short reason of the deprecation and a reference to the new entity that should be used instead of the deprecated one.

C++-entities can also be deprecated with `UE_DEPRECATED(Version, Description)` macro, `_DEPRECATED` name-postfix, `UDEPRECATED_` or `ADEPRECATED_` classname-prefixes, with `DeprecatedMessage` and `DeprecatedVersion` macro specifiers.

#### @ref
Syntax: `@ref <reference> [text]`, can be inlined

Provides an inline reference to a related entity. The entity is determined by the `<reference>` which can be the name of the referenced entity, qualified or not or a path to it. `<reference>` can be enclosed in double quotes if it contains spaces. If `[text]` is provided in the resulting documentation, the link to the referenced entity will be shown as "text" and not as "reference". `@ref` can be used inside descriptions used by other tags and inside the main description.

The reference can be:
 - a simple name e.g. `Function`;
 - a qualified name (e.g. with a namespace or class name preceding the entity name) e.g. `Class::Property` or `std::cout`;
 - can end with parentheses if the referenced entity is a function or method e.g. `DoSomething()`;
 - can be provided in the UE-object format, e.g. `/Script/Module.Class` or `/Game/Package.Class:Function`.

The resolve will be executed in the most local scope first, i.e. the entity will be searched across the parameters (if `@ref` is found in a documentation piece of a function) or enumeration elements (if `@ref` is found in a documentation piece of an enumeration). If failed the scope will be widened, e.g. to the containing class, interface or structure, then to the header file (if `@ref` is in C++ context), to the containing module and finally, to the whole project.

Note that C++ entities and Blueprint-entities can freely cross-reference each other.

If the reference couldn't be resolved or is ambiguous, in the resulting documentation it will be replaced by simple text, no link will be provided. 

It's recommended to always use @ref when referencing another entity.

Example of a `@ref`:
```
If one would want to reference something mid-text 
they would like to know that they can easily 
do it with @ref Class::Something "something cool" syntax.
```
