# 03 — Operators

The tools for working with data. There are six files here, one per operator category.

## Files

| File | Operators | What it shows |
| --- | --- | --- |
| [ArithmeticOperators.java](ArithmeticOperators.java) | `+` `-` `*` `/` `%` | Real-world examples (total marks, wallet balance, electricity bill) plus the String concatenation trap |
| [RelationalOperator.java](RelationalOperator.java) | `>` `<` `>=` `<=` `==` `!=` | Every comparison returns a `boolean` |
| [LogicalOperators.java](LogicalOperators.java) | `&&` `\|\|` `!` | Combining two conditions |
| [CompundAssignment.java](CompundAssignment.java) | `+=` `-=` `*=` `/=` `%=` | `num += 5` as shorthand for `num = num + 5` |
| [IncrementDec.java](IncrementDec.java) | `++` `--` | The real difference between pre and post increment |
| [TernoryOper.java](TernoryOper.java) | `? :` | The one-line version of `if-else` |

## Key points

**Arithmetic:** `/` performs integer division when both operands are `int` — `10/3` gives `3`, not `3.33`. `%` gives the remainder (very commonly used for even/odd checks).

**The dual role of `+`:** addition with numbers, concatenation with `String`. It evaluates left to right, and once a `String` appears, everything from that point on becomes concatenation:

```java
System.out.println(10 + 20);           // 30     — both int, addition
System.out.println("10" + 20);         // 1020   — String involved, concatenation
System.out.println(10 + 20 + "java");  // 30java — 10+20=30 first, then concatenation
System.out.println("java" + 10 + 20);  // java1020 — concatenation from the start
```

**Compound assignment:** `num += 5` is shorthand for `num = num + 5`. The trace through `CompundAssignment.java`:

```
start: 10  →  += 5 → 15  →  -= 3 → 12  →  *= 2 → 24  →  /= 4 → 6  →  %= 2 → 0
```

**Pre vs post increment:**

| Form | What happens first | Value of the expression |
| --- | --- | --- |
| `++c` (pre) | the variable is incremented | the **new** value |
| `c++` (post) | the old value is used | the **old** value; the variable is incremented afterwards |

```java
int c = 5;
int d = ++c;    // c becomes 6 first, so d = 6
int res = c++;  // res = 6 (the old value), and c becomes 7
```

**Ternary:** `condition ? value_if_true : value_if_false`

```java
String res = age >= 18 ? "Adult" : "Minor";
```

## Compile and run

```bash
javac IncrementDec.java
java IncrementDec
```

## Gotchas

**1. One comment in `ArithmeticOperators.java` is wrong.** The line reads:

```java
System.out.println(10+20); //20
```

The actual output is `30`. The comment is a typo — the code is correct.

**2. Chained increment expressions — learn to solve these on paper.** The rule: the expression is evaluated **left to right**, and each `++`/`--` changes the variable immediately.

In `IncrementDec.java`:

```java
int k = 5;
int r = ++k + ++k - k-- + k++ + k--;
```

Step by step:

| Step | Operation | Value used | `k` after |
| --- | --- | --- | --- |
| 1 | `++k` | 6 | 6 |
| 2 | `++k` | 7 | 7 |
| 3 | `k--` | 7 | 6 |
| 4 | `k++` | 6 | 7 |
| 5 | `k--` | 7 | 6 |

So `r = 6 + 7 - 7 + 6 + 7 = 19`, and `k = 6`.

In `TernoryOper.java`:

```java
int a = 6;
int b = a++ + ++a - a-- + --a;   // 6 + 8 - 8 + 6 = 12,  a = 6

int a1 = 2;
int r1 = ++a1 + a1++ * --a1;     // 3 + (3 * 3) = 12,  a1 = 3
```

In the second case `*` has higher precedence than `+`, but **evaluation order is still left to right** — all three operand values are computed first (3, 3, 3), and *only then* is `3 + 9` applied according to precedence. This distinction gets asked in interviews.

Practical advice: never write expressions like this in real code. Modify a variable at most once per statement.
