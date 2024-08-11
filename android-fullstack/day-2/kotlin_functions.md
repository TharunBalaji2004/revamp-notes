---
sidebar_position: 3
slug: kotlin-functions
title: Kotlin Functions
---

## 1. Simple Functions

Simple functions in Kotlin are declared using the `fun` keyword. They can take parameters and return a value.

### **Syntax**:
```kotlin
fun functionName(parameter1: Type, parameter2: Type): ReturnType {
    // Function body
    return value
}
```

### **Example**:
```kotlin
fun add(a: Int, b: Int): Int {
    return a + b
}

fun main() {
    val result = add(3, 5)
    println(result) // Output: 8
}
```

## 2. Compact or Single-Line Functions

Kotlin allows you to define functions in a more concise way using single-line expressions. If the function consists of a single expression, you can omit the braces and the `return` keyword.

### **Syntax**:
```kotlin
fun functionName(parameter1: Type, parameter2: Type): ReturnType = expression
```

### **Example**:
```kotlin
fun multiply(a: Int, b: Int): Int = a * b

fun main() {
    val result = multiply(4, 5)
    println(result) // Output: 20
}
```

## 3. Lambda Expressions

Lambda expressions are anonymous functions that can be treated as values. They are defined using curly braces `{}` and can be passed as arguments to higher-order functions.

### 1. Basic Lambda Expression

A lambda expression in Kotlin is defined using curly braces `{}` and can take parameters and return a value. The parameters are declared before the `->` symbol, and the function body follows.

#### **Syntax**:
```kotlin
val lambdaName: (Type1, Type2) -> ReturnType = { param1, param2 -> expression }
```

#### **Example**:
```kotlin
val sum: (Int, Int) -> Int = { a, b -> a + b }

fun main() {
    val result = sum(3, 4)
    println(result) // Output: 7
}
```

### 2. Lambda with `it` Keyword

When a lambda has only one parameter, Kotlin implicitly names it `it`. This can make the code more concise.

#### **Example**:
```kotlin
val square: (Int) -> Int = { it * it }

fun main() {
    val result = square(5)
    println(result) // Output: 25
}
```

### 3. Lambda with Explicit Parameter Types

You can explicitly specify the types of the parameters in a lambda expression if it's not clear from the context.

#### **Example**:
```kotlin
val concatenate: (String, String) -> String = { a: String, b: String -> a + b }

fun main() {
    val result = concatenate("Hello, ", "World!")
    println(result) // Output: Hello, World!
}
```

### 4. Lambda Inside Higher-Order Functions

Kotlin's standard library provides many higher-order functions like `map`, `filter`, `forEach`, etc., which take lambdas as arguments.

#### **Example with `map`**:
```kotlin
val numbers = listOf(1, 2, 3, 4, 5)
val doubled = numbers.map { it * 2 }

fun main() {
    println(doubled) // Output: [2, 4, 6, 8, 10]
}
```

## 4. Extension Function

Extension functions in Kotlin are a powerful feature that allows you to extend the functionality of existing classes without modifying their source code. Essentially, they let you add new functions to a class, and these functions can be called as if they were part of the class itself.

### **Syntax**:
```kotlin
// Define an extension function for the class
fun Class.functionName(): ReturnType {
    // Function Logic
}
```

### **Example**:
```kotlin
// Define an extension function for the String class
fun String.isPalindrome(): Boolean {
    // this represents the reference of current value
    return this == this.reversed()
}

fun main() {
    val word = "racecar"
    if (word.isPalindrome()) {
        println("$word is a palindrome")
    } else {
        println("$word is not a palindrome")
    }
}

// Output: racecar is a palindrome
```

## 5. Anonymous Function

An anonymous function is a way to define a function without naming it. Unlike lambdas, anonymous functions can have explicit return types and can use labeled return statements.

### **Syntax**:
```kotlin
val functionName = fun(parameter1: Type, parameter2: Type): ReturnType {
    // Function body
    return value
}
```

### **Example**:
```kotlin
val sum = fun(a: Int, b: Int): Int {
    return a + b
}

fun main() {
    val result = sum(5, 7)
    println(result) // Output: 12
}
```



