# 🔁 Writing Reusable Code in TypeScript with Generics

## 📌 Introduction

In modern applications, writing reusable and scalable code is essential. TypeScript Generics allow developers to create flexible yet strongly typed functions and components that work with multiple data types without duplication.

---

## ❌ Without Generics (Code Duplication)

```ts
function getString(value: string): string {
  return value;
}

function getNumber(value: number): number {
  return value;
}
```

This approach is repetitive and not scalable.

---

## ✅ Using Generics

```ts
function identity<T>(value: T): T {
  return value;
}

const a = identity<string>("Hello");
const b = identity<number>(42);
```

👉 One function works for all types safely.

---

## 📦 Real-World Example: API Response

```ts
interface ApiResponse<T> {
  data: T;
  success: boolean;
}

const userResponse: ApiResponse<{ name: string }> = {
  data: { name: "John" },
  success: true,
};
```

---

## 🔐 Generics with Constraints

```ts
function getLength<T extends { length: number }>(item: T): number {
  return item.length;
}

getLength("Hello"); // ✅
getLength([1, 2, 3]); // ✅
// getLength(123); ❌ Error
```

---

## 🚀 Benefits of Generics

- Eliminates code duplication
- Maintains strict type safety
- Works with multiple data structures
- Scales easily in large applications

---

## 🧩 Conclusion

Generics are one of TypeScript’s most powerful features. They allow you to write reusable, flexible, and type-safe code without sacrificing clarity or maintainability. Mastering generics is key to building scalable applications.
