---
sidebar_position: 2
slug: class-properties
title: Kotlin Class Properties
---

Kotlin class properties are an essential aspect of object-oriented programming in Kotlin. They define the characteristics of an object. Kotlin provides a concise and powerful way to manage properties, including initialization blocks (`init`), and custom getters and setters. 

### 1. `init` Block

The `init` block is used to initialize class properties. It runs immediately after the primary constructor. You can have multiple `init` blocks in a class, and they will be executed in the order they appear.

#### **Syntax**:
```kotlin
class ClassName(val property1: Type, var property2: Type) {
    init {
        // Initialization code
    }
}
```

#### **Example**:
```kotlin
class Person(val name: String, var age: Int) {
    val isAdult: Boolean

    init {
        isAdult = age >= 18
        println("Person: $name, $age years old, is adult: $isAdult")
    }

}

fun main() {
    val person = Person("Tharun", 22)
    // Output: 
    // Person: Tharun, 22 years old, is adult: true
}
```

### 2. Getters and Setters

In Kotlin, properties can have custom getters and setters. By default, Kotlin provides a field with automatic getter and setter methods. You can override these to provide custom logic.

#### **Default Getters and Setters**:
By default, Kotlin generates getter and setter methods for mutable properties (`var`) and a getter for read-only properties (`val`).

#### **Example**:
```kotlin
class Person {
    var name: String = "Tharun"
    val age: Int = 25
}

fun main() {
    val person = Person()
    println(person.name) // Accesses the getter
    person.name = "Balaji" // Accesses the setter
    println(person.name)
    println(person.age) // Accesses the getter
    person.age = 30 // Error: Val cannot be reassigned
}
```

#### **Custom Getters and Setters**:
You can define custom getters and setters to add additional logic.

#### **Syntax**:
```kotlin
var property: Type
    get() = field
    set(value) {
        field = value
    }
```

#### **Example**:
```kotlin
class Person {
    var name: String = ""
        get() = field.toUpperCase() // Custom getter
        set(value) {
            field = value.trim() // Custom setter
        }

    var age: Int = 0
        get() = field
        set(value) {
            if (value > 0) {
                field = value
            } else {
                println("Age cannot be negative or zero")
            }
        }
}

fun main() {
    val person = Person()
    person.name = "   Tharun "
    println(person.name) // Output: THARUN

    person.age = 22
    println(person.age) // Output: 22

    person.age = -5 // Output: Age cannot be negative or zero
    println(person.age) // Output: 30
}
```



