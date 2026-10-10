# 06.01 — Class Declaration

The first step: writing a class. This only creates the blueprint — no object yet.

## File

| File | What it shows |
| --- | --- |
| [Student.java](Student.java) | The `Student` class — three fields and one method |

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

- The class contains two kinds of things: **fields** (`age`, `name`, `course`) and a **method** (`study()`)
- The fields are at class level, not inside any method — which is what makes them the object's state
- This file has no `main` method, so it will not run — it will only compile

## Compile

```bash
javac Student.java
```

This produces `Student.class`. Trying to run it gives:

```bash
java Student
# Error: Main method not found in class Student
```

That is expected. Running requires a class with `main`, which is in [02-object-creation](../02-object-creation).

## Note

The original class folder also contained an exact copy of this file named `Main.java` (differing only by one extra blank line). It was a duplicate, so it is not kept here — there was no value in having the same class under two names, and compiling both together would cause a "duplicate class" error.
