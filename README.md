# Java Full Stack Development

Mera Java Full Stack Development course ka practice repository. Jo classes me padhaya jaata hai, wahi code topic-wise organise karke yahan rakhta hoon — taaki revision ke time seedha folder kholo aur topic mil jaaye.

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

Numbering seekhne ke order me hai, isliye folder listing hi course ka flow dikha deti hai. Jaise aage ke topics padhte jayenge, naye numbered folders add hote rahenge (`02-advanced-java`, `03-spring`, etc.).

## How to compile and run

Har program ek standalone file hai. JDK install hone ke baad kisi bhi topic folder me jaake:

```bash
javac VariableExample01.java
java VariableExample01
```

Dhyaan rakhna: `java` command ke saath **class ka naam** dete hain, file ka naam nahi. Kuch files me class ka naam file ke naam se match nahi karta (puraane class notes me aisa hua tha) — aise cases topic README me note kiye hue hain.

Poore folder ko ek saath compile karna ho:

```bash
javac *.java
```

## Conventions

- Source files sirf `.java` — compiled `.class` files commit nahi karte (dekho [.gitignore](.gitignore)).
- Ek topic = ek folder, aur us folder me ek `README.md` jo batata hai kis file me kya hai.
- Class me likha code jaisa hai waisa hi rakha hai, formatting badli nahi — kuch files me jaan-boojh kar errors ya tricky output hai (sikhane ke liye), unhe topic README me explain kiya hai.

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
