# 04. Control Statements

## Learning objectives
- Use `if` and `else`.
- Use `if` as an expression.
- Use `when` for multiple branches.
- Combine conditions safely.

## 1. `if` and `else`

```kotlin
val marks = 78

if (marks >= 50) {
    println("Pass")
} else {
    println("Fail")
}
```

The condition must evaluate to a Boolean.

## 2. `if` as an expression

Kotlin's `if` can return a value:

```kotlin
val result = if (marks >= 50) "Pass" else "Fail"
println(result)
```

## 3. Multiple conditions

```kotlin
val attendance = 82

if (attendance >= 90) {
    println("Excellent attendance")
} else if (attendance >= 75) {
    println("Eligible")
} else {
    println("Attendance shortage")
}
```

Place conditions in an order that prevents a broader condition from hiding a more specific one.

## 4. `when`

Use `when` when several possible values or conditions need separate branches.

```kotlin
val grade = 'A'

when (grade) {
    'A' -> println("Excellent")
    'B' -> println("Very good")
    'C' -> println("Good")
    'D' -> println("Needs improvement")
    else -> println("Invalid grade")
}
```

`when` can also be used as an expression:

```kotlin
val message = when (grade) {
    'A' -> "Excellent"
    'B' -> "Very good"
    else -> "Review required"
}
```

## 5. Range conditions

```kotlin
val marks = 86

when (marks) {
    in 90..100 -> println("A")
    in 75..89 -> println("B")
    in 50..74 -> println("C")
    in 0..49 -> println("Fail")
    else -> println("Invalid marks")
}
```

## 6. Business rule example

```kotlin
fun canReceiveCertificate(feePaid: Boolean, attendance: Int): Boolean {
    return feePaid && attendance >= 75
}
```

For a real system, validate that attendance is between 0 and 100 and verify fee status from trusted backend data.

## Exercises
1. Check whether a number is positive, negative or zero.
2. Check whether a student passed.
3. Convert marks into grades.
4. Check whether a fee balance is zero.
5. Determine certificate eligibility from fee and attendance conditions.
6. Reject marks outside the range 0 to 100.

## Assessment
1. What is the difference between `if` and `when`?
2. Can `if` return a value in Kotlin?
3. What is the purpose of `else`?
4. What does `in 75..89` test?
5. Why should input ranges be validated?

## Practical assignment
Create a student result program. Accept marks for three subjects, calculate the average and assign a grade using `when` or `if` expressions.
