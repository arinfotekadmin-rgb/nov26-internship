# 06. Functions

## Learning objectives
- Declare and call functions.
- Use parameters and return types.
- Apply default and named arguments.
- Write single-expression functions.
- Understand local functions and function scope.

## 1. What is a function?
A function is a reusable block of code that performs a defined task. Functions help separate a program into smaller units that are easier to test and maintain.

## 2. Function syntax

```kotlin
fun functionName(parameter: Type): ReturnType {
    // statements
    return value
}
```

Example:

```kotlin
fun calculateTotalFee(courseFee: Double, registrationFee: Double): Double {
    return courseFee + registrationFee
}

fun main() {
    val total = calculateTotalFee(5000.0, 500.0)
    println(total)
}
```

## 3. Parameters and arguments
A parameter is declared in the function definition. An argument is the value supplied when calling the function.

## 4. Functions without a return value

```kotlin
fun displayWelcome() {
    println("Welcome to AR INFOTEK")
}
```

A function without an explicit return type returns `Unit`.

## 5. Default arguments

```kotlin
fun calculateFee(courseFee: Double, registrationFee: Double = 500.0): Double {
    return courseFee + registrationFee
}

println(calculateFee(5000.0))
println(calculateFee(5000.0, 300.0))
```

## 6. Named arguments

```kotlin
val total = calculateFee(
    courseFee = 5000.0,
    registrationFee = 300.0
)
```

Named arguments improve clarity when functions have several parameters.

## 7. Single-expression functions

```kotlin
fun square(number: Int): Int = number * number
```

## 8. Local functions

A function can be declared inside another function:

```kotlin
fun createReceipt() {
    fun formatAmount(amount: Double): String = "₹$amount"

    println(formatAmount(5500.0))
}
```

Use local functions when the helper belongs only to one operation.

## 9. Function design
A good function should have a clear responsibility, meaningful name, manageable number of parameters and predictable result. Avoid functions that perform unrelated tasks.

## Exercises
1. Write a function to calculate total fee.
2. Write a function to calculate discount amount.
3. Write a function to return the larger of two numbers.
4. Write a function to check whether a number is even.
5. Write a function to calculate average marks.
6. Write a function with a default registration fee.
7. Use named arguments to call a function with three parameters.
8. Write a function that returns a formatted student summary.

## Assessment
1. What is a function?
2. Difference between a parameter and an argument?
3. What is the default return type when no return type is specified?
4. What is a default argument?
5. When are named arguments useful?

## Practical assignment
Build a fee calculator using separate functions for subtotal, discount, amount paid and outstanding balance. Test each function with at least three input combinations.
