# 02. Variables and Data Types

## Learning objectives
- Declare immutable and mutable variables.
- Identify common Kotlin types.
- Use type inference and explicit types.
- Convert values safely.
- Understand string templates.

## 1. `val` and `var`

Use `val` when a reference should not be reassigned. Use `var` when reassignment is required.

```kotlin
val instituteName = "AR INFOTEK"
var enrolledStudents = 25

enrolledStudents = 26
// instituteName = "Other Name" // Compile error
```

Prefer `val` unless the value must change.

## 2. Common types

| Type | Example | Purpose |
|---|---|---|
| `Int` | `25` | Whole numbers |
| `Long` | `9000000000L` | Larger whole numbers |
| `Double` | `4500.50` | Decimal values |
| `Float` | `3.14f` | Single-precision decimal |
| `Boolean` | `true` | True/false |
| `Char` | `'A'` | One character |
| `String` | `"Kotlin"` | Text |

```kotlin
val studentId: Int = 101
val fee: Double = 5000.0
val isPaid: Boolean = false
val grade: Char = 'A'
val studentName: String = "Arun"
```

## 3. Type inference

Kotlin can infer the type from the assigned value:

```kotlin
val courseName = "Android Development" // String
val durationDays = 30                  // Int
```

Use explicit types when they improve clarity or are required by the context.

## 4. Type conversion

Kotlin does not automatically convert all numeric types.

```kotlin
val count: Int = 10
val decimalCount: Double = count.toDouble()

val input = "2500"
val amount = input.toIntOrNull()

println(decimalCount)
println(amount)
```

`toIntOrNull()` returns `null` if the text cannot be converted. It is safer than assuming every input is valid.

## 5. String templates

```kotlin
val student = "Arun"
val fee = 5000

println("Student: $student")
println("Fee: ₹$fee")
println("Next fee: ₹${fee + 500}")
```

Use `${expression}` when you need an expression inside a string.

## 6. Constants

A top-level `const val` can be used for compile-time constants when its type and value meet Kotlin's constant requirements.

```kotlin
const val INSTITUTE_NAME = "AR INFOTEK"
```

Do not use `const` for values that must be calculated at runtime.

## Exercises
1. Declare a student name, ID, email and course.
2. Declare a course fee and registration fee.
3. Calculate the total fee.
4. Convert a numeric string using `toIntOrNull()`.
5. Print a formatted student summary.
6. Explain why `val` is preferred when reassignment is unnecessary.

## Assessment
1. Difference between `val` and `var`?
2. Which type stores true or false?
3. What is type inference?
4. Why does `"25".toIntOrNull()` return a nullable result?
5. How do you insert an expression into a string?

## Practical assignment
Create a student admission summary with at least six variables. Print all values and calculate the total payable fee.
