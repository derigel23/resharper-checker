ReSharper.Checker MSIL weaver
-----------------------------

Fody/Mono.Cecil-based MSIL weaver to materialize ReSharper annotations like
`[NotNull]` into runtime arguments/return values checks to verify nullness
contracts in you code dynamically in addition to ReSharper static analysis.

#### Download

Project is currently under development.

Future releases will be available at nuget.org feed.

#### Features

* Emit checks for `[NotNull]` parameters at methods/constructors/accessors enter
* Emit checks for `[NotNull]` return values and `out`-parameters valies at exit
* Supports checking for null pointers, `ref`-parameters and values of generic types
* Resolves `[NotNull]` annotations from overriden/implemented methods in hierarchy
* Applies `[NotNull]` annotations from property declarations to accessor bodies
* Produces `throw new ArgumentNullException("param")` in cases of violations
* Very lightweight generated code (no more O(1), no `try`-`finally` blocks, etc)
* Installation and MSBuild integration just by referencing NuGet package
* No extra binary dependencies required

#### Future work

* Support for `[NotNull]` on fields (after init or per access?)
* Support for usage-side checks emit
* Support for `[NotNull]` in delegate declarations
* Support for iterator/`async` methods in C#?
* Provide control for checks emit scope (public surface only/whole assembly)
* Provide control for checks code (to replace `throw` with logging, for example)

#### Feedback

Feel free to post any issues or your ideas here, or contact me directly: *alexander.shvedov[at]jetbrains.com*