Maintaining  the code - 
debug , testing, bug fixes, refactoring
understandable , self explanatory, reusable code, extensible

This can be achieved by writing code in object oriented programming not procedural programming as solving DSA questions.


Object Oriented Programming
Inheritance 
Abstraction
Polymorphism
Encapsulation


Classes - Real world entities such as Mentor, Mentees, Instructor, Users, Batch , Assignments, Homework, Submission.

MVC - Model View Controller 
Controller class
Service Class
Utility Class

Single Responsibility Principle -
Any code entity has to focus on only one single responsibility. 
Use Inheritance to apply the above rule.


Use case of the abstract class 
When we know that there is a method which is common between all the child classes such that in each class it has different implementation , then we use the concept of abstract class. 

Class Bird {
	Abstract fly () {} 
} 

Class Eagle extends Bird {
fly() {
“Fly above 2000 ft”
}
}



Class Hen extends Bird {
fly() {
“Fly below 500 ft”
}
}

Any class which has at least one abstract method is termed as an abstract class.

Abstract method has to be common against all the child classes but it’s implementation can be different.

Any method which is termed as abstract in parent class needs to be added in child class. If not included , it gives a compilation error.

Logical meaning of abstract - It’s a concept or idea.

Creating an object of an abstract class is prohibited because abstract class has no implementation inside it. For Ex: Bird is an abstract class with fly() as the abstract method
Bird b = new Bird();
b.fly() —-> This is wrong because fly() method is not defined or elaborated what to do. —> compilation error.

Throw an exception if a class is not supposed to implement a method but is forced to do so .
This is a violation of the Liskov Substitution Principle(Design Principle). 
 To solve the above problem use “Interface”.

All methods should be called inside interface - set of behaviours
Difference between abstract class and interface — Important

Use case for abstract class - When classes share some common behavior
Use case for Interface - When you want to enforce structure only

For Example : 
Some birds like penguin , ostriches do not fly. So if we will make fly as an abstract method, it is enforced to add in all child classes which extend Bird class. 
But this problem can be solved if we do not make fly as abstract method , we make it an interface and implement it in the child classes where it is used. 

Use of abstraction

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

 What the abstract class does:
Provides common behavior like eat()

Forces child to implement some methods like makeSound()

Great for code reuse + enforcing structure

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

But in case of a Penguin, which cannot fly, we simply don't implement Fly:

class Penguin extends Bird {
  makeSound() {
    console.log("Penguin sound");
  }

  swim() {
    console.log("Swimming instead of flying");
  }
}

Questions 1 - 40+ OOPs Interview Questions and Answers (2025) - InterviewBit
Questions 2 - https://leetcode.com/discuss/post/4440061/part-2-top-16-oops-interview-questions-w-vw45/


SOLID Principles

Single Responsibility Principle
Litmus Test to check violation of single responsibility principle
1 - Many if/else conditions
2 - Code is not modular - everything written inside single function
3 - Unspecified utility / helper classes

Open close Principle
Open for extension
Closed for modification



