# TypescriptDemos
GuideLines

Names

Use PascalCase for type names.
Do not use "I" as a prefix for interface names.
Use PascalCase for enum values.
Use camelCase for function names.
Use camelCase for property names and local variables.
Do not use "_" as a prefix for private properties.
Use whole words in names when possible.
Components

1 file per logical component (e.g. parser, scanner, emitter, checker).
Do not add new files. :)
files with ".generated.*" suffix are auto-generated, do not hand-edit them.
Types

Do not export types/functions unless you need to share it across multiple components.
Do not introduce new types/values to the global namespace.
Shared types should be defined in 'types.ts'.
Within a file, type definitions should come first.
null and undefined

Use undefined. Do not use null.
General Assumptions

Consider objects like Nodes, Symbols, etc. as immutable outside the component that created them. Do not change them.
Consider arrays as immutable by default after creation.
Classes

For consistency, do not use classes in the core compiler pipeline. Use function closures instead.
Flags

More than 2 related Boolean properties on a type should be turned into a flag.
Comments

Use JSDoc style comments for functions, interfaces, enums, and classes.
Strings

Use double quotes for strings.
All strings visible to the user need to be localized (make an entry in diagnosticMessages.json).
Diagnostic Messages

Use a period at the end of a sentence.
Use indefinite articles for indefinite entities.
Definite entities should be named (this is for a variable name, type name, etc..).
When stating a rule, the subject should be in the singular (e.g. "An external module cannot..." instead of "External modules cannot...").
Use present tense.
Diagnostic Message Codes

Diagnostics are categorized into general ranges. If adding a new diagnostic message, use the first integral number greater than the last used number in the appropriate range.

1000 range for syntactic messages
2000 for semantic messages
4000 for declaration emit messages
5000 for compiler options messages
6000 for command line compiler messages
7000 for noImplicitAny messages
General Constructs

For a variety of reasons, we avoid certain constructs, and use some of our own. Among them:

Do not use ECMAScript 5 functions; instead use those found in core.ts.
Do not use for..in statements; instead, use ts.forEach, ts.forEachKey and ts.forEachValue. Be aware of their slightly different semantics.
Try to use ts.forEach, ts.map, and ts.filter instead of loops when it is not strongly inconvenient.
Style

Use arrow functions over anonymous function expressions.
Only surround arrow function parameters when necessary. 
For example, (x) => x + x is wrong but the following are correct:
x => x + x
(x,y) => x + y
<T>(x: T, y: T) => x === y
Always surround loop and conditional bodies with curly braces. Statements on the same line are allowed to omit braces.
Open curly braces always go on the same line as whatever necessitates them.
Parenthesized constructs should have no surrounding whitespace. 
A single space follows commas, colons, and semicolons in those constructs. For example:
for (var i = 0, n = str.length; i < 10; i++) { }
if (x < 10) { }
function f(x: number, y: string): void { }
Use a single declaration per variable statement 
(i.e. use var x = 1; var y = 2; over var x = 1, y = 2;).
else goes on a separate line from the closing curly brace.
Use 4 spaces per indentation.
