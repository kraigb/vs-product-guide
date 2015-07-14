<properties
    pageTitle="F# 4.0"
    description="F# 4.0 was built completely in the open by F# community developers, in partnership with the Visual F# team at Microsoft.  It represents the work of 38 contributors, over 75% of whom have no Microsoft affiliation. It includes major enhancements across the language, runtime, and IDE experience."
    slug="languages_fsharp"
    order="520"    
    keywords="visual studio, vs2015, vs, visualstudio, languages, F#"
/>

## Language

- **Implicit quotation of method arguments:** Method arguments of type FSharp.Quotations.Expr<_> can be marked with the [<ReflectedDefinition>] attribute, enabling automatic quotation of the corresponding argument expressions at callsites. This enables seamless syntax for various meta-programming scenarios that depend on access to the underlying AST, e.g. LINQ-style transformations or R-style plotting routines that label chart axes automatically.
- **Extended preprocessor grammar:** F# preprocessor directives support the standard logical operators &&, ||, and !, as well as grouping via (  ). This leads to significantly cleaner conditionally-compiled code, and the ability to easily express conditions that previously required code duplication.
- **Rational exponents in units of measure:** F# units of measure were previously limited to support only integer exponents. With F# 4.0, units can be raised to arbitrary rational powers. Certain physical sciences, such as electrical engineering, frequently use such fractional powers for units.
- **Inheritance from types with multiple generic interface instantiations:** Earlier versions of F# disallowed types from implementing the same .NET interface at multiple generic instantiations, or even inheriting from C# types that did so. This was due to complexities in how multiple generic instantiations would interact with F# type inference. Although the former restriction still applies, the restriction on inheritance is lifted in F# 4.0, which significantly simplifies interoperability with certain C#-based APIs.
- **Non-nullable provided types:** Provided types which report the attribute [<AllowNullLiteral( false )>], are be treated as non-nullable in the same way as standard F# types. This brings stronger safety guarantees to provided types and aligns them more closely with patterns and idioms from the rest of the language.
- **Multiple properties in [<StructuredFormatDisplay>]:** F# types specifying custom %A string formatting via the [<StructuredFormatDisplay>] attribute were previously limited to interpolating just a single property value. StructuredFormatDisplay supports an arbitrary number of interpolated properties, as well as escaped { } brackets.
- **Extension properties in object initializers:** F# supports not just extension methods, but extension properties, as well.  Settable extension properties can be assigned directly within F# object initializers, allowing for one-step initialization of data.
- **Leading 'Microsoft' prefix optional:** Although Microsoft publishes the Visual F# Tools for use in Visual Studio on Windows, the F# language itself is supported cross-platform by a variety of companies, and its primary advocate is the independent, community-governed F# Software Foundation. To keep F# code itself vendor- and platform-neutral, the leading "Microsoft." can be optionally omitted when referring to namespaces, modules, and types from the FSharp.Core runtime.
- **Constructors as first-class functions:** Class names can be used as first-class function values, representing the constructor(s) for that class.
- **Unification of 'mutable' and 'ref':** The 'mutable' syntax can be used everywhere, and captured values will be automatically converted to heap-based 'ref' values by the compiler when needed. An optional warning issues notifications when this occurs.
- **Static parameters to provided methods:** Individual methods provided by type providers can specify static parameters.
- **Non-nullable provided types:** Provided types can be specified as non-nullable via the standard [<AllowNullLiteral(false)>].
- **Simplified use of units of measure values with 'printf'-style functions:** Unitized numerical values work seamlessly with numerical printf format specifiers, without requiring the units to be removed.
- **Support for high-dimensional .NET arrays:** .NET arrays of rank 5 or greater can be consumed by F# code.
- **Multiple properties in 'StructuredFormatDisplayAttribute':** %A formatting specified through [<StructuredFormatDisplay>] can include multiple properties.



## Runtime

- **Optimized non-structural comparison operators:** The FSharp.Core.Operators.NonStructuralComparison module can be opened, replacing the default F# structural comparison operators with more efficient non-structural operators. This can provide significant performance gains when processing types with custom operator implementations, particularly value types.
- **Normalization of Array, List, and Seq modules:** The set of collection-processing functions is consistent across the Array, List, and Seq modules (barring APIs not applicable to certain types), with dedicated, optimized implementations for each type.
- **Optimized structural hashing:** Significant optimizations improve the performance of generic hash comparison for primitive types, leading to performance gains by APIs such as 'distinct' and 'groupBy'.
- **Async extensions to WebClient:** Two new extension methods for System.Net.WebClient, WebClient.AsyncDownloadFile and WebClient.AsyncDownloadData (in the  FSharp.Control.WebExtensions module) allow for easier usage of WebClient within F# async workflows.
 **Slicing syntax on F# lists:** F# lists support slicing syntax for obtaining sub-lists.
- **Interop APIs for Option:** A handful of new convenience APIs have been added for converting between possibly-null .NET types and F# option types.
- **Quotation active pattern for Decimal values:** There is a dedicated active pattern in the runtime for deconstructing F# quotations which contain constant System.Decimal values.  This previously required some awkward matching on compiler-internal function names.
- **Better Async stack traces:** Exceptions occuring in F# async computations carry more user-friendly stack traces, making it easier to diagnose issues.
- **Interop APIs for Option:** APIs in the Option module allow for converting to and from null objects and System.Nullable values.


## IDE and Tools Experience

- **Script debugging:** the Visual Studio debugger can debug F# scripts directly. The debugger can be attached to the current F# Interactive session.
- **Assembly metadata in project templates:** All F# project templates contain a file AssemblyInfo.fs that contains common assembly-level metadata attributes.
- **Integrated up-to-date check:** F# projects correctly report their "up-to-date" status when building in Visual Studio.
- **Modified GC settings on the compiler for better performance:** The F# compiler (fsc.exe) uses GCLatencyMode.Batch, which gives a noticeable improvement in overall throughput.
- **Intellisense in object initializers:** Object initializer expressions support IntelliSense completion of settable properties, using Ctrl+Space.
- **IntelliSense completion for named parameters:** Method and constructor calls support IntelliSense auto-completion of named parameters, using Ctrl+Space.
- **Bug fixes around folder support:** Visual F# tools do not directly support folders in projects, but a number of project system bugs have been fixed improve the folder support added by the Visual F# Power Tools extension.
- **Improved startup time for FSI:** Adjustments to the AppDomain loading behavior has improved startup time over F# 3.1.2.
- **New hotkeys for FSI:** From within Visual Studio, hotkeys are assigned for the "Reset" (Ctrl+Alt+R) and "Clear All" (Ctrl+Alt+C) actions of F# Interactive. These mappings were chosen to match those found in other F# IDEs.
