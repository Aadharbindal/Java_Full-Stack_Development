# 01 — Variables

Variable = memory me ek named box jisme value rakhi jaati hai.

## Files

| File | Kya dikhata hai |
| --- | --- |
| [VariableExample01.java](VariableExample01.java) | Declaration aur initialization alag-alag: `int age;` phir `age=20;` |
| [VariableExample02.java](VariableExample02.java) | Value reassign karna — ek hi variable me nayi value daalo, purani chali jaati hai |
| [VariableExample03.java](VariableExample03.java) | Naming rules — `age1`, `student_marks`, `$sal`, `studentName` sab valid hain |
| [DefaultValue.java](DefaultValue.java) | **Compile error** — local variable ko bina initialize kiye use karna |

## Key points

Variable use karne ke do steps hote hain:

```java
int age;      // 1. declaration — type aur naam bata diya
age = 20;     // 2. initialization — value de di
```

Dono ek line me bhi ho sakte hain: `int age = 20;`

**Naming rules:**

- Letter, `_` ya `$` se shuru ho sakta hai — digit se **nahi**
- Beech me letters, digits, `_`, `$` chal jaate hain
- Spaces aur keywords (`int`, `class`, `for`...) allowed nahi
- Case-sensitive hai: `age` aur `Age` do alag variables hain
- Convention: `camelCase` use karo (`studentName`, na `student_name` na `StudentName`)

## Gotchas

**`DefaultValue.java` compile hi nahi hoga** — aur ye hi iska point hai:

```java
int age;
System.out.println(age);   // error: variable age might not have been initialized
```

**Local variables ko Java default value nahi deta.** Method ke andar banaya variable use karne se pehle initialize karna *compulsory* hai. Fields (class ke andar, method ke bahar) ko default value milti hai — `int` ko `0`, `boolean` ko `false`, object references ko `null`. Wo difference [06-classes-and-objects](../06-classes-and-objects) me dikhta hai, jahan `s.age` print karne par `0` aata hai.

Error khud dekhne ke liye:

```bash
javac DefaultValue.java
```

`VariableExample03.java` me `$sal` aur `student_marks` declare hote hain par print nahi hote — sirf naming dikhane ke liye likhe the. Compile warning nahi aayegi, unused local variables Java me allowed hain.
