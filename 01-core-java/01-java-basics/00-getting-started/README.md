# 00 — Getting Started

The first step: the structure of a Java program, and understanding that statements run top to bottom, one at a time.

## Files

| File | What it shows |
| --- | --- |
| [Test.java](Test.java) | Minimal program — declare a variable and print it three times with `System.out.println` |
| [ControlStatements.java](ControlStatements.java) | Sequential execution — five print statements run in exactly the order they are written |

## Key points

- Every program lives inside a class: `class Test { ... }`
- Execution starts at the `main` method: `public static void main(String[] args)`
- The JVM looks specifically for `main`, so the signature has to be exactly this
- `System.out.println(...)` prints and moves to the next line; `System.out.print(...)` does not break the line
- Statement order is execution order. Whatever is written first runs first

## Compile and run

```bash
javac Test.java
java Test
```

Expected output:

```
20
20
20
```

## Gotcha

The name `ControlStatements.java` suggests `if` or `switch`, but the file only contains print statements. That is deliberate: before learning control statements, it helps to see that **without** any control statement the flow is perfectly straight. The actual `if` and `switch` examples are in [04-control-statements](../04-control-statements).
