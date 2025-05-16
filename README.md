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

## Day 08: Classes & Access Modifiers

### 📌 What You’ll Learn:
- Creating classes in TypeScript
- `public`, `private`, `protected` modifiers
- Constructors & methods

---

### 🧱 Basic Class
```ts
class Person {
  name: string;

  constructor(name: string) {
    this.name = name;
  }

  greet() {
    console.log(`Hello, ${this.name}`);
  }
}

const p = new Person("John");
p.greet();
```

### 🔐 Access Modifiers
```ts
class Employee {
  public name: string;
  private salary: number;

  constructor(name: string, salary: number) {
    this.name = name;
    this.salary = salary;
  }

  getSalary(): number {
    return this.salary;
  }
}
```

### 👥 Inheritance
```ts
class Manager extends Employee {
  constructor(name: string, salary: number) {
    super(name, salary);
  }
}
```

### 📝 Exercises
1. Create a class for a Car with methods like `drive()` and `stop()`.
2. Use `private` fields and access them via methods.
3. Create a class that inherits another class.

✅ Next: **Day 9 - Generics**

---

## Day 09: Generics

### 📌 What You’ll Learn:
- Generic functions
- Generic types
- Constraints with generics

---

### 🔁 What are Generics?
Generics let you write functions and classes that work with any type.
```ts
function identity<T>(value: T): T {
  return value;
}

identity<string>("Hello");
identity<number>(123);
```

### 📦 Generic Arrays
```ts
function firstElement<T>(arr: T[]): T {
  return arr[0];
}
```

### 🧱 Generic Interfaces & Classes
```ts
interface Box<T> {
  content: T;
}

const box: Box<string> = { content: "Books" };
```

### 📝 Exercises
1. Write a generic `reverseArray` function.
2. Create a `Box<T>` type and use it.
3. Add a constraint to accept only objects with `length` property.

✅ Next: **Day 10 - Enums**

---

## Day 10: Enums

### 📌 What You’ll Learn:
- Numeric and string enums
- Reverse mappings
- Use cases for enums

---

### 🔢 Numeric Enums
```ts
enum Direction {
  Up,
  Down,
  Left,
  Right,
}

let move: Direction = Direction.Left;
```

### 🔤 String Enums
```ts
enum Status {
  Success = "SUCCESS",
  Error = "ERROR",
}
```

### 🔁 Reverse Mapping
```ts
enum Role {
  Admin = 1,
  User = 2,
}

console.log(Role[1]); // "Admin"
```

### 📝 Exercises
1. Create a string enum for HTTP methods.
2. Use enums in function parameters.
3. Print enum values and reverse map them.

## Day 11: Type Narrowing

### 📌 What You’ll Learn:
- Type guards
- Narrowing types using `typeof`, `in`, and `instanceof`

---

### 🔍 Type Guards

```ts
function padLeft(value: string, padding: string | number) {
  if (typeof padding === "number") {
    return Array(padding + 1).join(" ") + value;
  }
  return padding + value;
}
```

### 🔐 `in` Operator

```ts
interface Admin {
  role: string;
}
interface User {
  name: string;
}

function printUserInfo(person: Admin | User) {
  if ("role" in person) {
    console.log(`Admin role: ${person.role}`);
  } else {
    console.log(`User name: ${person.name}`);
  }
}
```

### 🔨 `instanceof`

```ts
class Car {
  drive() {
    console.log("Driving...");
  }
}

class Truck {
  load() {
    console.log("Loading...");
  }
}

function operate(vehicle: Car | Truck) {
  if (vehicle instanceof Truck) {
    vehicle.load();
  } else {
    vehicle.drive();
  }
}
```

### 📝 Exercises
1. Use `typeof` to narrow between string and number types.
2. Use `in` to differentiate object shapes.
3. Create two classes and use `instanceof` in a function.

✅ Next: **Day 12 - Type Assertions**

---

## Day 12: Type Assertions

### 📌 What You’ll Learn:
- What is type assertion
- When and how to use it

---

### 🔄 Type Assertion Syntax

```ts
let someValue: unknown = "I am a string";
let strLength: number = (someValue as string).length;
```

Alternative syntax:
```ts
let strLength2: number = (<string>someValue).length;
```

### 🧱 Use Cases

```ts
const input = document.getElementById("username") as HTMLInputElement;
console.log(input.value);
```

### ⚠️ Warning
Type assertions do **not** perform type checking or restructuring. They tell the compiler what you know is true.

### 📝 Exercises
1. Use `as` to assert types on `unknown` variables.
2. Access a property on a DOM element using type assertion.

✅ Next: **Day 13 - Literal Types**

---

## Day 13: Literal Types

### 📌 What You’ll Learn:
- Literal types
- `as const`

---

### 🔠 Literal Type
```ts
let direction: "up" | "down";
direction = "up"; // ✅
direction = "left"; // ❌ Error
```

### 🧱 Example with Functions
```ts
function move(direction: "left" | "right") {
  console.log(`Moving ${direction}`);
}
```

### 🔐 `as const`
```ts
let config = {
  apiUrl: "https://api.com",
} as const;
```

### 📝 Exercises
1. Create a function that accepts only certain string literals.
2. Use `as const` and observe type behavior.

✅ Next: **Day 14 - Nullable Types**

---

## Day 14: Nullable Types

### 📌 What You’ll Learn:
- `null` & `undefined`
- Optional chaining
- Nullish coalescing

---

### ✅ Basic Example
```ts
let name: string | null = null;
```

### 🔗 Optional Chaining
```ts
const user = {
  profile: {
    email: "user@example.com",
  },
};

console.log(user?.profile?.email);
```

### ❓ Nullish Coalescing
```ts
let input = null;
let value = input ?? "default";
console.log(value); // "default"
```

### 📝 Exercises
1. Access nested properties safely using optional chaining.
2. Use `??` to provide default values.

✅ Next: **Day 15 - Utility Types**

---

## Day 15: Utility Types

### 📌 What You’ll Learn:
- Built-in utility types: `Partial`, `Required`, `Readonly`, `Pick`, `Omit`

---

### 🧱 `Partial`
```ts
type Todo = {
  title: string;
  description: string;
};

const updateTodo = (todo: Partial<Todo>) => {
  // can contain some or all props
};
```

### 🧱 `Readonly`
```ts
const todo: Readonly<Todo> = {
  title: "Learn TS",
  description: "Practice daily",
};
// todo.title = "New Title"; ❌ Error
```

### 📝 Exercises
1. Create a type and make it `Partial`.
2. Use `Pick` and `Omit` to create subsets.



## Day 16: `keyof` & `typeof`

### 📌 What You’ll Learn:
- `typeof` to get the type from a variable
- `keyof` to get keys of an object type

---

### 🧠 `typeof`
```ts
let name = "Alice";
type NameType = typeof name; // string
```

### 🔑 `keyof`
```ts
interface User {
  id: number;
  name: string;
}

type UserKeys = keyof User; // "id" | "name"
```

### 📝 Exercises
1. Use `typeof` to create a type from a function's return value.
2. Combine `typeof` and `keyof` to create a type from an object’s keys.

✅ Next: **Day 17 - Mapped Types**

---

## Day 17: Mapped Types

### 📌 What You’ll Learn:
- Mapped types to transform existing types

---

### 🔄 Mapped Type Example
```ts
type User = {
  id: number;
  name: string;
};

type OptionalUser = {
  [K in keyof User]?: User[K];
};
```

### 📝 Exercises
1. Create a mapped type that makes all fields required.
2. Create a mapped type that wraps every field in a function.

✅ Next: **Day 18 - Conditional Types**

---

## Day 18: Conditional Types

### 📌 What You’ll Learn:
- Writing types based on conditions

---

### ❓ Conditional Type
```ts
type IsString<T> = T extends string ? true : false;

let check: IsString<"hello">; // true
let check2: IsString<123>;    // false
```

### 📝 Exercises
1. Create a conditional type to check if type is array.
2. Create a conditional type to convert `null` to `never`.

✅ Next: **Day 19 - Template Literal Types**

---

## Day 19: Template Literal Types

### 📌 What You’ll Learn:
- Creating new types from template strings

---

### 🔤 Template Literal Example
```ts
type EventName = `on${Capitalize<string>}`;
```

### 📝 Exercises
1. Create a type like `"GET:/user" | "POST:/user"`.
2. Create a route name prefix using template literals.

✅ Next: **Day 20 - Type Guards**

---

## Day 20: Type Guards

### 📌 What You’ll Learn:
- How to narrow types using conditions

---

### 🛡️ Type Guard Example
```ts
function isString(value: unknown): value is string {
  return typeof value === "string";
}

function print(value: unknown) {
  if (isString(value)) {
    console.log(value.toUpperCase());
  }
}
```

### 📝 Exercises
1. Write a type guard for checking if a value is an array.
2. Create a type guard for custom interface.



## Day 21: Conditional Types

### 📌 What You’ll Learn:
- What are conditional types
- How to use them
- Practical examples

---

### 🔄 What Are Conditional Types?
Conditional types let you choose one type or another based on a condition.

```ts
type IsString<T> = T extends string ? "Yes" : "No";

type A = IsString<string>;  // "Yes"
type B = IsString<number>;  // "No"
```

### 🧪 Example: Remove Null
```ts
type NonNullable<T> = T extends null | undefined ? never : T;

type Clean = NonNullable<string | null>; // string
```

### 📝 Exercises
1. Create a type that checks if a type is an array.
2. Build a `Flatten<T>` type that gets the inner type of an array.

---

## Day 22: Template Literal Types

### 📌 What You’ll Learn:
- Template literals in types
- Combine strings
- Generate types dynamically

---

### 🔤 Basic Usage
```ts
type Greeting = `Hello, ${string}`;

const greet: Greeting = "Hello, world";
```

### 🧱 Combine Union Types
```ts
type Status = "success" | "error";
type Message = `status-${Status}`;
// "status-success" | "status-error"
```

### 📝 Exercises
1. Create a type for API endpoints like `/user/:id`.
2. Combine `"top" | "bottom"` with `"left" | "right"` into corner positions.

---

## Day 23: Mapped Types

### 📌 What You’ll Learn:
- Create new types from existing keys
- `keyof`, `in`, and `as`

---

### 🔁 Basic Mapping
```ts
interface Todo {
  title: string;
  completed: boolean;
}

type ReadOnlyTodo = {
  readonly [K in keyof Todo]: Todo[K];
};
```

### 📝 Exercises
1. Create a type that makes all fields optional.
2. Create a type that makes all fields required.

---

## Day 24: keyof and typeof Operators

### 📌 What You’ll Learn:
- `keyof` to get property names
- `typeof` to get value types

---

### 🔑 keyof
```ts
interface Person {
  name: string;
  age: number;
}

type PersonKeys = keyof Person; // "name" | "age"
```

### 📦 typeof
```ts
const user = {
  id: 1,
  name: "Alice",
};

type UserType = typeof user;
```

### 📝 Exercises
1. Create a function that accepts only valid keys of an object.
2. Use `typeof` to type variables based on constants.

---

## Day 25: Advanced Mapped Types

### 📌 What You’ll Learn:
- Conditional mapped types
- Renaming keys

---

### 🧱 Conditional Mapping
```ts
type Nullable<T> = {
  [K in keyof T]: T[K] | null;
};
```

### 📝 Exercises
1. Convert all types in a type to string.
2. Remove readonly from all fields.

---

## Day 26: Utility Types Deep Dive

### 📌 What You’ll Learn:
- `Exclude`, `Extract`, `ReturnType`, `InstanceType`

---

### 🧰 Examples
```ts
type A = Exclude<"a" | "b", "b">;      // "a"
type B = Extract<"a" | "b", "b" | "c">; // "b"

type Fn = () => string;
type R = ReturnType<Fn>; // string
```

### 📝 Exercises
1. Use `ReturnType` to infer the return type of a function.
2. Use `Exclude` to remove keys from a union.

---

## Day 27: Declaration Merging

### 📌 What You’ll Learn:
- Merge interfaces
- Extend modules

---

### 🧬 Interface Merging
```ts
interface Box {
  height: number;
}

interface Box {
  width: number;
}

const box: Box = {
  height: 100,
  width: 200,
};
```

### 📝 Exercises
1. Try merging two interfaces with different properties.
2. Merge namespaces for customization.

---

## Day 28: Type Guards

### 📌 What You’ll Learn:
- Narrow down types using logic
- `typeof`, `in`, `instanceof`

---

### 🛡️ Examples
```ts
function isString(val: unknown): val is string {
  return typeof val === "string";
}

function process(val: string | number) {
  if (isString(val)) {
    console.log(val.toUpperCase());
  }
}
```

### 📝 Exercises
1. Create a custom type guard.
2. Use `in` to check if property exists.

---

## Day 29: TSConfig & Compiler Options

### 📌 What You’ll Learn:
- tsconfig.json basics
- Useful compiler options

---

### 🛠️ Common Options
```json
{
  "compilerOptions": {
    "target": "ES2020",
    "module": "commonjs",
    "strict": true,
    "outDir": "./dist"
  }
}
```

### 📝 Exercises
1. Enable strict mode and observe errors.
2. Change output directory and compile.

---

## Day 30: Build a Mini Project (Todo CLI)

### 📌 What You’ll Learn:
- Apply everything you learned
- Use types, classes, enums, generics, utility types

---

### ✅ Todo CLI Project
```ts
interface Todo {
  id: number;
  task: string;
  done: boolean;
}

class TodoApp {
  private todos: Todo[] = [];

  add(task: string) {
    const todo: Todo = {
      id: Date.now(),
      task,
      done: false,
    };
    this.todos.push(todo);
  }

  list() {
    return this.todos;
  }

  toggle(id: number) {
    const todo = this.todos.find(t => t.id === id);
    if (todo) todo.done = !todo.done;
  }
}
```

### 📝 Exercises
1. Add persistence using local file.
2. Extend with priority and due date.

🎉 **You did it! 30 Days Complete!**




