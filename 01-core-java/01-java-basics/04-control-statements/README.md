# 04 — Control Statements

Decision making: condition ke hisaab se program ka raasta badalna.

## Files

| File | Kya dikhata hai | Output |
| --- | --- | --- |
| [IfElseCode.java](IfElseCode.java) | Simple `if-else` — pass/fail, aur `%` se even/odd check | `pass`, `end`, `even` |
| [IfElseCode02.java](IfElseCode02.java) | `else-if` ladder — marks se grade nikalna | `Grade A+` |
| [NestedIfExample.java](NestedIfExample.java) | Nested `if` — login check (username ke andar password) | `Wrong password` |
| [SwitchExample.java](SwitchExample.java) | `switch` — day number se din ka naam | `Monday` |

## Key points

**`if-else`** — do raaste, ek chalega:

```java
if (marks >= 45) {
    System.out.println("pass");
} else {
    System.out.println("fail");
}
```

**`else-if` ladder** — bahut si conditions, par **sirf pehli matching** chalti hai aur baaki skip ho jaati hain. Isliye order important hai: `>= 90` ko `>= 75` se pehle check karna padega, warna 90 marks bhi "Grade A" me chale jayenge.

**Nested `if`** — ek `if` ke andar dusra `if`. Outer condition true ho tabhi inner check hoti hai.

**`switch`** — ek hi variable ki kai exact values compare karni hon to `else-if` ladder se saaf dikhta hai:

```java
switch (day) {
    case 1:  System.out.println("Monday"); break;
    case 2:  System.out.println("Tuesday"); break;
    default: System.out.println("Invalid day");
}
```

- `break` zaruri hai — warna **fall-through** ho jaata hai (matching case ke baad neeche ke sab cases bhi chal jaate hain)
- `default` optional hai, par rakhna accha hai — koi case match na ho to wo chalta hai
- `switch` sirf `int`-compatible types, `char`, `String`, aur `enum` par kaam karta hai — `boolean` par nahi

## `if-else` vs `switch`

| Use `if-else` jab | Use `switch` jab |
| --- | --- |
| Range check karni ho (`marks >= 90`) | Exact value match karni ho (`day == 1`) |
| Conditions alag-alag variables par hon | Ek hi variable ki kai values hon |
| Complex `&&` / `\|\|` logic ho | Values ki list flat ho |

## Compile & run

```bash
javac SwitchExample.java
java SwitchExample
```

## Gotchas

**1. `NestedIfExample.java` me `String` comparison galat tareeke se hui hai.** Ye sabse important lesson hai is folder ka:

```java
if (username == "genie")      // GALAT tareeka
```

`==` references compare karta hai — "kya ye dono *wahi ek* object hain?" — content nahi. Yahan ye **accidentally** kaam kar jaata hai, kyunki `"genie"` ek string literal hai aur Java literals ko String Pool me reuse karta hai, isliye dono taraf same object hai.

Par scanner se input lo, ya `new String("genie")` banao, to turant toot jaata hai:

```java
String username = new String("genie");
System.out.println(username == "genie");        // false  (alag object)
System.out.println(username.equals("genie"));   // true   (same content)
```

**Rule: `String` compare karne ke liye hamesha `.equals()` use karo.** Sahi version:

```java
if (username.equals("genie")) {
    if (password.equals("123")) { ... }
}
```

Is file ka output `Wrong password` hai, kyunki `password` me `"1231"` set hai par `"123"` se compare ho raha hai.

**2. `IfElseCode02.java` me ek dead statement hai.** `Grade B` branch ke andar:

```java
else if (marks >= 60) {
    System.out.println("Grade B");
    marks = 40;                    // iska koi fayda nahi
}
```

`marks` ko yahan badalne se kuch nahi hota — `else-if` ladder already decide kar chuki hai, aur uske baad `marks` dobara use hi nahi hota. Ye dikhane ke liye tha ki ladder **ek baar** match karke exit ho jaati hai, dobara top se check nahi karti. Is run me ye branch chalti bhi nahi (`marks = 90` hai, to `Grade A+` par hi ladder khatam).

**3. `if` ke saath braces hamesha lagao.** Bina braces `if` sirf agli *ek* statement ko control karta hai — baad me koi line add karne par silent bug ban jaata hai.
