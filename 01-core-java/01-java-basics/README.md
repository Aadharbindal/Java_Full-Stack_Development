# 01 — Java Basics

The first section of Core Java. Folders are numbered so they can be read in sequence.

## Topics

| # | Topic | Files | Focus |
| --- | --- | --- | --- |
| 00 | [getting-started](00-getting-started) | 2 | The `main` method, `System.out.println`, statements running line by line |
| 01 | [variables](01-variables) | 4 | Declare vs initialize, reassigning values, naming rules, the default-value rule |
| 02 | [data-types](02-data-types) | 2 | `int` `double` `float` `char` `boolean` `String`, and the ranges of `byte`/`short`/`int`/`long` |
| 03 | [operators](03-operators) | 6 | Arithmetic, relational, logical, compound assignment, increment/decrement, ternary |
| 04 | [control-statements](04-control-statements) | 4 | `if`, `if-else`, the `else-if` ladder, nested `if`, `switch` |
| 05 | [loops](05-loops) | 4 | `while`, `for`, nested `for`, `do-while`, `break` and `continue` |
| 06 | [classes-and-objects](06-classes-and-objects) | 2 | Writing a class, fields and methods, creating objects with `new`, the `.` operator |

## Suggested reading order

1. `00-getting-started` — understand the structure of a program
2. `01-variables` → `02-data-types` — storing data
3. `03-operators` — working with data
4. `04-control-statements` → `05-loops` — controlling the flow
5. `06-classes-and-objects` — entry point into OOP

## Compile and run

```bash
javac ArithmeticOperators.java
java ArithmeticOperators
```

## Note

This code is kept exactly as it was written in class — deliberately. Some files have:

- a class name that does not match the file name,
- a compile-time error (which was the whole point of the example),
- or output that looks wrong at first glance (tricky increment/decrement expressions).

Every such case is explained under "Gotchas" in that topic's README. Read it before copying and running the file.
