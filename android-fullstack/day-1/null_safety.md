---
sidebar_position: 5
slug: kotlin-null-safety
title: Kotlin Null Safety
---

Kotlin's null safety features are designed to eliminate the risk of NullPointerExceptions (NPEs) from your code. This is achieved through a combination of type system enhancements and special operators that allow you to handle nullable types safely and concisely. Here’s a detailed look at Kotlin’s null safety:

### 1. **Nullable and Non-Nullable Types**
In Kotlin, types are non-nullable by default, which means a variable cannot hold a `null` value unless explicitly specified.

#### **Non-Nullable Types**
- **Definition**: A type that cannot hold a `null` value.
- **Usage**: Ensures that the variable always has a valid value.

```kotlin
var name: String = "John"
name = null // Compilation error
```

#### **Nullable Types**
- **Definition**: A type that can hold a `null` value.
- **Usage**: Declared using the `?` operator.

```kotlin
var nullableName: String? = "John"
nullableName = null // Valid
```

### 2. **Safe Calls (`?.`)**
The safe call operator `?.` allows you to safely access properties or call methods on a nullable object without causing a `NullPointerException`. If the object is `null`, the entire expression evaluates to `null`.

#### **Example**:
```kotlin
val length = nullableName?.length // Returns null if nullableName is null
```
In this example, `length` will be `null` if `nullableName` is `null`.

### 3. **Elvis Operator (`?:`)**
The Elvis operator `?:` provides a default value if the left-hand side expression is `null`.

#### **Example**:
```kotlin
val nameLength = nullableName?.length ?: 0 // Returns 0 if nullableName is null
```
Here, `nameLength` will be `0` if `nullableName` is `null`.

### 4. **Safe Casts (`as?`)**
The safe cast operator `as?` attempts to cast an object to a specified type, returning `null` if the cast is not possible.

#### **Example**:
```kotlin
val obj: Any = "Hello"
val str: String? = obj as? String // Safe cast, returns "Hello"
val num: Int? = obj as? Int // Safe cast, returns null
```

### 5. **Non-Null Assertion (`!!`)**
The non-null assertion operator `!!` converts any value to a non-null type, throwing a `NullPointerException` if the value is `null`. Use this operator with caution.

#### **Example**:
```kotlin
val length = nullableName!!.length // Throws NullPointerException if nullableName is null
```

### 6. **Let Function**
The `let` function is often used with safe calls to execute a block of code only if the value is not `null`.

#### **Example**:
```kotlin
nullableName?.let {
    println("Name length: ${it.length}")
}
```
Here, the block of code inside `let` will only be executed if `nullableName` is not `null`.

### 7. **Lateinit Properties**
The `lateinit` keyword allows you to declare a non-nullable `var` that will be initialized later. If accessed before initialization, it throws an `UninitializedPropertyAccessException`.

#### **Example**:
```kotlin
lateinit var database: Database

fun setupDatabase() {
    database = Database()
}
```




