# 01. Introduction to Kotlin

## Learning objectives
- Explain what Kotlin is and where it is used.
- Understand Kotlin source files and the `main` function.
- Run a basic Kotlin program in Android Studio.
- Read compiler errors and use the Kotlin Playground.

## 1. What is Kotlin?
Kotlin is a statically typed programming language developed by JetBrains. It is widely used for Android development and also supports server-side, desktop and multiplatform development. Kotlin is concise, interoperable with Java and includes language features such as null safety and coroutines.

Official documentation: https://kotlinlang.org/docs/home.html

## 2. Kotlin and Android
For this programme:
- Kotlin is the programming language.
- Android Studio is the IDE.
- Jetpack Compose is the UI toolkit.
- Android SDK provides Android APIs.
- Gradle builds the project.

These are related tools, but they are not interchangeable.

## 3. First Kotlin program

Create a Kotlin file named `HelloKotlin.kt` in a Kotlin/JVM scratch project or use the Kotlin Playground at https://play.kotlinlang.org/.

```kotlin
fun main() {
    println("Hello, Kotlin!")
    println("Welcome to AR INFOTEK")
}
```

Expected output:

```text
Hello, Kotlin!
Welcome to AR INFOTEK
```

## 4. Understand the program
- `fun` declares a function.
- `main` is the conventional entry point for a Kotlin/JVM console program.
- `{ }` delimit the function body.
- `println()` writes text followed by a line break.

An Android application does not start by calling a console `main()` function. Android starts application components such as activities. The console examples in this batch teach the language independently of Android UI.

## 5. Comments

```kotlin
// Single-line comment

/*
   Multi-line comment
*/

/**
 * Documentation comment for declarations.
 */
```

Use comments to explain intent, not to repeat obvious code.

## 6. Kotlin Playground
Open https://play.kotlinlang.org/, enter the first program and select Run. This is useful for small language exercises. Use Android Studio for Android-specific code.

## Exercises
1. Print your name.
2. Print the company name AR INFOTEK.
3. Print three lines describing an Android application.
4. Add a comment above each output statement.
5. Create a program that prints a course title, duration and fee on separate lines.

## Assessment
1. What does statically typed mean?
2. What does `fun` declare?
3. What is the purpose of `main()` in a console program?
4. What is the difference between `print()` and `println()`?
5. Does an Android activity start through the console `main()` function?

## Completion task
Write a program that prints a simple student receipt with student name, course, fee and payment status.
