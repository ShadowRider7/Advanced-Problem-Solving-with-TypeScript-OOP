\*\* Why any is a Type Safety Hole (and unknown is Better)

Problem with any
let data: any = "Hello";
data.toFixed(2); // No error at compile time, but crashes at runtime

TypeScript allows this because any tells the compiler:

“Trust me, I know what I’m doing.”

That’s why it’s called a type safety hole—errors slip through unnoticed.

Safer Alternative: unknown

unknown forces you to validate the type before using it.

let data: unknown = "Hello";

if (typeof data === "string") {
console.log(data.toUpperCase());
}

Now TypeScript enforces checks before usage.

\*\* What is Type Narrowing?

Type narrowing is the process of refining a variable’s type using checks.

Example:
function printLength(value: unknown) {
if (typeof value === "string") {
// Type narrowed to string
console.log(value.length);
} else {
console.log("Not a string");
}
}

Common Narrowing Techniques:
typeof (for primitives)
instanceof (for classes)
in operator (for object properties)
Custom type guards

This ensures our app handles unpredictable data without runtime surprises.
