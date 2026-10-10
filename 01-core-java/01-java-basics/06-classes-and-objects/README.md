# 06 — Classes and Objects

The entry point into OOP. Everything so far lived inside `main` — now we define our own type.

## Subfolders

| # | Folder | What it covers |
| --- | --- | --- |
| 01 | [class-declaration](01-class-declaration) | How to write a class — fields and methods |
| 02 | [object-creation](02-object-creation) | Creating objects with `new`, accessing fields with `.` |

> Why are these in two separate folders? Both files declare a class named `Student`. Keeping them in one folder would make `javac *.java` fail with **"duplicate class: Student"**. In separate folders each one compiles independently.

## Class vs object

A **class** is a blueprint or design. An **object** is an actual thing built from that blueprint.

Think of the plan for a house: there is one plan (the class), but many houses (objects) can be built from it — and each house has its own colour and condition.

```java
class Student {
    int age;              // field (state — what the object "has")
    String name;
    String course;

    void study() {        // method (behaviour — what the object "does")
        System.out.println("Student is studying");
    }
}
```

```java
Student s = new Student();    // create an object
s.age = 20;                   // assign a value to a field
System.out.println(s.age);    // read the field
s.study();                    // call the method
```

## Key points

- A **field** is a variable declared inside the class but outside any method. It holds the object's data
- A **method** is what the object does. `void` means it returns nothing
- `new Student()` creates a new object in memory and returns its address
- `s` is not the object — `s` is a **reference** that points to the object
- The `.` (dot) operator reaches the object's fields and methods
- Any number of objects can be created from one class, and each object has its own copy of the fields

## Fields get default values

This is the **opposite** of `DefaultValue.java` in [01-variables](../01-variables), where using an uninitialized local variable is a compile error. Fields do not behave that way:

| Field type | Default value |
| --- | --- |
| `int`, `byte`, `short`, `long` | `0` |
| `float`, `double` | `0.0` |
| `char` | `'\u0000'` (appears blank) |
| `boolean` | `false` |
| `String` and other objects | `null` |

That is why printing them *before* assigning anything in `02-object-creation` gives:

```
0
null
```

An easy way to remember it: initializing **local variables** is your responsibility; **fields** are filled with zero/null by the JVM when the object is created.

## Naming conventions

- Class names in `PascalCase` — `Student`, `TestClass`
- Fields and methods in `camelCase` — `studentName`, `study()`
- A `public` class name must match the file name **exactly**
