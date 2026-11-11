# 13. Exception Handling

## Learning objectives
- Understand exceptions.
- Use `try`, `catch` and `finally`.
- Use `throw` to signal invalid conditions.
- Write safe input parsing.
- Avoid hiding errors.

## 1. What is an exception?
An exception represents an abnormal condition that interrupts normal program flow. Examples include invalid conversions, missing files and failed operations.

## 2. `try` and `catch`

```kotlin
fun parseStudentId(value: String): Int {
    return try {
        value.toInt()
    } catch (exception: NumberFormatException) {
        -1
    }
}
```

For user input, `toIntOrNull()` may be simpler than catching a conversion exception.

## 3. `finally`

```kotlin
try {
    println("Processing")
} catch (exception: Exception) {
    println("An error occurred")
} finally {
    println("Operation finished")
}
```

`finally` runs when control leaves the try/catch structure, subject to process termination or other exceptional runtime conditions. Use resource-specific management APIs such as `use` for closeable resources.

## 4. Throwing an exception

```kotlin
fun validateFee(fee: Double) {
    if (fee < 0) {
        throw IllegalArgumentException("Fee cannot be negative")
    }
}
```

Use a suitable exception type and message.

## 5. `require` and `check`

```kotlin
fun createCourse(title: String, fee: Double) {
    require(title.isNotBlank()) { "Course title is required" }
    require(fee >= 0) { "Fee cannot be negative" }
}
```

- `require` checks caller-supplied arguments.
- `check` checks a condition required for the current object's or program's state.

## 6. Do not swallow errors

Avoid empty catch blocks. Log or handle the error appropriately, and return a meaningful result to the caller. Do not expose stack traces or internal server details to application users.

## Exercises
1. Parse a numeric student ID.
2. Handle invalid fee input.
3. Reject an empty course title.
4. Write a function that throws when marks are outside 0 to 100.
5. Use `finally` to display a completion message.
6. Explain when `toIntOrNull()` is preferable.

## Assessment
1. What is an exception?
2. What does `catch` do?
3. What is the purpose of `finally`?
4. Difference between `require` and `check`?
5. Why is an empty catch block dangerous?

## Practical assignment
Build a command-line admission form using sample input values. Validate name, student ID, course fee and marks. Display clear validation messages for invalid data.
