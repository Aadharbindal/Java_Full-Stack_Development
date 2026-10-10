# Java Full Stack Development

Practice repository for my Java Full Stack Development course. Everything taught in class is organised here topic-wise, so revision is just a matter of opening the right folder.

## Repository structure

```
Java_Full-Stack_Development/
└── 01-core-java/
    └── 01-java-basics/
        ├── 00-getting-started/        First programs, sequential execution
        ├── 01-variables/              Declaration, initialization, naming rules
        ├── 02-data-types/             Primitives, ranges, String
        ├── 03-operators/              Arithmetic, relational, logical, unary, ternary
        ├── 04-control-statements/     if / else-if / nested if / switch
        ├── 05-loops/                  while, for, do-while, break & continue
        └── 06-classes-and-objects/    Class declaration, object creation
```

Folders are numbered in learning order, so the directory listing itself shows the course flow. New numbered folders get added as the course moves forward (`02-advanced-java`, `03-spring`, and so on).

## How to compile and run

Every program is a standalone file. Once a JDK is installed, go into any topic folder:

```bash
javac VariableExample01.java
java VariableExample01
```

Note that the `java` command takes the **class name**, not the file name. In a few files the class name does not match the file name (that is how it was written in class) — those cases are called out in the topic README.

To compile a whole folder at once:

```bash
javac *.java
```

## Conventions

- Only `.java` sources are committed — compiled `.class` files are not (see [.gitignore](.gitignore)).
- One topic per folder, and each folder has a `README.md` explaining what each file does.
- Class code is kept exactly as written, with no reformatting. Some files contain deliberate errors or tricky output for teaching purposes; those are explained in the topic README.

## Topic index

| Module | Topic | Files |
| --- | --- | --- |
| Core Java | [Getting started](01-core-java/01-java-basics/00-getting-started) | 2 |
| Core Java | [Variables](01-core-java/01-java-basics/01-variables) | 4 |
| Core Java | [Data types](01-core-java/01-java-basics/02-data-types) | 2 |
| Core Java | [Operators](01-core-java/01-java-basics/03-operators) | 6 |
| Core Java | [Control statements](01-core-java/01-java-basics/04-control-statements) | 4 |
| Core Java | [Loops](01-core-java/01-java-basics/05-loops) | 4 |
| Core Java | [Classes and objects](01-core-java/01-java-basics/06-classes-and-objects) | 2 |
