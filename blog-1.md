# 🧠 Type Safety in TypeScript: Why `unknown` is Safer than `any`

## 📌 Introduction

TypeScript’s strength lies in its ability to catch errors at compile time. However, using the `any` type can completely bypass this safety. In contrast, `unknown` provides a safer way to handle unpredictable data while still enforcing type checks. This blog explores why `any` is considered a “type safety hole” and how `unknown` combined with type narrowing improves reliability.

---

## 🚫 The Problem with `any`

The `any` type disables TypeScript’s type checking.

```ts
let data: any = "Hello";
data.toFixed(2); // ❌ No compile error, but runtime crash
```

Here, TypeScript allows invalid operations, leading to potential bugs.

👉 This is why `any` is called a **type safety hole**.

---

## ✅ The Safer Alternative: `unknown`

`unknown` forces you to check the type before using it.

```ts
let data: unknown = "Hello";

if (typeof data === "string") {
  console.log(data.toUpperCase()); // ✅ Safe
}
```

Now TypeScript ensures safe usage.

---

## 🔍 What is Type Narrowing?

Type narrowing means refining a variable’s type using checks.

```ts
function printLength(value: unknown) {
  if (typeof value === "string") {
    console.log(value.length); // ✅ Narrowed to string
  }
}
```

---

## 🛠️ Custom Type Guards

```ts
function isNumber(value: unknown): value is number {
  return typeof value === "number";
}

function process(value: unknown) {
  if (isNumber(value)) {
    console.log(value.toFixed(2)); // ✅ Safe
  }
}
```

---

## 🎯 Why It Matters

- Prevents runtime errors
- Forces validation of external data
- Improves code reliability

---

## 🧩 Conclusion

Avoid `any` whenever possible. Use `unknown` instead and apply type narrowing techniques to safely handle dynamic data. This small change significantly improves the robustness of your TypeScript applications.
