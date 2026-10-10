# 02 — Data Types

Java statically typed hai: har variable ka type pehle se fix karna padta hai, aur usme sirf usi type ki value aa sakti hai.

## Files

| File | Kya dikhata hai |
| --- | --- |
| [IntDataType.java](IntDataType.java) | Sirf `int` — pehla step |
| [DataType.java](DataType.java) | Poora tour: integer, decimal, `char`, `boolean`, `String`, aur integer types ki range comparison |

## Primitive types

| Type | Size | Range | Example |
| --- | --- | --- | --- |
| `byte` | 1 byte | -128 to 127 | `byte smallNum = 100;` |
| `short` | 2 bytes | -32,768 to 32,767 | `short mediumNum = 300;` |
| `int` | 4 bytes | ~ -2.1 billion to 2.1 billion | `int normalNum = 100000;` |
| `long` | 8 bytes | bahut bada | `long bigNum = 8938397839837L;` |
| `float` | 4 bytes | ~7 decimal digits precision | `float height = 5.10f;` |
| `double` | 8 bytes | ~15 decimal digits precision | `double price = 99.88;` |
| `char` | 2 bytes | ek single character | `char grade = 'A';` |
| `boolean` | 1 bit (JVM-dependent) | `true` / `false` | `boolean isPassed = true;` |

`String` primitive **nahi** hai — wo ek class hai, isliye capital `S` se likhte hain.

## Key points

- Decimal literal by default `double` hota hai. `float` me daalna ho to `f` suffix lazmi: `5.10f`
- Integer literal by default `int` hota hai. `int` ki range se bada ho to `L` suffix lazmi: `8938397839837L`
- `char` me **single quotes** (`'A'`), `String` me **double quotes** (`"Rahul"`)
- Jitni zarurat ho utna hi bada type lo — `byte`/`short` memory bachate hain, par normally `int` hi default choice hai
- Paise ke calculations me `float`/`double` se precision loss hota hai; wahan `BigDecimal` use hota hai (aage padhenge)

## Compile & run

```bash
javac DataType.java
java DataType
```

## Gotchas

**1. Ye dono files ek saath compile nahi hongi.** Dono ke andar class ka naam `DataType` hai (`IntDataType.java` me bhi `class DataType` likha hai, file ke naam se match nahi karta). Isliye:

```bash
javac *.java        # error: duplicate class: DataType
```

Ek-ek karke compile karo:

```bash
javac DataType.java && java DataType
javac IntDataType.java && java DataType
```

Dhyaan do — `IntDataType.java` compile karne par bhi banta hai `DataType.class`, kyunki `java` command file ka naam nahi, **class ka naam** leta hai. Java me non-public class ka naam file se match karna zaruri nahi hai; `public` class ka naam match karna **zaruri** hai.

**2. `double salary = 3555232424245.34f;`** — yahan value pehle `float` ban rahi hai (`f` suffix), aur phir `double` me jaa rahi hai. `float` me sirf ~7 digits ki precision hoti hai, isliye output exact `3555232424245.34` nahi aayega — kuch aisa aayega `3.5552324E12`. Sahi tareeka hai suffix hata dena:

```java
double salary = 3555232424245.34;
```

**3. `float height = 5.10f;`** print hone par `5.1` dikhega, `5.10` nahi — trailing zero value ka part nahi hota.
