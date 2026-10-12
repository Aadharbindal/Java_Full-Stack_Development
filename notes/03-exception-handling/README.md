# Notes — 03 Exception Handling

Theory notes on what happens when a program hits a problem at runtime, and how to deal with it instead of crashing.

## Files

| # | File | Class date | Pages | What it covers |
| --- | --- | --- | --- | --- |
| 01 | [01-exception-handling.pdf](01-exception-handling.pdf) | 04 Jul 2026 | 7 | What an exception is, `Error` vs `Exception`, checked vs unchecked, compile-time error vs runtime exception, why handling matters, the five keywords, printing exception info, `try-catch` flow, `finally`, `throw`, custom exceptions |

## Key ideas from these notes

**Exception = a runtime problem.** An unwanted or unexpected event during execution that disrupts the normal flow. The example used in class is `ArithmeticException: / by zero` — the program stops at `a/b` and the next line never runs.

**`Error` vs `Exception`** — an `Error` is usually a serious problem application code cannot handle; an `Exception` is a problem the code *can* handle. As a backend developer you mainly handle exceptions, not errors.

**Checked vs unchecked:**

| | Checked | Unchecked |
| --- | --- | --- |
| Compiler forces handling | Yes | No |
| Thrown at | compile time if unhandled | runtime |
| Examples | `IOException`, `SQLException` | `NullPointerException`, `ArrayIndexOutOfBoundsException` |

The rule given in class: `RuntimeException` and all its subclasses, plus `Error` and all its subclasses, are unchecked — everything else is checked.

**The five keywords:**

| Keyword | Purpose |
| --- | --- |
| `try` | wrap the risky code |
| `catch` | handle the exception |
| `finally` | cleanup that always runs, exception or not |
| `throw` | manually raise an exception |
| `throws` | delegate the responsibility to the caller |

**Printing exception information** — three methods, increasing in detail:

| Method | Prints |
| --- | --- |
| `getMessage()` | only the description |
| `toString()` | exception name and description |
| `printStackTrace()` | exception name, description, and the full stack trace |

## Note on ordering

Section numbers in [notes](..) group topics, not dates. This session (04 Jul) was actually taught one day *before* [variable types and interfaces](../02-oop/05-variable-types-and-interfaces.pdf) (05 Jul), which sits in the OOP section because that is where it belongs topically. Class dates are listed in every table, so the real timeline stays visible.

The notes end on "how to create a custom exception", marked as very important, which suggests the topic continues in a later class. Further exception notes go in this folder.

## Related code

No code committed for this topic yet.
