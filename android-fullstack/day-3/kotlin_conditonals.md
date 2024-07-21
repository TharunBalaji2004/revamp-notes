---
sidebar_position: 1
slug: kotlin-conditionals
title: Kotlin Conditionals
---

Kotlin offers a variety of conditional structures to control the flow of execution in your programs. These include traditional `if`-`else` statements, the more versatile `when` expression, and various forms of looping constructs. Here’s a detailed look at Kotlin conditionals:

### 1. **`if` as an Expression**
In Kotlin, `if` can also be used as an expression, which means it can return a value. This is useful for assigning values based on conditions.

#### **Syntax**:
```kotlin
val result = if (condition) {
    // Code to execute if condition is true
    value1
} else {
    // Code to execute if condition is false
    value2
}
```

#### **Example**:
```kotlin
val age = 18
val category = if (age >= 18) "Adult" else "Minor"
println("Category: $category")
```

### 2. **`if`-`else` Statement**
The `if`-`else` statement in Kotlin works similarly to other programming languages. It allows you to execute a block of code if a specified condition is true and another block if the condition is false.

#### **Syntax**:
```kotlin
if (condition) {
    // Code to execute if condition is true
} else {
    // Code to execute if condition is false
}
```

#### **Example**:
```kotlin
val age = 18

if (age >= 18) {
    println("You are an adult.")
} else {
    println("You are a minor.")
}
```

### 3. **`else if` Ladder**
Kotlin also supports `else if` for checking multiple conditions in a ladder-like structure.

#### **Example**:
```kotlin
val score = 85

val grade = if (score >= 90) {
    "A"
} else if (score >= 80) {
    "B"
} else if (score >= 70) {
    "C"
} else if (score >= 60) {
    "D"
} else {
    "F"
}

println("Grade: $grade")
```


### 4. **`when` Expression**
The `when` expression in Kotlin is a powerful replacement for the `switch` statement found in many other languages. It can be used for matching a value against a set of conditions and executing corresponding blocks of code.

#### **Syntax**:
```kotlin
when (value) {
    condition1 -> {
        // Code to execute if value matches condition1
    }
    condition2 -> {
        // Code to execute if value matches condition2
    }
    else -> {
        // Code to execute if no conditions are met
    }
}
```

#### **Example**:
```kotlin
val dayOfWeek = 3

val dayName = when (dayOfWeek) {
    1 -> "Monday"
    2 -> "Tuesday"
    3 -> "Wednesday"
    4 -> "Thursday"
    5 -> "Friday"
    6 -> "Saturday"
    7 -> "Sunday"
    else -> "Invalid day"
}

println("Day: $dayName")
```

You can use `if` and `when` together for more complex conditions.

#### **Example**:
```kotlin
val number = 15

val result = when {
    number % 2 == 0 -> "Even"
    number % 3 == 0 -> "Divisible by 3"
    number % 5 == 0 -> "Divisible by 5"
    else -> "Not divisible by 2, 3, or 5"
}

println("Result: $result")
```

### 5. **Range and Collection Checks in `when`**
You can check if a value is within a range or a collection directly in a `when` expression.

#### **Example**:
```kotlin
val number = 15

val result = when (number) {
    in 1..10 -> "Between 1 and 10"
    in 11..20 -> "Between 11 and 20"
    !in 21..30 -> "Not between 21 and 30"
    else -> "Out of range"
}

println("Result: $result")
```

### 6. **Smart Casts in `when`**
Kotlin’s `when` expression supports smart casts, allowing you to perform type-specific operations based on the type of the value.

#### **Example**:
```kotlin
fun checkType(obj: Any) {
    when (obj) {
        is String -> println("It's a string of length ${obj.length}")
        is Int -> println("It's an integer with value $obj")
        is Boolean -> println("It's a boolean with value $obj")
        else -> println("Unknown type")
    }
}

checkType("Hello")
checkType(123)
checkType(true)
```


### 7. **Using Multiple Conditions in `when`**
You can check multiple conditions in a single `when` branch using commas.

#### **Example**:
```kotlin
val input = "yes"

when (input) {
    "yes", "y", "Y" -> println("Affirmative")
    "no", "n", "N" -> println("Negative")
    else -> println("Unknown input")
}
```


