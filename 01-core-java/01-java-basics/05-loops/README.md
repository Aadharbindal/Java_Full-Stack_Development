# 05 — Loops

Ek hi kaam baar-baar karwana, bina code repeat kiye.

## Files

| File | Class ka naam | Kya dikhata hai |
| --- | --- | --- |
| [LoopsExample.java](LoopsExample.java) | `WhileLoopExample` | `while` loop — hello 10 baar, sum of 1 to 5, multiplication table |
| [ForWhileLoopExample.java](ForWhileLoopExample.java) | `ForWhileLoopExample` | `for` loop, factorial attempt, nested `for` se star pattern |
| [DoWhileLoopExample.java](DoWhileLoopExample.java) | `DoWhileLoopExample` | `do-while` — condition false hone par bhi ek baar chalta hai |
| [ConBreak.java](ConBreak.java) | `ConBreak` | `break` loop todta hai, `continue` ek iteration skip karta hai |

## Teen loops, ek hi kaam

Har loop ke 3 hisse hote hain: **initialization**, **condition**, **update**.

```java
// while — hisse alag-alag likhe jaate hain
int i = 1;                    // init
while (i <= 10) {             // condition
    System.out.println(i);
    i++;                      // update
}

// for — teeno ek line me
for (int i = 1; i <= 10; i++) {
    System.out.println(i);
}

// do-while — condition BAAD me check hoti hai
int i = 1;
do {
    System.out.println(i);
    i++;
} while (i <= 10);
```

| Loop | Condition kab check hoti hai | Minimum kitni baar chalega | Kab use karo |
| --- | --- | --- | --- |
| `while` | pehle | 0 baar | Kitni baar chalega pata nahi |
| `for` | pehle | 0 baar | Count pata hai (1 se 10 tak) |
| `do-while` | baad me | **1 baar** | Menu — ek baar dikhana to hai hi |

## `break` vs `continue`

```java
for (int i = 1; i <= 10; i++) {
    if (i == 5) break;        // loop poora khatam → 1 2 3 4
    System.out.println(i);
}

for (int i = 1; i <= 10; i++) {
    if (i % 2 != 0) continue; // ye iteration skip → 2 4 6 8 10
    System.out.println(i);
}
```

`break` = bahar nikal jao. `continue` = ye round chhodo, agla shuru karo.

## Nested loops

Loop ke andar loop — rows aur columns ke liye:

```java
for (int row = 1; row <= 3; row++) {
    for (int col = 1; col <= 3; col++) {
        System.out.print("* ");
    }
    System.out.println();     // row khatam, nayi line
}
```

```
* * *
* * *
* * *
```

Yahan `print` (not `println`) inner loop me hai aur `println` outer me — isliye stars ek line me aate hain aur row ke end par line tootti hai.

## Compile & run

```bash
javac LoopsExample.java
java WhileLoopExample          # file ka naam nahi, CLASS ka naam
```

## Gotchas

**1. `LoopsExample.java` ke andar class ka naam `WhileLoopExample` hai.** Dono match nahi karte, isliye run karte waqt `java WhileLoopExample` likhna padega. Java me ye allowed hai kyunki class `public` nahi hai — `public` class ka naam file ke naam se match karna **compulsory** hota hai.

**2. `ForWhileLoopExample.java` ka factorial galat answer deta hai.** Ye dhyaan se dekho:

```java
int num = 5;
int fact = 1;
for (int i = 1; i <= num; i++) {
    i++;                  // <-- ye extra increment problem hai
    fact = fact * i;
}
System.out.println("factorial = " + fact);   // 48 aata hai, 120 nahi
```

`i` do jagah badh raha hai — ek body me (`i++`), ek loop header me. To iteration 1, 2, 3 ke bajaye 2, 4, 6 par chalti hai:

| Iteration | body me `i++` ke baad | `fact` |
| --- | --- | --- |
| 1 | 2 | 2 |
| 2 | 4 | 8 |
| 3 | 6 | 48 |

`5! = 120` chahiye. Fix: body se `i++` hata do —

```java
for (int i = 1; i <= num; i++) {
    fact = fact * i;      // 1*2*3*4*5 = 120
}
```

**Lesson: loop variable ko loop ke body me mat chhedo.** Header me jo update likha hai, usi ko kaam karne do.

**3. `DoWhileLoopExample.java` me pehla loop condition false hone par bhi chalta hai** — aur ye bug nahi, pura point hai:

```java
int i = 10;
do {
    System.out.println("Hello World!");   // ek baar print HOTA hai
    i++;
} while (i <= 5);                          // 11 <= 5 false, exit
```

`i` shuru se hi 5 se bada hai. `while` loop hota to ek baar bhi na chalta; `do-while` me condition **baad** me check hoti hai, isliye body guaranteed ek baar chalti hai.

**4. Infinite loop se bacho.** Update statement bhool gaye to condition kabhi false nahi hogi:

```java
int i = 1;
while (i <= 10) {
    System.out.println(i);
    // i++ bhool gaye → hamesha chalega
}
```

Aisa ho jaye to terminal me `Ctrl + C` dabao.
