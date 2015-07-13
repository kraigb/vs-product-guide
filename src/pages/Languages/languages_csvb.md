<properties
    pageTitle="C# and Visual Basic"
    description="Visual Studio 2015 ships new language features for C#6 and Visual Basic 14."
    slug="languages_csvb"
    order="500"    
    keywords="visual studio, vs2015, vs, visualstudio, languages, C#, VB, visual basic"
/>

## Language Features

New C# and Visual Basic language features help reduce boilerplate and clutter in everyday code, encourage a more declarative style of programming, and bring the two languages even closer together. For example, there are syntactic improvements to type and member declarations and to null checking. Also, local variables can be declared inside expressions, and await can be used in catch and finally blocks. Many of these features are implemented only for one of the two languages in earlier releases, but will be available to both languages in the final release.

- **nameof** expressions are a new form of string literal to provide strings that name a program element. This is arefactoring-safe way of getting the name of a parameter, member, or type as a string.
- **String interpolation** provides a concise way of describing string templates that insert expressions into format strings, making it easier than String.Format.
- **Null-conditional operators** address many of the situations where code tends to drown in null-checking. They let you access members and elements only when the receiver is not-null, providing a null result otherwise. They are especially useful when combined with the null-coalescing operator '??'.
- **Extension Add methods** are observed in collection initializers; we used to only recognize instance methods called Add.
- **Overload resolution** is improved in a few ways so that more things just work the way you'd expect them to. The improvements all relate to "“betterness" – the way the compiler decides which of two overloads is better for a given argument.
- **Exception filters** are a CLR capability that has been exposed in Visual Basic and F#, and is available now in C#.
- **Await in catch and finally blocks** is allowed, obviating some very tricky workarounds.
- **Auto-property initializers** are enabled, and are similar to initializers on fields.
- **Getter-only auto-properties** allow you to omit a setter on an auto-property.
- **Expression-bodied function members** allow methods, properties, and other kinds of function members to have bodies that are expressions instead of statement blocks, just like with lambda expressions.
- **using static** is a kind of **using** clause that lets you import static members of types directly into scope, so you can call for example WriteLine() or Sqrt() without prefixing with the class name.


## Additional C# Features

- **Parameterless constructors** in structs are allowed.
- **Index initializers** extend object initializers so that you can now initialize not only members but also indices of the newly created object.

_For complete details with code samples for C#, see [New Features in C# 6](http://blogs.msdn.com/b/csharpfaq/archive/2014/11/20/new-features-in-c-6.aspx)._


## Additional Visual Basic Features

- **?. operator:** an easier way to check whether something is null before dotting into it. It's useful because production-quality code is typically littered with hundreds of null-checks all over the place, and ?. will make them all easier to read.
- **Multiline Strings:** Previously, you had to use cumbersome workarounds to get multiline strings in Visual Basic. VB14 supports multiline strings literals directly.
- **Comments:** are handled better in statements that split over multiple lines. This is particularly nice for LINQ expressions. 

_For complete details with code samples for Visual Basic, see [New Language Features in Visual Basic 14](http://blogs.msdn.com/b/vbteam/archive/2014/12/09/new-language-features-in-visual-basic-14.aspx) as well as [New Language Features in VB 14](https://roslyn.codeplex.com/discussions/571884)._
