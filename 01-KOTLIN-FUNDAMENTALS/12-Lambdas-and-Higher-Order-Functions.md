# 12. Lambdas and Higher-Order Functions

## Learning objectives
- Write lambda expressions.
- Understand function types.
- Pass functions as arguments.
- Return functions from functions.
- Use collection operations with lambdas.

## 1. Lambda expression
A lambda is an anonymous function expression.

```kotlin
val greet = { name: String -> "Hello, $name" }
println(greet("Arun"))
```

The type of `greet` is `(String) -> String`.

## 2. Lambda syntax

```kotlin
{ parameters -> expression }
```

For multiple statements, use a block:

```kotlin
val calculate = { a: Int, b: Int ->
    val total = a + b
    total * 2
}
```

The last expression in the lambda is its result.

## 3. Function types

```kotlin
val operation: (Int, Int) -> Int = { a, b -> a + b }
println(operation(10, 20))
```

A function type describes the input and output types.

## 4. Higher-order functions
A higher-order function accepts a function as an argument or returns a function.

```kotlin
fun calculate(
    a: Int,
    b: Int,
    operation: (Int, Int) -> Int
): Int {
    return operation(a, b)
}

val result = calculate(10, 5) { x, y -> x * y }
println(result)
```

## 5. Trailing lambda
When the last parameter is a function, its lambda can be written outside the parentheses.

```kotlin
val names = listOf("Arun", "Priya", "Kumar")
val filtered = names.filter { name -> name.startsWith("A") }
```

## 6. Implicit `it`
A lambda with one parameter can use `it`.

```kotlin
val lengths = names.map { it.length }
```

Use an explicit parameter name when it improves clarity.

## 7. Android relevance
Compose uses lambdas for event callbacks:

```kotlin
Button(onClick = {
    println("Button clicked")
}) {
    Text("Continue")
}
```

The callback is a function passed to the composable.

## Exercises
1. Create a lambda that doubles a number.
2. Create a lambda that formats a student name.
3. Write a higher-order function that applies a discount operation.
4. Filter students by course.
5. Map course names to uppercase.
6. Sort a list using a custom comparison.
7. Create a function that accepts a validation callback.

## Assessment
1. What is a lambda?
2. What does `(Int) -> String` describe?
3. What is a higher-order function?
4. When can you use `it`?
5. What is a trailing lambda?

## Practical assignment
Build a course search utility. Use lambdas to filter courses by title, map them to display labels and sort them by fee.
