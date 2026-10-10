# 05 — Loops

Doing the same work repeatedly, without repeating the code.

## Files

| File | Class name | What it shows |
| --- | --- | --- |
| [LoopsExample.java](LoopsExample.java) | `WhileLoopExample` | `while` loop — hello ten times, sum of 1 to 5, multiplication table |
| [ForWhileLoopExample.java](ForWhileLoopExample.java) | `ForWhileLoopExample` | `for` loop, a factorial attempt, star pattern with nested `for` |
| [DoWhileLoopExample.java](DoWhileLoopExample.java) | `DoWhileLoopExample` | `do-while` — runs once even when the condition is false |
| [ConBreak.java](ConBreak.java) | `ConBreak` | `break` exits the loop, `continue` skips one iteration |

## Three loops, the same job

Every loop has three parts: **initialization**, **condition**, and **update**.

```java
// while — the parts are written separately
int i = 1;                    // init
while (i <= 10) {             // condition
    System.out.println(i);
    i++;                      // update
}

// for — all three on one line
for (int i = 1; i <= 10; i++) {
    System.out.println(i);
}

// do-while — the condition is checked AFTERWARDS
int i = 1;
do {
    System.out.println(i);
    i++;
} while (i <= 10);
```

| Loop | Condition checked | Minimum runs | When to use |
| --- | --- | --- | --- |
| `while` | before | 0 times | The number of iterations is not known |
| `for` | before | 0 times | The count is known (1 to 10) |
| `do-while` | after | **1 time** | A menu — it has to be shown at least once |

## `break` vs `continue`

```java
for (int i = 1; i <= 10; i++) {
    if (i == 5) break;        // exits the loop entirely → 1 2 3 4
    System.out.println(i);
}

for (int i = 1; i <= 10; i++) {
    if (i % 2 != 0) continue; // skips this iteration → 2 4 6 8 10
    System.out.println(i);
}
```

`break` = get out. `continue` = skip this round, start the next one.

## Nested loops

A loop inside a loop — for rows and columns:

```java
for (int row = 1; row <= 3; row++) {
    for (int col = 1; col <= 3; col++) {
        System.out.print("* ");
    }
    System.out.println();     // row finished, new line
}
```

```
* * *
* * *
* * *
```

Here `print` (not `println`) is in the inner loop and `println` is in the outer one — which is why the stars stay on one line and the line only breaks at the end of a row.

## Compile and run

```bash
javac LoopsExample.java
java WhileLoopExample          # the CLASS name, not the file name
```

## Gotchas

**1. `LoopsExample.java` contains a class named `WhileLoopExample`.** The two do not match, so running it requires `java WhileLoopExample`. Java allows this because the class is not `public` — the name of a `public` class **must** match the file name.

**2. The factorial in `ForWhileLoopExample.java` gives the wrong answer.** Look closely:

```java
int num = 5;
int fact = 1;
for (int i = 1; i <= num; i++) {
    i++;                  // <-- this extra increment is the problem
    fact = fact * i;
}
System.out.println("factorial = " + fact);   // prints 48, not 120
```

`i` is being incremented in two places — once in the body (`i++`) and once in the loop header. So the iterations land on 2, 4, 6 instead of 1, 2, 3:

| Iteration | `i` after the body's `i++` | `fact` |
| --- | --- | --- |
| 1 | 2 | 2 |
| 2 | 4 | 8 |
| 3 | 6 | 48 |

`5! = 120` is what we want. The fix is to remove the `i++` from the body:

```java
for (int i = 1; i <= num; i++) {
    fact = fact * i;      // 1*2*3*4*5 = 120
}
```

**Lesson: do not touch the loop variable inside the loop body.** Let the update in the header do its job.

**3. The first loop in `DoWhileLoopExample.java` runs even though the condition is false** — and this is not a bug, it is the entire point:

```java
int i = 10;
do {
    System.out.println("Hello World!");   // this DOES print once
    i++;
} while (i <= 5);                          // 11 <= 5 is false, exit
```

`i` starts out already greater than 5. A `while` loop would not have run at all; in a `do-while` the condition is checked **afterwards**, so the body is guaranteed to run once.

**4. Watch out for infinite loops.** Forget the update statement and the condition never becomes false:

```java
int i = 1;
while (i <= 10) {
    System.out.println(i);
    // forgot i++ → runs forever
}
```

If this happens, press `Ctrl + C` in the terminal.
