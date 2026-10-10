# 01 — Java Basics

Core Java ka pehla section. Sequence me padhne ke liye folders numbered hain.

## Topics

| # | Topic | Files | Focus |
| --- | --- | --- | --- |
| 00 | [getting-started](00-getting-started) | 2 | `main` method, `System.out.println`, statements line-by-line chalte hain |
| 01 | [variables](01-variables) | 4 | Declare vs initialize, value reassign, naming rules, default value ka rule |
| 02 | [data-types](02-data-types) | 2 | `int` `double` `float` `char` `boolean` `String`, aur `byte`/`short`/`int`/`long` ki range |
| 03 | [operators](03-operators) | 6 | Arithmetic, relational, logical, compound assignment, increment/decrement, ternary |
| 04 | [control-statements](04-control-statements) | 4 | `if`, `if-else`, `else-if` ladder, nested `if`, `switch` |
| 05 | [loops](05-loops) | 4 | `while`, `for`, nested `for`, `do-while`, `break` aur `continue` |
| 06 | [classes-and-objects](06-classes-and-objects) | 2 | Class banana, fields & methods, `new` se object banana, `.` operator |

## Padhne ka suggested order

1. `00-getting-started` — program ka structure samajh lo
2. `01-variables` → `02-data-types` — data store karna
3. `03-operators` — data par kaam karna
4. `04-control-statements` → `05-loops` — flow control karna
5. `06-classes-and-objects` — OOP ki entry

## Compile & run

```bash
javac ArithmeticOperators.java
java ArithmeticOperators
```

## Note

Ye code class me jaisa likha gaya tha waisa hi rakha hai — deliberately. Kuch files me:

- class ka naam file ke naam se match nahi karta,
- ya compile-time error hai (jo topic ka point hi tha),
- ya output pehli nazar me galat lagta hai (tricky increment/decrement expressions).

Har aisa case us topic ke README me "Gotchas" ke neeche explain kiya hua hai. Copy-paste karke chalane se pehle wo padh lena.
