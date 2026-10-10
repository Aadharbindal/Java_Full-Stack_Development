# 02 — Data Types

Java is statically typed: every variable's type is fixed up front, and only values of that type can go into it.

## Files

| File | What it shows |
| --- | --- |
| [IntDataType.java](IntDataType.java) | Just `int` — the first step |
| [DataType.java](DataType.java) | The full tour: integer types, decimals, `char`, `boolean`, `String`, and a comparison of integer ranges |

## Primitive types

| Type | Size | Range | Example |
| --- | --- | --- | --- |
| `byte` | 1 byte | -128 to 127 | `byte smallNum = 100;` |
| `short` | 2 bytes | -32,768 to 32,767 | `short mediumNum = 300;` |
| `int` | 4 bytes | about -2.1 billion to 2.1 billion | `int normalNum = 100000;` |
| `long` | 8 bytes | very large | `long bigNum = 8938397839837L;` |
| `float` | 4 bytes | about 7 decimal digits of precision | `float height = 5.10f;` |
| `double` | 8 bytes | about 15 decimal digits of precision | `double price = 99.88;` |
| `char` | 2 bytes | a single character | `char grade = 'A';` |
| `boolean` | 1 bit (JVM-dependent) | `true` / `false` | `boolean isPassed = true;` |

`String` is **not** a primitive — it is a class, which is why it is written with a capital `S`.

## Key points

- A decimal literal is a `double` by default. To make it a `float`, the `f` suffix is required: `5.10f`
- An integer literal is an `int` by default. If it is larger than the `int` range, the `L` suffix is required: `8938397839837L`
- `char` uses **single quotes** (`'A'`), `String` uses **double quotes** (`"Rahul"`)
- Use only as large a type as needed — `byte`/`short` save memory, but `int` is the normal default choice
- `float` and `double` lose precision in money calculations; `BigDecimal` is used there instead (covered later)

## Compile and run

```bash
javac DataType.java
java DataType
```

## Gotchas

**1. These two files cannot be compiled together.** Both declare a class named `DataType` (`IntDataType.java` also contains `class DataType`, which does not match its file name). So:

```bash
javac *.java        # error: duplicate class: DataType
```

Compile them one at a time:

```bash
javac DataType.java && java DataType
javac IntDataType.java && java DataType
```

Note that compiling `IntDataType.java` also produces `DataType.class`, because the `java` command takes the **class name**, not the file name. In Java, a non-public class does not need to match its file name; a `public` class **does**.

**2. `double salary = 3555232424245.34f;`** — the value becomes a `float` first (because of the `f` suffix) and is only then widened to `double`. A `float` holds only about 7 digits of precision, so the output will not be exactly `3555232424245.34` — it will be something like `3.5552324E12`. The fix is to drop the suffix:

```java
double salary = 3555232424245.34;
```

**3. `float height = 5.10f;`** prints as `5.1`, not `5.10` — a trailing zero is not part of the value.
