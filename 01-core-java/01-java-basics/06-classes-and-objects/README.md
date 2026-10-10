# 06 — Classes and Objects

OOP ki entry. Ab tak sab kuch `main` ke andar tha — ab apna khud ka type banayenge.

## Subfolders

| # | Folder | Kya cover hota hai |
| --- | --- | --- |
| 01 | [class-declaration](01-class-declaration) | Class kaise likhte hain — fields aur methods |
| 02 | [object-creation](02-object-creation) | `new` se object banana, `.` se fields access karna |

> Ye do alag folders me kyun hain? Dono files ke andar `class Student` declare hota hai. Ek hi folder me rakhte to `javac *.java` par **"duplicate class: Student"** error aata. Alag folders me rehne se dono independently compile ho jaati hain.

## Class vs Object

**Class** = blueprint / design. **Object** = us blueprint se banayi hui asli cheez.

Jaise ek ghar ka naksha (class) ek hi hota hai, par us naksha se kai ghar (objects) ban sakte hain — aur har ghar ka rang-roop apna.

```java
class Student {
    int age;              // field (state — object kya "hai")
    String name;
    String course;

    void study() {        // method (behaviour — object kya "karta hai")
        System.out.println("Student is studying");
    }
}
```

```java
Student s = new Student();    // object banaya
s.age = 20;                   // field me value daali
System.out.println(s.age);    // field padhi
s.study();                    // method call ki
```

## Key points

- **Field** = class ke andar, kisi method ke bahar declare kiya variable. Object ka data rakhta hai
- **Method** = object ka kaam. `void` ka matlab kuch return nahi karta
- `new Student()` memory me naya object banata hai aur uska address return karta hai
- `s` object nahi hai — `s` ek **reference** hai jo object ko point karta hai
- `.` (dot) operator se object ke fields aur methods tak pahunchte hain
- Ek class se jitne chaaho objects bana lo, har object ke fields apne-apne hote hain

## Fields ko default value milti hai

Ye [01-variables](../01-variables) ke `DefaultValue.java` se **ulta** hai — wahan local variable bina initialize use karne par compile error aata hai. Fields ke saath aisa nahi:

| Field ka type | Default value |
| --- | --- |
| `int`, `byte`, `short`, `long` | `0` |
| `float`, `double` | `0.0` |
| `char` | `'\u0000'` (blank dikhta hai) |
| `boolean` | `false` |
| `String` aur baaki objects | `null` |

Isliye `02-object-creation` me value set karne se *pehle* print karne par output aata hai:

```
0
null
```

Yaad rakhne ka tareeka: **local variables** ko initialize karna tumhari zimmedari hai; **fields** ko JVM object banate waqt zero/null se bhar deta hai.

## Naming convention

- Class ka naam `PascalCase` me — `Student`, `TestClass`
- Fields aur methods `camelCase` me — `studentName`, `study()`
- `public` class ka naam file ke naam se **exactly** match karna chahiye
