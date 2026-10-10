# 06.02 — Object Creation

Ab blueprint se asli object banate hain aur use karte hain.

## File

| File | Kya dikhata hai |
| --- | --- |
| [TestClass.java](TestClass.java) | `Student` class + `public class TestClass` jisme `main` hai — object banana aur fields access karna |

```java
Student s = new Student();     // object creation

System.out.println(s.age);     // 0      — default value
System.out.println(s.name);    // null   — default value

s.age = 20;                    // value set ki
s.name = "Amit";

System.out.println(s.age);     // 20
System.out.println(s.name);    // Amit
```

## Expected output

```
0
null
20
Amit
```

## Compile & run

```bash
javac TestClass.java
java TestClass
```

Dhyaan do — ek hi `.java` file se **do** class files banti hain: `Student.class` aur `TestClass.class`. Ek file me kai classes ho sakti hain, par `public` sirf ek hi ho sakti hai, aur usi ka naam file ke naam se match karna chahiye.

## Key points

- `new Student()` memory (heap) me naya object banata hai
- `s` object nahi, ek **reference variable** hai jo object ka address rakhta hai
- `.` operator se object ke andar jaate hain: `s.age`, `s.name`, `s.study()`
- Ek class se kai objects ban sakte hain, aur sabke fields independent hote hain:

```java
Student s1 = new Student();
Student s2 = new Student();
s1.name = "Amit";
s2.name = "Rahul";
// s1.name aur s2.name ek dusre ko affect nahi karte
```

## Gotchas

**1. Set karne se pehle fields print karne par `0` aur `null` aate hain, error nahi.** Fields ko JVM default value deta hai. Ye local variables se ulta hai — [01-variables/DefaultValue.java](../../01-variables/DefaultValue.java) bina initialize kiye use karne par **compile error** deta hai.

**2. `s.study()` is file me call hi nahi hui.** Method class me defined hai par `main` me use nahi kiya gaya. Khud add karke dekho:

```java
s.study();      // Student is studying
```

**3. `null` par `.` lagane se crash hota hai.** `s.name` abhi `null` hai, to:

```java
System.out.println(s.name.length());   // NullPointerException
```

Ye Java ka sabse common runtime error hai — `null` reference par koi method call nahi kar sakte. Isliye object ke fields use karne se pehle set karna zaruri hai.
