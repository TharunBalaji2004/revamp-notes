---
sidebar_position: 4
slug: oops-concepts
title: OOPS Concepts
---

Kotlin supports various Object-Oriented Programming (OOP) concepts, enabling you to design and implement systems in a structured and maintainable way. Here’s an overview of key OOP concepts in Kotlin:

### 1. **Objects**

- **Objects**: Singletons that are used to hold properties and methods. Objects need not to be initialized and can be accessed directly. They are created using the `object` keyword.

  #### **Example**:
  ```kotlin
  object DatabaseConnection {
      fun connect() {
          println("Connecting to the database...")
      }
  }

  fun main() {
      DatabaseConnection.connect() // Output: Connecting to the database...
  }
  ```

### 2. **Inheritance**

- **Inheritance**: Allows a class to inherit properties and methods from another class. The `open` keyword is used to make a class inheritable, and the `:` symbol is used to indicate inheritance.

:::info
By default, Kotlin classes are final and cannot be inherited (or) extended. So `open` keyword should specified for classes and functions for inheritance.
::: 

  #### **Example**:
  ```kotlin
  open class Animal(val name: String) {
      open fun makeSound() {
          println("Some generic sound")
      }
  }

  class Dog(name: String) : Animal(name) {
      override fun makeSound() {
          println("Bark")
      }
  }

  fun main() {
      val dog = Dog("Buddy")
      dog.makeSound() // Output: Bark
  }
  ```

### 3. **Polymorphism**

- **Polymorphism**: Allows objects to be treated as instances of their parent class. The actual method that is called is determined at runtime, making it possible to call overridden methods in child classes.

  #### **Example**:
  ```kotlin
  open class Animal {
      open fun makeSound() {
          println("Some sound")
      }
  }

  class Cat : Animal() {
      override fun makeSound() {
          println("Meow")
      }
  }

  fun main() {
      val animal: Animal = Cat()
      animal.makeSound() // Output: Meow
  }
  ```

### 4. **Encapsulation**

- **Encapsulation**: Hides the internal state of an object and requires all interaction to be performed through an object's methods. This is achieved using access modifiers (`private`, `protected`, `public`).

  #### **Example**:
  ```kotlin
  class Person(private var name: String) {
      fun getName(): String {
          return name
      }

      fun setName(newName: String) {
          name = newName
      }
  }

  fun main() {
      val person = Person("Alice")
      println(person.getName()) // Output: Alice
      person.setName("Bob")
      println(person.getName()) // Output: Bob
  }
  ```

### 5. **Abstraction**

- **Abstraction**: Allows you to define abstract classes and interfaces that provide a common interface for a group of related classes. Abstract classes cannot be instantiated directly.

  #### **Example**:
  ```kotlin
  abstract class Vehicle {
      abstract fun start()
      fun stop() {
          println("Vehicle stopped")
      }
  }

  class Car : Vehicle() {
      override fun start() {
          println("Car started")
      }
  }

  fun main() {
      val car = Car()
      car.start() // Output: Car started
      car.stop()  // Output: Vehicle stopped
  }
  ```

  #### **Example with Interface**:
  ```kotlin
  interface Drawable {
      fun draw()
  }

  class Circle : Drawable {
      override fun draw() {
          println("Drawing a circle")
      }
  }

  fun main() {
      val circle = Circle()
      circle.draw() // Output: Drawing a circle
  }
  ```

