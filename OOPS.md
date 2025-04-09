# Why System Design is Important

System design is important to ensure that code is:

- Easily **debuggable**
- Supports proper **testing**, **bug fixes**, and **refactoring**
- **Understandable** and **self-explanatory**
- **Reusable** and **extensible**

---

## How Can This Be Achieved?

This can be achieved by writing code using **Object-Oriented Programming (OOP)** instead of procedural programming (like in most DSA problems).

---

## Object-Oriented Programming Concepts

- **Inheritance**
- **Abstraction**
- **Polymorphism**
- **Encapsulation**

### Real-World Examples (Classes):

- `Mentor`
- `Mentees`
- `Instructor`
- `Users`
- `Batch`
- `Assignments`
- `Homework`
- `Submission`

---

## MVC Architecture

- **Model-View-Controller**
  - `Controller` class
  - `Service` class
  - `Utility` class

---

## Design Principles

### Single Responsibility Principle

> Any code entity should have only **one single responsibility**.

Use **inheritance** to apply this principle effectively.

---

## Use Case of Abstract Class

When there's a method that is **common among all child classes**, but its **implementation differs**, use an **abstract class**.

### Example:

```java
abstract class Bird {
  abstract void fly();
}

class Eagle extends Bird {
  void fly() {
    System.out.println("Fly above 2000 ft");
  }
}

class Hen extends Bird {
  void fly() {
    System.out.println("Fly below 500 ft");
  }
}
```

### Key Notes:
- Any class with at least **one abstract method** is an **abstract class**.
- An **abstract method** must be implemented in all child classes.
- If not implemented, it causes a **compilation error**.
- You **cannot instantiate** an abstract class:

```java
Bird b = new Bird(); // ❌ Compilation error
```

Because `fly()` is abstract and not defined.

---

## Interface vs Abstract Class

If a class is forced to implement a method that it shouldn’t (e.g., a bird that can’t fly), it **violates Liskov Substitution Principle**.

To solve this:  
✅ Use an **Interface** instead.

---

### When to Use:

- **Abstract Class** → When multiple classes **share some behavior**
- **Interface** → When you want to **enforce structure/behavior** only

---

### Real-World Example: Birds That Can’t Fly

Some birds like **penguins** or **ostriches** cannot fly.

If `fly()` is an abstract method in `Bird`, then **all** child classes must implement it—even those that shouldn't.

### Better Solution:

- Create a `Fly` interface and only implement it in the birds that can fly.

---

## Use of Abstraction in TypeScript / JavaScript

```ts
abstract class Bird {
  abstract makeSound(): void;

  eat() {
    console.log("Peck peck");
  }
}

class Penguin extends Bird {
  makeSound() {
    console.log("Penguin sound");
  }

  swim() {
    console.log("Penguin swims");
  }
}
```

### What the Abstract Class Does:

- Provides common behavior (`eat()`)
- Forces child to implement certain methods (`makeSound()`)

✅ Good for **code reuse** + **enforcing structure**

---

## Using Interface

```ts
interface Fly {
  fly(): void;
}

class Sparrow extends Bird implements Fly {
  makeSound() {
    console.log("Chirp chirp");
  }

  fly() {
    console.log("Flying high!");
  }
}
```

### For Penguins That Don’t Fly:

```ts
class Penguin extends Bird {
  makeSound() {
    console.log("Penguin sound");
  }

  swim() {
    console.log("Swimming instead of flying");
  }
}
```

---

## Reference Questions

- **[InterviewBit: 40+ OOPs Interview Questions and Answers (2025)](https://www.interviewbit.com)**
- **[LeetCode OOPs Questions – Part 2 (Top 16)](https://leetcode.com/discuss/post/4440061/part-2-top-16-oops-interview-questions-w-vw45/)**
