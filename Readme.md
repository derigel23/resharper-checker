ReSharper.Checker MSIL weaver
-----------------------------

Fody/Mono.Cecil-based MSIL weaver to materialize ReSharper annotations like
`[NotNull]` into runtime arguments/return values checks to verify nullness
contracts in you code dynamically in addition to ReSharper static analysis.

#### Download

Project is currently under development.

Future releases will be available at nuget.org feed.

#### Features

* Emit checks for `[NotNull]`-annotated parameters at method/constructor enter
* Emit checks for `[NotNull]`-annotated method return values and `out`-parameters at exit
* Supports checking for null pointers, generic values and `ref`-parameter types
* Supports resolve for `[NotNull]`-annotations from overriden/implemented methods
* By now emits `throw new ArgumentNullException("param")` in cases of violations

#### Future work

* Support for `[NotNull]` on properties
* Support for `[NotNull]` on fields (after init or per access?)
* Support for usage-side checks emit
* Support for `[NotNull]` in delegate declarations
* Support for iterator/`async` methods in C#?
* Provide control for checks emit scope (public surface only/whole assembly)
* Provide control for checks code (to replace `throw` with logging, for example)

#### Feedback

Feel free to post any issues or your ideas here, or contact me directly: *alexander.shvedov[at]jetbrains.com*