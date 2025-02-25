# Reading Head First Design Patterns

Content related to reading the book Head First Design Patterns, Second Edition.

The source code from the book can be downloaded from [Wickedly Smart - Head First Design Patterns](https://wickedlysmart.com/head-first-design-patterns).

## Object-oriented Programming

> Object-oriented programming (OOP) is a programming paradigm based on the concept of objects, which can contain data and code: data in the form of fields (often known as attributes or properties), and code in the form of procedures (often known as methods). In OOP, computer programs are designed by making them out of objects that interact with one another.  
Source: [Wikipedia - Object-oriented programming](https://en.wikipedia.org/wiki/Object-oriented_programming)

## OOP Basics

- Abstraction
- Encapsulation
- Polymorphism
- Inheritance

## OOP Design Principles

&#x262F; Identify the aspects of your application that vary and separate them from what stays the same.  
&#x262F; Program to an interface, not an implementation.  
&#x262F; Favour composition over inheritance.  
&#x262F; Strive for loosely coupled designs between objects that interact.  
&#x262F; Classes should be open for extension, but closed for modification.  

## OOP Design Patterns

> **Strategy**  
The strategy pattern defines a family of algorithms, encapsulates each one, and makes them interchangeable. Strategy lets the algorithm vary independently from clients that use it.

The strategy pattern is used in the `ducks` project part of this repository.

> **Observer**  
The observer pattern defines a on-to-many dependency between objects so that when one object changes state, all of its dependents are notified and updated automatically.

## Chapter 1 Welcome to Design Patterns: Intro to Design Patterns

### Sharpen Your Pencil - Inheritance Disadvantages

The ticked checkboxes indicates an disadvantages of using *inheritance* to provide Duck behaviour:

- [x] Code is duplicated across subclasses.
  - For example the overridden `fly()` method in `RubberDuck` and `DecoyDuck`, being identical.
- [x] Runtime behaviour changes are difficult.
  - The inheritance tree is typically set up statically at compile time.
- [ ] We can't make ducks dance.
  - False, we can add a `dance()` method if needed.
- [x] It's hard to gain knowledge of all duck behaviors.
  - We have to check every subclass for what behaviors being overridden.
- [ ] Ducks can't fly and quack at the same time.
  - False, a duck can both fly an quack, assuming our system supports parallelism.
- [x] Changes can unintentionally affect other ducks.
  - On example being when Joe by mistake made the rubber ducks able to fly.

### Sharpen Your Pencil - Change

Lots of things can drive change, some reasons are:

- My customers or users decide they want something else or, they want new functionality.
- My company decided it is going with another database vendor and it is also purchasing its data from another supplier that uses a different data format. Aargh!
- Well, technology changes and we’ve got to update our code to make use of protocols.
- We’ve learned enough building our system that we’d like to go back and do things a little better.
- There are new requirements incoming regarding security.
- An hardware component previously used have reached end of life, need to adapt to another component.
- A defect was discovered in a shared software component that we use and we need to upgrade to the new latest version.
- The number of users have increased and we need to optimize the performance of the software to keep up.

### Sharpen Your Pencil - Program to an Interface

- Using our new design, what would you do if you needed to add rocket-powered flying to the SimUDuck app?
  - Create a new class `FlyRocketPowered` that implements the `FlyBehaviour` interface, just as the existing classes `FlyWithWings` and `FlyNoWay`.
- Can you think of a class that might want to use the `Quack` behaviour that isn’t a duck?
  - One example is a duck call, a device that makes duck sounds.

### Design Puzzle - Game Characters

![Game characters class diagram](/resources/images/game-characters.png)

## Chapter 2 - Keeping your Objects in the Know: The Observer Pattern

### Sharpen Your Pencil - First Misguided Weather Station Implementation

Based on the first `WeatherData` implementation, which of the following apply?

- [X] We are coding to concrete implementations, not interfaces.
- [X] For every new display we’ll need to alter this code.
- [X] We have no way to add (or remove) display elements at runtime.
- [ ] The display elements don’t implement a common interface.
  - The `update` method is a common interface that all display elements have.
- [X] We haven’t encapsulated the part that changes.
- [ ] We are violating encapsulation of the `WeatherData` class.
  - False, since we only use the public interfaces of the `WeatherData` class.

### Sharpen Your Pencil - Weather Station Classes

![Weather station class diagram](/resources/images/weather-station.png)

## Chapter 3

### Sharpen Your Pencil - Double Mocha Soy Latte with Whip

![Double  Mocha Soy Latte with Whip](/resources/images/double-mocha-soy-latte-with-whip.png)