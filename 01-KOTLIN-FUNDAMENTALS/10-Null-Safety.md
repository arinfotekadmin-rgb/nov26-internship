# 10. Null Safety

## Learning objectives
- Understand nullable and non-nullable types.
- Use safe calls and the Elvis operator.
- Use safe casts and nullable conversion.
- Avoid unsafe assertions.
- Handle missing data in application models.

## 1. Nullable types
A normal Kotlin variable cannot hold `null`.

```kotlin
var name: String = "Arun"
// name = null // Compile error

var email: String? = "arun@example.com"
email = null
```

The `?` after a type makes it nullable.

## 2. Safe call operator

```kotlin
val length = email?.length
```

If `email` is null, the expression returns null instead of throwing a null-pointer exception.

## 3. Elvis operator

```kotlin
val displayEmail = email ?: "Email not provided"
```

The right side is used when the left side is null.

## 4. Safe call with `let`

```kotlin
email?.let {
    println("Email: $it")
}
```

The block runs only when the value is non-null.

## 5. Not-null assertion

```kotlin
// email!!.length
```

`!!` throws an exception if the value is null. Avoid it unless you can prove the value cannot be null at that point. Prefer safe calls, validation or explicit error handling.

## 6. Nullable function result

```kotlin
fun findStudentEmail(id: Int): String? {
    return if (id == 101) "arun@example.com" else null
}
```

Callers must handle the possibility of no result.

## 7. Safe input conversion

```kotlin
val feeText = "5000"
val fee = feeText.toDoubleOrNull()

if (fee != null) {
    println("Fee: $fee")
} else {
    println("Enter a valid fee")
}
```

## 8. Android relevance
API responses may omit optional fields. Model optional values as nullable only when the API contract permits them. Validate required fields at the data boundary and present a useful UI state when data is missing.

## Exercises
1. Declare a nullable phone number.
2. Display a fallback when email is null.
3. Safely calculate the length of an optional name.
4. Convert a text fee to `Double?`.
5. Write a function that returns null when a student ID is not found.
6. Remove `!!` from a sample program and replace it with safe handling.

## Assessment
1. What does `String?` mean?
2. What does `?.` do?
3. What is the purpose of `?:`?
4. Why can `!!` cause a crash?
5. What does `toIntOrNull()` return when conversion fails?

## Practical assignment
Create a student lookup program. Search a list by ID, handle a missing student, and display optional email and phone values safely.
