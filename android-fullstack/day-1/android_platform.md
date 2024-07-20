---
sidebar_position: 1
slug: android-platform
title: Android Platform Architecture
---

# Android Platform Architecture

Lets learn about how Android OS 📱 was designed and developed by Google.

Android OS is an
- Mobile Operating System software
- Open source software
- **Linux-based** tech stack

<div align="center">
    <img src="/img/platform.png" width="500"></img>
</div>

## Android Tech Stack

### Linux Kernel
- Foundation of Android: The Linux kernel is the base of the Android platform.
- Key Functionalities: 
    - Supports threading and low-level memory management through the Android Runtime (ART).
- Security and Hardware Support:
    - Utilizes key security features of Linux.
    - Allows device manufacturers to develop hardware drivers for a familiar kernel.

### Hardware Abstraction Layer (HAL)
- Purpose: Provides standard interfaces to expose device hardware capabilities to the higher-level Java API framework.
- Structure:
    - Each module implements an interface for specific hardware components (e.g., camera, Bluetooth).
- Operation: 
    - When a framework API calls to access hardware, the system loads the appropriate library module.

### Android Runtime (ART)
- Version: Used in devices running Android 5.0 (API level 21) or higher.
- Process Management: Each app runs in its own process with its own instance of ART.
- Execution:
    - Executes Dalvik Executable format (DEX) files.
    - Optimized for minimal memory footprint.
    - Java sources compiled into DEX bytecode using tools like d8.
- Major Features:
    - Ahead-of-time (AOT) and just-in-time (JIT) compilation.
    - Optimized garbage collection (GC).
    - Conversion of DEX files to more compact machine code on Android 9 (API level 28) and higher.
    - Improved debugging support, including sampling profiler, detailed diagnostic exceptions, crash reporting, and watchpoints.
- Compatibility: Apps that run well on ART are likely to work on Dalvik, but not necessarily the reverse.

### Native C/C++ Libraries
- Core Components: Many Android system components and services, such as ART and HAL, are built using C and C++.
- Java Framework APIs: Provide access to functionality of some native libraries (e.g., OpenGL ES for 2D and 3D graphics).
- Android NDK: Allows apps to access native platform libraries directly if C or C++ code is required.

### Java API Framework
- Feature Set: The entire Android OS feature set is available through Java language APIs.
- Building Blocks: 
    - Simplifies reuse of core, modular system components and services:
    - Rich and extensible view system for UI components (lists, grids, text boxes, buttons, web browser).
    - Resource manager for non-code resources (localized strings, graphics, layout files).
    - Notification manager for custom alerts in the status bar.
    - Activity manager for managing app lifecycle and navigation.
    - Content providers for accessing or sharing data between apps.

### System Apps
- Core Apps: Includes email, SMS messaging, calendars, internet browsing, contacts, and more.
- Equal Status: 
    - System apps have no special status; third-party apps can replace them (e.g., default web browser, SMS messenger, keyboard).
- Developer Access:
    -  System apps provide key capabilities accessible from other apps (e.g., invoking an installed SMS app to send messages).

:::info

The origin of Android is that it was initially conceived as an operating system for digital cameras. When Andy Rubin, the co-founder of **Android Inc.**, and his team started working on the project in 2003, their original vision was to create an advanced operating system for **cameras**!

::: 