<properties
    pageTitle="TypeScript"
    description="TypeScript 1.4 and TypeScript 1.5 (Beta) continue to build new features to work with more JavaScript patterns, create richer typings, and use new EcmaScript 6 features."
    slug="languages_typescript"
    order="530"    
    keywords="visual studio, vs2015, vs, visualstudio, languages, TypeScript"
/>

## Type system improvements

- **Union types:** JavaScript functions may take a number of possible argument types, typically supported using function overloads. Uniton types allow you to specify that that a value is one of a number of different types. Union types also allow for better type inference in arrays and other places where you might have multiple kinds of values in a collection.
- **Stricter generics:** with union types able to represent a wide range of type scenarios, Typescript applies more strictness to certain generic calls to catch certain coding errors.
- **Type aliases:** allow defining alternate names for the original types using the **type** keyword.
- **Const enums:** For heavy uses of enums, it's helpful to have an even more restricted form that we know is safe to always inline. This helps with performance, code size, and with working with cases where the enum aliases themselves may not be exported.
- **Type guards:** A common pattern in JavaScript is to use typeof or instanceof to examine the type of an expression at runtime. TypeScript understands these conditions and will change type inference accordingly when used in an if block.


## ECMAScript 6 Support

- **ES6 output mode:** the --target command line option allows 'ES6' as a target.
- **Let/Const:** The ES6 'let' feature is similar to 'var', but it aims to simplify the mental model for the variable’s scope. With 'let', you can scope variables to blocks of code rather than whole functions.
- **Template Strings:** ECMAScript 6 has improved on string interpolation in JavaScript by adding template strings. These special strings can freely mix in expressions, allowing a lighter syntax when pieces of a string depend on associated values.
    
## Decorator metadata (Typescript 1.5)

TypeScript 1.5 includes a metadata API for working with decorators, allowing you to add and read metadata on declarations.


_Further details can be found on the [_TypeScript 1.4_](http://blogs.msdn.com/b/typescript/archive/2015/01/16/announcing-typescript-1-4.aspx) and [_TypeScript 1.5 (Beta)_](http://blogs.msdn.com/b/typescript/archive/2015/04/30/announcing-typescript-1-5-beta.aspx) team blog posts._
