**Tags:** #_Todo
#ToTag #ToLink 
- - -
# TypeScript Overview
TypeScript is a superset of JavaScript that adds strong typing. It transpiles to JavaScript using the `tsc` command.
## Installation
Project-specific:
```bash
npm install typescript
npx tsc        # Run compiler 
```
System-wide installation also possible.
Note: Even if transpilation fails, it still outputs JavaScript. TypeScript doesn't run directly in browsers.
# 1. Basic Types and Variables
## Variable Declarations
- `const`: Immutable
- `let`: Block-scoped
- `var`: Function-scoped
- Null assignment implications
- `!`: Non-null assertion operator
## Variable Types
- Primitive Types: `number`, `string`, `boolean`, `null`, `undefined`, `void`, `symbol`, `bigint`
- Difference between `Number` (object) vs `number` (primitive)
- Arrays: Two syntaxes: `type[]` or `Array<type>`
- Objects: Can define structure inline or with interfaces
- Type Inference: TypeScript automatically detects types
- Union Types: `type1 | type2`
- Type Aliases: `type CustomType = existing types`
# 2. Functions
Three declaration types:
```typescript
function name(params){}
const name = function(params){}
const name = (params) => {}
```
- Type inference for return values
- Optional parameters: `param?`
- Default parameters: `param = value`
- Rest parameters: `...args`
- Generic functions: `<T>`
# 3. Classes
```typescript
class Example {
    constructor() {}
    method() {}
}
```
- Access modifiers: `public`, `private`, `protected`
- `private` vs `#` private fields
- `this` keyword refers to class instance
- Inheritance using `extends`
- `super` for parent class access
- Static members
- Getters/setters
# 4. Interfaces
```typescript
interface Example {
    property: type;
}
```
- Alternative to generics
- Force class structure
- `implements` keyword
- Object structure definition
# 5. Advanced Features
- Destructuring: `let {prop1: newName, prop2} = object`
- String interpolation: `${variable}`
- Array methods:
  - `filter()`
  - `find()`
  - `reduce()`
  - `concat()`
  - `join()`
- Equality operators: `=` (assignment), `==` (loose equality), `===` (strict equality)
- Decorators (experimental feature)
# 6. Compiler Configuration
tsconfig.json options:
```json
{
    "compilerOptions": {
        "outDir": "./dist",
        "sourceMap": true,
        "experimentalDecorators": true,
        "strict": true
    }
}
```

TypeScript errors don't prevent compilation to JavaScript but provide development-time type checking.
# 7. Module System
- `export` to make available
- `import` to use
- Member access using dot notation: `class.member`
- - - 
## ***Sources:***
- [Typescript Oficial site](https://www.typescriptlang.org/docs/)