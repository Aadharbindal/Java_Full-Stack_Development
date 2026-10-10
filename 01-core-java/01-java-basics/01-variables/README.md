# 01 — Variables

A variable is a named box in memory that holds a value.

## Files

| File | What it shows |
| --- | --- |
| [VariableExample01.java](VariableExample01.java) | Declaration and initialization as separate steps: `int age;` then `age=20;` |
| [VariableExample02.java](VariableExample02.java) | Reassigning a value — put a new value in the same variable, the old one is gone |
| [VariableExample03.java](VariableExample03.java) | Naming rules — `age1`, `student_marks`, `$sal`, `studentName` are all valid |
| [DefaultValue.java](DefaultValue.java) | **Compile error** — using a local variable without initializing it |

## Key points

Using a variable takes two steps:

```java
int age;      // 1. declaration — type and name are set
age = 20;     // 2. initialization — a value is assigned
```

Both can go on one line: `int age = 20;`

**Naming rules:**

- Can start with a letter, `_`, or `$` — **not** with a digit
- Letters, digits, `_`, and `$` are allowed after the first character
- Spaces and keywords (`int`, `class`, `for`, ...) are not allowed
- Names are case-sensitive: `age` and `Age` are two different variables
- Convention: use `camelCase` (`studentName`, not `student_name` or `StudentName`)

## Gotchas

**`DefaultValue.java` will not compile** — and that is exactly the point:

```java
int age;
System.out.println(age);   // error: variable age might not have been initialized
```

**Java does not give local variables a default value.** A variable declared inside a method *must* be initialized before it is used. Fields (declared inside a class but outside any method) do get defaults — `0` for `int`, `false` for `boolean`, `null` for object references. That difference shows up in [06-classes-and-objects](../06-classes-and-objects), where printing `s.age` gives `0`.

To see the error yourself:

```bash
javac DefaultValue.java
```

In `VariableExample03.java`, `$sal` and `student_marks` are declared but never printed — they exist only to demonstrate naming. There is no compile warning for this; unused local variables are allowed in Java.
