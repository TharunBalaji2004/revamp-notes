---
sidebar_position: 1
slug: kotlin-class
title: Kotlin Class
---


In Kotlin, classes and objects are fundamental building blocks for object-oriented programming (OOP). They allow you to create complex data structures and model real-world entities with properties and behaviors.

### 1. Classes & Object Creation

A class is a blueprint for creating objects (instances). It defines properties and methods that the created objects will have. 

#### **Defining a Simple Class**

To define a class in Kotlin, use the `class` keyword followed by the class name.

#### **Syntax**:
```kotlin
class ClassName {
    // Properties and methods
}
```

#### **Example**:
```kotlin
class Person {
    var name: String = ""
    var age: Int = 0

    fun introduce() {
        println("Hello, my name is $name and I am $age years old.")
    }
}

fun main() {
    val person = Person()
    person.name = "John"
    person.age = 25
    person.introduce() // Output: Hello, my name is John and I am 25 years old.
}
```

### 2. Primary Constructor

Kotlin allows you to define a primary constructor directly in the class header.

#### **Syntax**:
```kotlin
class ClassName(val property1: Type, var property2: Type) {
    // Initializer block and other properties and methods
}
```

#### **Example**:
```kotlin
class Person(val name: String, var age: Int)

fun main() {
    val person = Person("Alice", 30)
    println("${person.name} is ${person.age} years old.") // Output: Alice is 30 years old.
}
```


### 3. Secondary Constructors

A class can also have secondary constructors using the `constructor` keyword. Secondary constructors are useful when you need multiple ways to initialize a class.

#### **Example**:
```kotlin
class Person {
    var name: String
    var age: Int

    constructor(name: String) {
        this.name = name
        this.age = 0
    }

    constructor(name: String, age: Int) {
        this.name = name
        this.age = age
    }
}

fun main() {
    val person1 = Person("Charlie")
    val person2 = Person("Diana", 35)
    println("${person1.name} is ${person1.age} years old.") // Output: Charlie is 0 years old.
    println("${person2.name} is ${person2.age} years old.") // Output: Diana is 35 years old.
}
```
s