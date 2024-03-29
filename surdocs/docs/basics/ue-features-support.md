# Support of the Unreal Engine features
            
The table below is the summary of what UE features Surreal Docs does and doesn't support.

|                                                                                                                                                                                            | UE 4.27 | UE 5.0 | UE 5.1      | UE 5.2      |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------|--------|-------------|-------------|
| Blueprint Classes                                                                                                                                                                          | Yes     | Yes    | Yes         | Yes         |
| Blueprint Structs                                                                                                                                                                          | Yes     | Yes    | Yes         | Yes         |
| Blueprint Interfaces                                                                                                                                                                       | Yes     | Yes    | Yes         | Yes         |
| Blueprint Enums                                                                                                                                                                            | Yes     | Yes    | Yes         | Yes         |
| Blueprint Properties                                                                                                                                                                       | Yes     | Yes    | Yes         | Yes         |
| Blueprint Functions                                                                                                                                                                        | Yes     | Yes    | Yes         | Yes         |
| Blueprint-only projects                                                                                                                                                                    | Yes     | Yes    | Yes         | Yes         |
| `UCLASS` macro                                                                                                                                                                             | Yes     | Yes    | Yes         | Yes         |
| `USTRUCT` macro                                                                                                                                                                            | Yes     | Yes    | Yes         | Yes         |
| `UFUNCTION` macro before a function                                                                                                                                                        | Yes     | Yes    | Yes         | Yes         |
| `UFUNCTION` macro before a delegate                                                                                                                                                        | Yes     | Yes    | Yes         | Yes         |
| `UDELEGATE` macro                                                                                                                                                                          | Yes     | Yes    | Yes         | Yes         |
| `UPROPERTY` macro                                                                                                                                                                          | Yes     | Yes    | Yes         | Yes         |
| `UPARAM` macro                                                                                                                                                                             | Yes     | Yes    | Yes         | Yes         |
| `UMETA` macro                                                                                                                                                                              | Yes     | Yes    | Yes         | Yes         |
| `UINTERFACE` macro                                                                                                                                                                         | Yes     | Yes    | Yes         | Yes         |
| `FORCEINLINE` macro                                                                                                                                                                        | Yes     | Yes    | Yes         | Yes         |
| `UE_DEPRECATED` macro                                                                                                                                                                      | Yes     | Yes    | Yes         | Yes         |
| `PURE_VIRTUAL` macro                                                                                                                                                                       | Yes     | Yes    | Yes         | Yes         |
| `DECLARE_*_DELEGATE_*` macros family                                                                                                                                                       | Yes     | Yes    | Yes         | Yes         |
| `DECLARE_EVENT_*` macros family                                                                                                                                                            | Yes     | Yes    | Yes         | Yes         |
| `DECLARE_DERIVED_EVENT` macro                                                                                                                                                              | Yes     | Yes    | Yes         | Yes         |
| `*_API` macros                                                                                                                                                                             | Yes     | Yes    | Yes         | Yes         |
| Documenting native modules (via `.Build.cs` files)                                                                                                                                         | Yes     | Yes    | Yes         | Yes         |
| Generation of docs for UE-plugins                                                                                                                                                          | Yes     | Yes    | Yes         | Yes         |
| Generation of docs for content-only UE-plugins                                                                                                                                             | Yes     | Yes    | Yes         | Yes         |
| Blueprint Namespaces                                                                                                                                                                       | Yes     | Yes    | Partial [1] | Partial [1] |
| Verse support                                                                                                                                                                              | No      | No     | No          | No          |
| Animation Blueprints ([SD-1048](https://issues.internal.medelfor.com/youtrack/issue/SD-1048/Add-support-for-animation-BPs "Animation BPs"))                                                | No      | No     | No          | No          |
| Gameplay Ability System macros ([SD-1034](https://issues.internal.medelfor.com/youtrack/issue/SD-1034/Add-support-for-GAS-macros-e.g.-GAMEPLAYATTRIBUTE "Gameplay Ability System macros")) | No      | No     | No          | No          |
| Latent functions ([SD-1084](https://issues.internal.medelfor.com/youtrack/issue/SD-1084/Add-support-of-latent-functions "Latent functions"))                                               | No      | No     | No          | No          |
| Slate macros ([SD-1037](https://issues.internal.medelfor.com/youtrack/issue/SD-1037/Add-support-for-Slate-macros "Slate macros"))                                                          | No      | No     | No          | No          |
| Blueprint macros ([SD-1047](https://issues.internal.medelfor.com/youtrack/issue/SD-1047/Add-support-for-graph-macros-macros-library "Blueprint macros"))                                   | No      | No     | No          | No          |
                       
If your project requires one of the unsupported features (including the ones that are not listed here), please let us know by sending an email to [support@medelfor.com](mailto:support@medelfor.com "Support email"), we'll do our best to speed up the implementation process.

***

[1] There's no additional support for the updated Blueprint namespaces ([SD-1167](https://issues.internal.medelfor.com/youtrack/issue/SD-1167/Support-for-updated-BP-namespaces-5.1 "SD-1167"))
