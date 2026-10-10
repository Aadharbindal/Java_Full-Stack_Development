# 03 — Operators

Data par kaam karne ke tools. Yahan 6 files hain, har ek operator ki ek category.

## Files

| File | Operators | Kya dikhata hai |
| --- | --- | --- |
| [ArithmeticOperators.java](ArithmeticOperators.java) | `+` `-` `*` `/` `%` | Real-world examples (total marks, wallet balance, electricity bill) + String concatenation ka trap |
| [RelationalOperator.java](RelationalOperator.java) | `>` `<` `>=` `<=` `==` `!=` | Sab comparisons `boolean` return karte hain |
| [LogicalOperators.java](LogicalOperators.java) | `&&` `\|\|` `!` | Do conditions ko jodna |
| [CompundAssignment.java](CompundAssignment.java) | `+=` `-=` `*=` `/=` `%=` | `num += 5` = `num = num + 5` ka shortcut |
| [IncrementDec.java](IncrementDec.java) | `++` `--` | Pre vs post increment ka asli difference |
| [TernoryOper.java](TernoryOper.java) | `? :` | `if-else` ka one-line version |

## Key points

**Arithmetic:** `/` integer division karta hai jab dono operands `int` hon — `10/3` ka answer `3` aata hai, `3.33` nahi. `%` remainder deta hai (even/odd check ke liye bahut use hota hai).

**`+` ka dual role:** numbers ke saath addition, `String` ke saath concatenation. Left-to-right chalta hai, aur jahan ek baar `String` mil gaya, wahan se aage sab concatenation ban jaata hai:

```java
System.out.println(10 + 20);           // 30     — dono int, addition
System.out.println("10" + 20);         // 1020   — String mila, concat
System.out.println(10 + 20 + "java");  // 30java — pehle 10+20=30, phir concat
System.out.println("java" + 10 + 20);  // java1020 — shuru se hi concat
```

**Compound assignment:** `num += 5` chhota likhne ka tareeka hai `num = num + 5` ka. `CompundAssignment.java` ka trace:

```
start: 10  →  += 5 → 15  →  -= 3 → 12  →  *= 2 → 24  →  /= 4 → 6  →  %= 2 → 0
```

**Pre vs post increment:**

| Form | Pehle kya hota hai | Expression ki value |
| --- | --- | --- |
| `++c` (pre) | variable badhta hai | **nayi** value |
| `c++` (post) | purani value use hoti hai | **purani** value, variable baad me badhta hai |

```java
int c = 5;
int d = ++c;    // c pehle 6 bana, phir d = 6
int res = c++;  // res ko purani 7... nahi — res = 6, aur c = 7
```

**Ternary:** `condition ? agar_true : agar_false`

```java
String res = age >= 18 ? "Adult" : "Minor";
```

## Compile & run

```bash
javac IncrementDec.java
java IncrementDec
```

## Gotchas

**1. `ArithmeticOperators.java` me ek comment galat hai.** Line par likha hai:

```java
System.out.println(10+20); //20
```

Actual output `30` hai. Comment typo hai — code sahi hai.

**2. Chained increment expressions — paper par solve karna seekho.** Rule: expression **left se right** evaluate hota hai, aur har `++`/`--` turant variable ko badal deta hai.

`IncrementDec.java` me:

```java
int k = 5;
int r = ++k + ++k - k-- + k++ + k--;
```

Step by step:

| Step | Operation | Value use hui | `k` ab |
| --- | --- | --- | --- |
| 1 | `++k` | 6 | 6 |
| 2 | `++k` | 7 | 7 |
| 3 | `k--` | 7 | 6 |
| 4 | `k++` | 6 | 7 |
| 5 | `k--` | 7 | 6 |

`r = 6 + 7 - 7 + 6 + 7 = 19`, aur `k = 6`.

`TernoryOper.java` me:

```java
int a = 6;
int b = a++ + ++a - a-- + --a;   // 6 + 8 - 8 + 6 = 12,  a = 6

int a1 = 2;
int r1 = ++a1 + a1++ * --a1;     // 3 + (3 * 3) = 12,  a1 = 3
```

Dusre case me `*` ki precedence `+` se zyada hai, par **evaluation order phir bhi left-to-right** hai — pehle teeno operands ki values nikalti hain (3, 3, 3), *phir* precedence ke hisaab se `3 + 9` hota hai. Ye distinction interviews me poocha jaata hai.

Practical advice: real code me aise expressions kabhi na likho. Ek statement me ek hi variable ko ek baar modify karo.
