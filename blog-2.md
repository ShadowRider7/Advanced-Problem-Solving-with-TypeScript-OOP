\*\* Generics: Reusable and Type-Safe Code

Generics allow you to write functions and components that adapt to different types while preserving strict typing.

Without Generics (Bad Repetition):
function getString(value: string): string {
return value;
}

function getNumber(value: number): number {
return value;
}

This is repetitive and not scalable.

With Generics:
function identity<T>(value: T): T {
return value;
}

const a = identity<string>("Hello");
const b = identity<number>(42);

Now one function works for any type, safely.
