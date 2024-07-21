---
sidebar_position: 3
slug: compilation-process
title: Compilation Process
---

| Kotlin Compilation | Android Compilation |
| :-----: | :-----: |
| <img src="/img/day2/kotlincomp.png" width="400"></img> | <img src="/img/day2/androidcomp.png" width="300"></img> |

### Kotlin Compilation

In order for Kotlin code to run, there are couple of steps which need to be done. For demonstration purpose let’s say we have TestClass.kt file which we want to run. The steps for compiling the given file will be the following:

- TestClass.kt is compiled by kotlinc (Kotlin compiler).
- Kotlinc compiles Kotlin source file into Java byte-code file as TestClass.class.
- Java byte-code file (TestClass.class) ends up in JVM (Java Virtual Machine).
- JVM understands byte-code and converts it into machine code, using JIT (Just-In-Time) compiler.
- The machine code is then fed to the memory and executed by computer’s central processing unit.

### Android Compilation

The main difference between regular Java/Kotlin code compilation and Android compilation process is that Android doesn’t work with JVM. Instead Android decided to create two virtual machines specifically for Android:

1. DVM (Dalvik Virtual Machine)
2. ART (Android Runtime) — introduced with the release of Android 4.4 (Kitkat), and before it the runtime environment for Android apps was DVM.

Regarding their functionalities, ART and Dalvik are compatible runtimes running Dex byte-code which can be found in .dex file.



