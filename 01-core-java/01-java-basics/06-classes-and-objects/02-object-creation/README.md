# 06.02 — Object Creation

Now we build an actual object from the blueprint and use it.

## File

| File | What it shows |
| --- | --- |
| [TestClass.java](TestClass.java) | The `Student` class plus `public class TestClass` containing `main` — creating an object and accessing its fields |

```java
Student s = new Student();     // object creation

System.out.println(s.age);     // 0      — default value
System.out.println(s.name);    // null   — default value

s.age = 20;                    // assign values
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

## Compile and run

```bash
javac TestClass.java
java TestClass
```

Note that this single `.java` file produces **two** class files: `Student.class` and `TestClass.class`. One file can hold several classes, but only one of them can be `public`, and that one's name must match the file name.

## Key points

- `new Student()` creates a new object in memory (on the heap)
- `s` is not the object but a **reference variable** holding the object's address
- The `.` operator reaches inside the object: `s.age`, `s.name`, `s.study()`
- Many objects can be created from one class, and their fields are independent:

```java
Student s1 = new Student();
Student s2 = new Student();
s1.name = "Amit";
s2.name = "Rahul";
// s1.name and s2.name do not affect each other
```

## Gotchas

**1. Printing the fields before assigning gives `0` and `null`, not an error.** The JVM assigns default values to fields. This is the opposite of local variables — [01-variables/DefaultValue.java](../../01-variables/DefaultValue.java) gives a **compile error** when used without initialization.

**2. `s.study()` is never called in this file.** The method is defined in the class but not used in `main`. Try adding it:

```java
s.study();      // Student is studying
```

**3. Calling `.` on `null` crashes.** `s.name` is still `null` at that point, so:

```java
System.out.println(s.name.length());   // NullPointerException
```

This is the single most common runtime error in Java — no method can be called on a `null` reference. Which is why an object's fields need to be set before they are used.
