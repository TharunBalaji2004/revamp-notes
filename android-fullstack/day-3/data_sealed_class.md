---
sidebar_position: 3
slug: data-sealed-class
title: Data & Sealed Class
---


## Data Classes

Data classes in Kotlin are used primarily to hold data. They automatically generate several useful methods, including `equals()`, `hashCode()`, `toString()`, `copy()`, and component functions for destructuring declarations. This reduces boilerplate code and makes the class more readable and maintainable.

### Defining a Data Class

To define a data class, use the `data` keyword before the class declaration. A data class must have at least one primary constructor parameter.

#### **Syntax**:
```kotlin
data class ClassName(val property1: Type, var property2: Type)
```

#### **Example**:
```kotlin
data class User(val name: String, val age: Int)

fun main() {
    val user1 = User("Tharun", 30)
    val user2 = User("Tharun", 30)

    println(user1) // Output: User(name=Tharun, age=30)

    println(user1 == user2) // Output: true

    println(user1.hashCode() == user2.hashCode()) // Output: true

    val user3 = user1.copy(name = "Balaji")
    println(user3) // Output: User(name=Balaji, age=30)

    // Destructuring declaration
    val (name, age) = user1
    println("Name: $name, Age: $age") // Output: Name: Tharun, Age: 30
}
```

### Copy Function

The `copy()` function allows you to create a copy of an object with some properties modified.

#### **Example**:
```kotlin
data class User(val name: String, val age: Int)

fun main() {
    val user1 = User("Tharun", 22)
    val user2 = user1.copy(age = 35)
    println(user2) // Output: User(name=Tharun, age=35)
}
```

## Sealed Classes

Sealed classes are used to represent restricted class hierarchies. They are useful when you have a fixed set of types that you want to represent. Sealed classes ensure that all subclasses are known at compile-time and are defined within the same file.

### Defining a Sealed Class

To define a sealed class, use the `sealed` keyword before the class declaration. Subclasses must be defined within the same file.

#### **Syntax**:
```kotlin
sealed class ClassName {
    // Subclasses
}
```

#### **Example**:
```kotlin
sealed class Shape {
    class Circle(val radius: Double) : Shape()
    class Rectangle(val width: Double, val height: Double) : Shape()
    class Sqaure(val side: Double) : Shape()
}

fun describeShape(shape: Shape): String {
    return when (shape) {
        is Shape.Circle -> "Circle with radius ${shape.radius}"
        is Shape.Rectangle -> "Rectangle with width ${shape.width} and height ${shape.height}"
        is Shape.Sqaure -> "Sqaure with side ${shape.side}"
    }
}

fun main() {
    val circle = Shape.Circle(3.0)
    val rectangle = Shape.Rectangle(4.0, 5.0)
    val sqaure = Shape.Sqaure(5.0)

    println(describeShape(circle)) // Output: Circle with radius 3.0
    println(describeShape(rectangle)) // Output: Rectangle with width 4.0 and height 5.0
    println(describeShape(sqaure)) // Output: Sqaure with side 5.0
}
```

### Advantages of Sealed Classes

1. **Exhaustive `when` Expressions**: When you use a sealed class in a `when` expression, the compiler knows all possible subclasses and can ensure that all cases are handled, making the code safer and more robust.
   
2. **Type Safety**: Since all subclasses are known at compile-time, it provides better type safety and ensures that you can't accidentally introduce a new subclass in a different file.

3. **Hierarchical Structure**: Sealed classes provide a structured way to represent a hierarchy of types with specific behaviors, making the code more organized and easier to understand.

