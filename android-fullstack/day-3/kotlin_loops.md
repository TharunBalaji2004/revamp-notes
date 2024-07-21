---
sidebar_position: 2
slug: kotlin-loops
title: Kotlin Loops
---

Kotlin offers various looping constructs that help you iterate over collections, ranges, or perform repetitive tasks. These constructs include `for`, `while`, and `do-while` loops. Here's a detailed overview of Kotlin loops:


### 1. **`for` Loop**
The `for` loop in Kotlin is used to iterate over ranges, arrays, or other collections.

#### **Syntax**:
```kotlin
for (item in collection) {
    // Code to execute for each item
}
```

#### **Example with Range**:
```kotlin
for (i in 1..5) {
    println(i)
}
// Output: 1 2 3 4 5
```

#### **Example with Array**:
```kotlin
val array = arrayOf("a", "b", "c")

for (element in array) {
    println(element)
}
// Output: a b c
```


### 2. **`while` Loop**
The `while` loop executes a block of code as long as the specified condition is true.

#### **Syntax**:
```kotlin
while (condition) {
    // Code to execute while the condition is true
}
```

#### **Example**:
```kotlin
var i = 1

while (i <= 5) {
    println(i)
    i++
}
// Output: 1 2 3 4 5
```

### 3. **`do-while` Loop**
The `do-while` loop is similar to the `while` loop, but it guarantees that the code block is executed at least once before the condition is tested.

#### **Syntax**:
```kotlin
do {
    // Code to execute
} while (condition)
```

#### **Example**:
```kotlin
var i = 1

do {
    println(i)
    i++
} while (i <= 5)
// Output: 1 2 3 4 5
```

### 4. **`break` and `continue`**
Kotlin supports `break` and `continue` to control the flow within loops.

#### **`break`**:
Exits the loop immediately.

```kotlin
for (i in 1..5) {
    if (i == 3) break
    println(i)
}
// Output: 1 2
```

#### **`continue`**:
Skips the current iteration and proceeds to the next iteration.

```kotlin
for (i in 1..5) {
    if (i == 3) continue
    println(i)
}
// Output: 1 2 4 5
```

### 5. **Nested Loops**
Loops can be nested within each other. `break` and `continue` can also be labeled to control nested loops.

#### **Example**:
```kotlin
for (i in 1..3) {
    for (j in 1..3) {
        println("i: $i, j: $j")
    }
}
```

