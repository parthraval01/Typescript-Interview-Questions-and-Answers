# Typescript Interview Questions and Answers

> Typescript Interviews – Top Questions &amp; Answers for Web Developers


---

## Basic Level Questions

### 1. What is TypeScript?
TypeScript is a **superset of JavaScript** that adds **static typing**. It helps catch errors during development instead of runtime.

---

### 2. Why use TypeScript over JavaScript?
- Detects bugs early with type checking.  
- Improves code readability and maintainability.  
- Supports modern JS features (compiled to older JS versions).  
- Great tooling (IntelliSense, autocompletion).

---

### 3. How do you install TypeScript?
```bash
npm install -g typescript
````

Then compile a file:

```bash
tsc file.ts
```

---

### 4. What is the file extension of TypeScript files?

`.ts` for regular files and `.tsx` for files using JSX (React).

---

### 5. What is the role of the TypeScript compiler?

The TypeScript compiler (`tsc`) **translates TypeScript to JavaScript**, ensuring type safety and compatibility.

---

### 6. What is a type in TypeScript?

A type defines **the shape of data** — what kind of value (string, number, boolean, etc.) can be assigned to a variable.

---

### 7. What are the primitive data types in TypeScript?

`string`, `number`, `boolean`, `null`, `undefined`, `bigint`, and `symbol`.

---

### 8. What is type inference?

TypeScript automatically infers the type when you declare and assign a variable:

```ts
let count = 10; // inferred as number
```

---

### 9. How do you explicitly define a type?

```ts
let username: string = "John";
let age: number = 25;
```

---

### 10. What is the difference between `any` and `unknown`?

* `any` disables all type checking.
* `unknown` is safer — you must check the type before using it.

```ts
let value: unknown = "Hi";
if (typeof value === "string") console.log(value.toUpperCase());
```

---

## Intermediate Level Questions

### 11. What are interfaces in TypeScript?

Interfaces define the **structure or shape** of an object.

```ts
interface User {
  name: string;
  age: number;
}
```

---

### 12. How are interfaces different from types?

* `interface` is extendable and used for object shapes.
* `type` can represent unions, primitives, and more.

```ts
type Status = "active" | "inactive";
```

---

### 13. What is a union type?

A variable can hold **multiple types**.

```ts
let result: string | number;
```

---

### 14. What is an intersection type?

It **combines multiple types** into one.

```ts
type A = { name: string };
type B = { age: number };
type C = A & B; // { name, age }
```

---

### 15. What are generics?

Generics make components **reusable** with different data types.

```ts
function identity<T>(value: T): T {
  return value;
}
```

---

### 16. What is type aliasing?

It gives a **name to a type**.

```ts
type ID = string | number;
```

---

### 17. What is an enum?

Enums are **named constants**.

```ts
enum Role { Admin, User, Guest }
```

---

### 18. What are tuples?

Tuples are **fixed-length arrays** with defined types.

```ts
let person: [string, number] = ["John", 30];
```

---

### 19. What is `readonly` in TypeScript?

It makes a property **immutable**.

```ts
interface User {
  readonly id: number;
  name: string;
}
```

---

### 20. How do you define optional properties?

Use `?` after the property name.

```ts
interface User {
  name: string;
  age?: number;
}
```

---

### 21. What is type assertion?

It tells the compiler “trust me, I know the type.”

```ts
let input = document.getElementById("id") as HTMLInputElement;
```

---

### 22. Difference between `interface` and `class`?

* `interface` defines a structure.
* `class` defines a blueprint with behavior (methods).

---

### 23. What is `never` type?

Used for functions that **never return**, like errors or infinite loops.

```ts
function throwError(): never {
  throw new Error("Error!");
}
```

---

### 24. What is `void` type?

Represents functions that **don’t return** anything.

```ts
function greet(): void {
  console.log("Hello");
}
```

---

### 25. What are type guards?

They **narrow down types** at runtime.

```ts
function print(val: string | number) {
  if (typeof val === "string") console.log(val.toUpperCase());
}
```

---

### 26. What is a module in TypeScript?

Modules are **files** that export or import code to keep it organized.

```ts
export const a = 10;
import { a } from "./file";
```

---

### 27. What are namespaces?

Namespaces group code logically in the same file (used less now).

```ts
namespace Utils {
  export function log(msg: string) {
    console.log(msg);
  }
}
```

---

### 28. What is `tsconfig.json`?

The configuration file for the TypeScript compiler — defines rules, target versions, etc.

---

### 29. What are decorators?

Decorators are **functions that modify classes or methods** (used in Angular).

```ts
function Logger(constructor: Function) {
  console.log("Logging...");
}
@Logger
class User {}
```

---

### 30. What is `declare` keyword used for?

Used to **declare variables or modules** that exist elsewhere (e.g., JS libraries).

```ts
declare let $: any;
```

---

### 31. What is a mapped type?

Used to **create new types** based on existing ones.

```ts
type ReadonlyUser = {
  readonly [K in keyof User]: User[K];
};
```

---

### 32. What is `Partial` in TypeScript?

Makes all properties optional.

```ts
type PartialUser = Partial<User>;
```

---

### 33. What is `Pick`?

Selects specific properties from a type.

```ts
type NameOnly = Pick<User, "name">;
```

---

### 34. What is `Omit`?

Removes properties from a type.

```ts
type UserWithoutAge = Omit<User, "age">;
```

---

### 35. What is `Record` type?

Creates a type with specific keys and values.

```ts
type Roles = Record<string, boolean>;
```

---

### 36. What is `keyof` operator?

Gets all property names of a type.

```ts
type Keys = keyof User; // "name" | "age"
```

---

### 37. What is `typeof` used for in TypeScript?

Gets the **type of a variable or function**.

```ts
const user = { name: "Tom" };
type UserType = typeof user;
```

---

### 38. What are index signatures?

Used when you don’t know property names.

```ts
interface Dictionary {
  [key: string]: string;
}
```

---

### 39. What are utility types?

Pre-built generic helpers like `Partial`, `Pick`, `Omit`, `Record`, `Readonly`, etc.

---

### 40. What is structural typing?

TypeScript checks **structure compatibility**, not exact matches.

```ts
interface Dog { name: string; }
let cat = { name: "Kitty" };
let dog: Dog = cat; // ✅ Works
```

---

## Advanced Level Questions

### 41. What is the difference between `interface` merging and `type` merging?

Interfaces can **merge automatically**, but types cannot.

---

### 42. How does TypeScript support React?

Through `.tsx` files and JSX typing — enhances props, states, and component type safety.

---

### 43. What is `this` parameter in TypeScript?

Used to **type the context** of a function.

```ts
function say(this: Person) {
  console.log(this.name);
}
```

---

### 44. How do you create a type from a function return?

```ts
function createUser() {
  return { name: "Sam", age: 30 };
}
type User = ReturnType<typeof createUser>;
```

---

### 45. What is `in` operator in TypeScript?

Checks if a property exists in an object (also used in mapped types).

---

### 46. What is discriminated union?

Union types with a **common property** for easy narrowing.

```ts
type Shape = { kind: "circle"; radius: number } | { kind: "square"; side: number };
```

---

### 47. How do you enforce immutability?

Use `readonly` or `Readonly<T>`.

---

### 48. How do you handle dynamic object keys?

Use `[key: string]: any;` or generics with `keyof`.

---

### 49. What is a generic constraint?

Limits the allowed types in generics.

```ts
function print<T extends string>(val: T) {
  console.log(val);
}
```

---

### 50. What is difference between `interface` and `abstract class`?

* **Interface** = structure.
* **Abstract class** = structure + shared logic.

---

### 51. What is type narrowing?

The process of refining a union type to a specific one via checks.

---

### 52. What are ambient declarations?

Used for declaring external library types with `.d.ts` files.

---

### 53. What is JSX in TypeScript?

JavaScript XML — used in React to describe UI elements.

---

### 54. What are declaration files (`.d.ts`)?

Files containing **type definitions** for JavaScript libraries.

---

### 55. What is the `--strict` flag?

Enables all strict type checking options for safer code.

---

### 56. What is difference between `const enum` and `enum`?

`const enum` inlines values during compilation, improving performance.

---

### 57. How to make a property type conditional?

```ts
type Conditional<T> = T extends string ? string : number;
```

---

### 58. What is `Exclude` type?

Removes certain types from a union.

```ts
type Result = Exclude<"a" | "b" | "c", "a">; // "b" | "c"
```

---

### 59. What is `Extract`?

Selects certain types from a union.

```ts
type Result = Extract<"a" | "b" | "c", "a">; // "a"
```

---

### 60. What is `NonNullable`?

Removes `null` and `undefined` from a type.

---

### 61. What is `Awaited`?

Unwraps the result of a Promise.

---

### 62. How to define a function type?

```ts
type Add = (a: number, b: number) => number;
```

---

### 63. How do you overload functions in TypeScript?

```ts
function add(a: number, b: number): number;
function add(a: string, b: string): string;
function add(a: any, b: any): any {
  return a + b;
}
```

---

### 64. What is `readonly` array?

```ts
const arr: readonly number[] = [1, 2];
```

---

### 65. How to make a tuple optional?

```ts
type OptionalTuple = [string, number?];
```

---

### 66. What is difference between `==` and `===`?

Same as JS: `==` checks value, `===` checks value + type.

---

### 67. How does TypeScript support async/await?

By compiling down to Promise-based JavaScript code.

---

### 68. What are decorators used for in Angular?

Used for defining metadata (e.g., `@Component`, `@Injectable`).

---

### 69. What are utility functions in TypeScript?

Predefined helper types like `Pick`, `Omit`, `Partial`, etc.

---

### 70. What is type compatibility?

If one type fits the structure of another, they are compatible.

---

### 71. How do you handle JSON data in TypeScript?

Use interfaces or types to define the JSON structure.

---

### 72. What is `as const`?

Makes an object’s properties immutable and literal.

```ts
const config = { mode: "dark" } as const;
```

---

### 73. How to define default generic type?

```ts
function useValue<T = string>(val: T): T {
  return val;
}
```

---

### 74. What is difference between `namespace` and `module`?

* `namespace`: internal module (same file).
* `module`: external (ES6 import/export).

---

### 75. What is declaration merging?

Multiple interface declarations with the same name merge.

---

### 76. What is index access type?

```ts
type UserName = User["name"];
```

---

### 77. What are mixins in TypeScript?

Technique to combine multiple classes together.

---

### 78. How to avoid “undefined” errors?

Enable `strictNullChecks` and handle null values properly.

---

### 79. What is difference between `extends` in interfaces and generics?

* `interface` `extends` → inheritance.
* `generic` `extends` → constraint.

---

### 80. What are conditional types?

Type logic that behaves like if-else.

```ts
type Check<T> = T extends string ? "String" : "Other";
```

---

### 81. What is the role of `infer` keyword?

Used to **extract types** within conditional types.

```ts
type Return<T> = T extends (...args: any) => infer R ? R : never;
```

---

### 82. What is the difference between `interface` and `type` in generics?

Interfaces can’t handle unions easily, but types can.

---

### 83. What is the `unknown` type used for?

A safer version of `any` that forces type checking before use.

---

### 84. What is the difference between static and instance members?

* Static = belongs to the class.
* Instance = belongs to the object.

---

### 85. How to ensure immutability in arrays?

Use `readonly` or freeze the array.

---

### 86. How to define custom types for APIs?

Create interfaces representing API response structure.

---

### 87. How do you use TypeScript with Node.js?

Use `ts-node` or compile `.ts` files to `.js` before running.

---

### 88. What are generics in React components?

They define reusable prop types for components.

---

### 89. What is “strict mode” in TypeScript?

Collection of type-safety features (`noImplicitAny`, `strictNullChecks`, etc.)

---

### 90. How does TypeScript handle backward compatibility?

It compiles to older JavaScript versions based on `target` in `tsconfig`.

---

### 91. How to make class members private or protected?

```ts
class User {
  private id: number;
  protected name: string;
}
```

---

### 92. What is the `public` modifier?

Public members are accessible anywhere.

---

### 93. How to implement interfaces in classes?

```ts
interface Person { name: string; }
class User implements Person {
  constructor(public name: string) {}
}
```

---

### 94. What are ambient namespaces?

Namespaces declared using `declare namespace` for external libraries.

---

### 95. What is the `satisfies` operator?

Ensures an object matches a specific type but keeps literal inference.

```ts
const user = { name: "Tom" } satisfies User;
```

---

### 96. What is difference between `object` and `{}` types?

* `object`: any non-primitive.
* `{}`: literally any value except `null`/`undefined`.

---

### 97. What is module augmentation?

Extending an existing module with additional features.

---

### 98. How to handle third-party libraries without types?

Install `@types/library` or declare manually.

---

### 99. How to use `typeof` for function types?

```ts
function greet(name: string) {}
type GreetType = typeof greet;
```

---

### 100. Why should teams adopt TypeScript?

    Fewer runtime bugs
    Predictable and readable code
    Better tooling
    Easier refactoring
    Ideal for large-scale applications

---
