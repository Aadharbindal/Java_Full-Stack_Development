# 04 — Control Statements

Decision making: changing the program's path based on a condition.

## Files

| File | What it shows | Output |
| --- | --- | --- |
| [IfElseCode.java](IfElseCode.java) | Simple `if-else` — pass/fail, and an even/odd check using `%` | `pass`, `end`, `even` |
| [IfElseCode02.java](IfElseCode02.java) | The `else-if` ladder — deriving a grade from marks | `Grade A+` |
| [NestedIfExample.java](NestedIfExample.java) | Nested `if` — a login check (password inside username) | `Wrong password` |
| [SwitchExample.java](SwitchExample.java) | `switch` — day number to day name | `Monday` |

## Key points

**`if-else`** — two paths, one runs:

```java
if (marks >= 45) {
    System.out.println("pass");
} else {
    System.out.println("fail");
}
```

**The `else-if` ladder** — many conditions, but only the **first match** runs and the rest are skipped. That makes order important: `>= 90` has to be checked before `>= 75`, otherwise 90 marks would also fall into "Grade A".

**Nested `if`** — one `if` inside another. The inner condition is only checked if the outer one is true.

**`switch`** — when comparing one variable against several exact values, this reads more cleanly than an `else-if` ladder:

```java
switch (day) {
    case 1:  System.out.println("Monday"); break;
    case 2:  System.out.println("Tuesday"); break;
    default: System.out.println("Invalid day");
}
```

- `break` is required — without it you get **fall-through** (every case below the matching one also runs)
- `default` is optional but worth having — it runs when no case matches
- `switch` works on `int`-compatible types, `char`, `String`, and `enum` — not on `boolean`

## `if-else` vs `switch`

| Use `if-else` when | Use `switch` when |
| --- | --- |
| Checking a range (`marks >= 90`) | Matching an exact value (`day == 1`) |
| Conditions involve different variables | One variable has several possible values |
| The logic needs complex `&&` / `\|\|` | The set of values is a flat list |

## Compile and run

```bash
javac SwitchExample.java
java SwitchExample
```

## Gotchas

**1. `NestedIfExample.java` compares Strings the wrong way.** This is the most important lesson in this folder:

```java
if (username == "genie")      // WRONG
```

`==` compares references — "are these the *same* object?" — not content. Here it happens to work **by accident**, because `"genie"` is a string literal and Java reuses literals from the String Pool, so both sides are the same object.

But take input from a Scanner, or build the string with `new String("genie")`, and it breaks immediately:

```java
String username = new String("genie");
System.out.println(username == "genie");        // false  (different object)
System.out.println(username.equals("genie"));   // true   (same content)
```

**Rule: always use `.equals()` to compare Strings.** The correct version:

```java
if (username.equals("genie")) {
    if (password.equals("123")) { ... }
}
```

This file outputs `Wrong password` because `password` is set to `"1231"` but compared against `"123"`.

**2. `IfElseCode02.java` contains a dead statement.** Inside the `Grade B` branch:

```java
else if (marks >= 60) {
    System.out.println("Grade B");
    marks = 40;                    // has no effect
}
```

Changing `marks` here does nothing — the `else-if` ladder has already made its decision, and `marks` is never used again afterwards. It is there to show that the ladder matches **once** and exits; it does not re-check from the top. In this run the branch does not even execute (`marks` is 90, so the ladder stops at `Grade A+`).

**3. Always use braces with `if`.** Without them, `if` controls only the next *single* statement — which turns into a silent bug the moment a line is added later.
