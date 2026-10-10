# 00 — Getting Started

Sabse pehla step: ek Java program ka structure, aur ye samajhna ki statements upar se neeche, ek-ek karke chalti hain.

## Files

| File | Kya dikhata hai |
| --- | --- |
| [Test.java](Test.java) | Minimal program — ek variable banao aur `System.out.println` se 3 baar print karo |
| [ControlStatements.java](ControlStatements.java) | Sequential execution — 5 print statements apne likhe hue order me hi chalti hain |

## Key points

- Har program ek class ke andar hota hai: `class Test { ... }`
- Program chalta hai `main` method se: `public static void main(String[] args)`
- JVM `main` ko hi dhundhta hai, isliye signature exactly yahi hona chahiye
- `System.out.println(...)` print karke next line par chala jaata hai; `System.out.print(...)` line nahi todta
- Statements ka order = execution ka order. Jo pehle likha hai wo pehle chalega

## Compile & run

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

`ControlStatements.java` naam se lagta hai ki `if`/`switch` hoga, par usme sirf print statements hain. Ye deliberately hai: "control statements" padhne se pehle ye dikhana tha ki **bina** kisi control statement ke flow bilkul straight hota hai. Asli `if`/`switch` [04-control-statements](../04-control-statements) me hain.
