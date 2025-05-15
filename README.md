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
