# 30-Days-of-Typescript


## Day 01: Introduction to TypeScript

### 📌 What is TypeScript?
TypeScript is a **typed superset of JavaScript** developed by Microsoft. It adds **static type definitions**, **modern JavaScript features**, and helps catch errors early through type checking.

### 🚀 Why Use TypeScript?
- **Optional static typing**
- **Better tooling** (IntelliSense, autocomplete)
- **Improved refactoring**
- **Early error detection**
- **Great support for modern JS (ES6+)**

### 🛠️ Installation

#### Globally (using npm):
```bash
npm install -g typescript
```

#### Locally to a project:
```bash
npm install --save-dev typescript
```

### 🔧 Initialize TypeScript in a Project
```bash
tsc --init
```
This creates a `tsconfig.json` file.

---

## 🧪 Examples

### Example 1: JavaScript vs TypeScript
#### JavaScript
```js
function add(a, b) {
  return a + b;
}
add("1", 2); // No error, but wrong result
```

#### TypeScript
```ts
function add(a: number, b: number): number {
  return a + b;
}
add("1", 2); // ❌ Error: Argument of type 'string' is not assignable to parameter of type 'number'.
```

### Example 2: Basic Types
```ts
let username: string = "John";
let age: number = 30;
let isLoggedIn: boolean = true;
```

### Example 3: Type Inference
```ts
let message = "Hello, TypeScript!"; // Inferred as string
document.body.innerText = message;
```

---

## 📝 Exercises
1. Install TypeScript globally and create a sample `.ts` file.
2. Use basic types: `string`, `number`, `boolean`.
3. Try inferring types and manually annotating them.
4. Compare a function in JavaScript and TypeScript.
5. Practice compiling `.ts` files using the TypeScript compiler (`tsc`).

---

## 📚 Resources
- [TypeScript Official Docs](https://www.typescriptlang.org/docs/)
- [Playground](https://www.typescriptlang.org/play)

---

✅ You're all set with TypeScript basics! Move to **Day 2** to learn about **Types & Type Annotations**.

---

## Day 02: Types & Type Annotations

### 📌 What are Type Annotations?
Type annotations explicitly tell TypeScript what type a variable, function, or parameter should be.

```ts
let name: string = "Alice";
let score: number = 99;
```

### ✍️ Basic Types in TypeScript:
- `string`
- `number`
- `boolean`
- `any`
- `unknown`
- `null` & `undefined`
- `void`
- `never`

---

## 🧪 Examples

### Example 1: Function with annotated parameters
```ts
function greet(name: string): string {
  return `Hello, ${name}!`;
}
```

### Example 2: Union Types
```ts
let id: number | string;
id = 101;
id = "abc123";
```

### Example 3: `any` vs `unknown`
```ts
let anything: any = 5;
anything = "text";

let notSure: unknown = "hello";
if (typeof notSure === "string") {
  console.log(notSure.toUpperCase());
}
```

### Example 4: Special Types
```ts
function logMessage(): void {
  console.log("Logging message...");
}

function throwError(): never {
  throw new Error("Something went wrong!");
}
```

---

## 📝 Exercises
1. Declare variables using all basic types.
2. Write a function with typed parameters and return type.
3. Use `union` types in a function parameter.
4. Try using `any` and then replace it with `unknown`.
5. Write a `never` returning function.

---

## 📚 Resources
- [TypeScript Handbook: Everyday Types](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html)
- [TypeScript Playground](https://www.typescriptlang.org/play)

---

✅ Ready for Day 03? We'll dive into **Functions & Return Types**!

---

## Day 03: Functions & Return Types

### 📌 What You’ll Learn:
- Writing functions with type annotations
- Specifying return types
- Function expressions
- Default & optional parameters

---

## 🧪 Examples

### Example 1: Basic function with return type
```ts
function sum(a: number, b: number): number {
  return a + b;
}
```

### Example 2: Function with optional and default parameters
```ts
function greet(name: string = "Guest"): string {
  return `Hello, ${name}!`;
}

function log(message?: string): void {
  console.log(message || "Default log");
}
```

### Example 3: Arrow function with types
```ts
const multiply = (x: number, y: number): number => x * y;
```

---

## 📝 Exercises
1. Write a function that accepts 2 numbers and returns their product.
2. Add an optional parameter to a function and handle it.
3. Rewrite a JavaScript arrow function into TypeScript with proper types.
4. Create a function that returns void.

---

## 📚 Resources
- [Function Types in TypeScript](https://www.typescriptlang.org/docs/handbook/2/functions.html)

---

✅ Next up — **Day 4: Arrays & Tuples**

---

## Day 04: Arrays & Tuples

### 📌 Why Arrays and Tuples Matter
Arrays allow you to group values, while tuples give you the power of fixed-length arrays with known types for each index.

### 🔹 Typed Arrays
```ts
const numbers: number[] = [1, 2, 3];
const fruits: Array<string> = ["apple", "banana"];
```

### 🔹 Multidimensional Arrays
```ts
const matrix: number[][] = [[1, 2], [3, 4]];
```

### 🔹 Tuples
```ts
let user: [string, number] = ["Alice", 30];
```

### 🔹 Tuple with Optional Values
```ts
let error: [number, string?] = [404];
```

### 🔹 Readonly Tuples
```ts
const point: readonly [number, number] = [10, 20];
```

---

## 📝 Exercises
1. Create a typed array of booleans.
2. Declare a tuple for a book: [title: string, pages: number].
3. Create a 2D number array and log its values.
4. Use a readonly tuple and try to modify it (check error).

---

## 📚 Resources
- [Array Types](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#arrays)
- [Tuples](https://www.typescriptlang.org/docs/handbook/2/objects.html#tuple-types)

---

## Day 05: Objects & Type Aliases

### 📌 What You’ll Learn:
- Defining object shapes
- Using type aliases
- Optional & readonly properties

### 🧱 Object Types
```ts
const user: { name: string; age: number; isAdmin: boolean } = {
  name: "Alice",
  age: 30,
  isAdmin: true
};
```

### 🏷️ Type Aliases
```ts
type User = {
  name: string;
  age: number;
  isAdmin?: boolean; // optional
};

const bob: User = {
  name: "Bob",
  age: 25
};
```

### 🔒 Readonly
```ts
type Point = {
  readonly x: number;
  readonly y: number;
};

const p1: Point = { x: 10, y: 20 };
// p1.x = 30; ❌ Error: Cannot assign to 'x' because it is a read-only property.
```

### 📝 Exercises
1. Create a `Product` type with `name`, `price`, and `inStock`.
2. Define a user object using type alias with optional `isAdmin`.
3. Try using `readonly` properties in a `Location` type.

---

✅ Get ready for **Day 6 — Interfaces**

---

## Day 06: Interfaces

### 📌 What You’ll Learn:
- Declaring interfaces
- Extending interfaces
- Difference between types and interfaces

### 📋 Defining Interfaces
```ts
interface Person {
  name: string;
  age: number;
}

const user: Person = {
  name: "Sarah",
  age: 22
};
```

### ➕ Extending Interfaces
```ts
interface Employee extends Person {
  employeeId: number;
}

const emp: Employee = {
  name: "John",
  age: 30,
  employeeId: 101
};
```

### 🔍 Interfaces vs Type Aliases
| Feature | Interface | Type Alias |
|--------|------------|------------|
| Extendable | ✅ Yes | ✅ Yes (with `&`) |
| Declaration Merging | ✅ Yes | ❌ No |
| Use Cases | Objects | Objects, primitives, unions |

### 📝 Exercises
1. Create an interface `Book` with `title`, `author`, and `isbn`.
2. Extend it with `BorrowedBook` that has `borrowerName` and `dueDate`.
3. Try merging interfaces by redeclaring.

---

✅ Ready for **Day 7 — Enums & Literal Types**

## Day 07: Enums

### 📌 What are Enums?
Enums (short for *enumerations*) allow you to define a set of named constants. They help make your code more readable and maintainable by giving meaningful names to related values.

### 🚀 Why Use Enums?
- Group related constants logically
- Avoid magic numbers or strings
- Provide better auto-completion and type safety

### 🧪 Examples

#### Example 1: Numeric Enum
```ts
enum Direction {
  Up, // 0
  Down, // 1
  Left, // 2
  Right // 3
}

let move: Direction = Direction.Up;
console.log(move); // Output: 0
```

#### Example 2: Custom Numeric Enum
```ts
enum StatusCode {
  Success = 200,
  NotFound = 404,
  ServerError = 500
}

console.log(StatusCode.NotFound); // Output: 404
```

#### Example 3: String Enum
```ts
enum Color {
  Red = "RED",
  Green = "GREEN",
  Blue = "BLUE"
}

let favoriteColor: Color = Color.Green;
console.log(favoriteColor); // Output: GREEN
```

### 📝 Exercises
1. Create an enum for days of the week.
2. Create a function that accepts an enum and returns a message.
3. Compare string vs numeric enums.

---
