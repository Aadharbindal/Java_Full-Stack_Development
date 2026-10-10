# 06.01 — Class Declaration

Pehla step: class likhna. Yahan sirf blueprint banta hai — object abhi nahi.

## File

| File | Kya dikhata hai |
| --- | --- |
| [Student.java](Student.java) | `Student` class — 3 fields aur 1 method |

```java
class Student {
    int age;
    String name;
    String course;

    void study() {
        System.out.println("Student is studying");
    }
}
```

## Key points

- Class ke andar do cheezein hain: **fields** (`age`, `name`, `course`) aur **method** (`study()`)
- Fields class level par hain, kisi method ke andar nahi — isliye ye object ki state banti hain
- Is file me `main` method **nahi** hai, isliye ye run nahi hogi — sirf compile hogi

## Compile

```bash
javac Student.java
```

`Student.class` ban jayegi. Run karne ki koshish karo to:

```bash
java Student
# Error: Main method not found in class Student
```

Ye expected hai. Chalane ke liye `main` wali class chahiye — wo [02-object-creation](../02-object-creation) me hai.

## Note

Original class folder me is file ki ek exact copy `Main.java` naam se bhi thi (bas ek extra blank line ka fark). Duplicate thi, isliye yahan nahi rakhi — ek hi class ko do naam se rakhne ka koi fayda nahi tha, aur ek saath compile karne par "duplicate class" error aata.
