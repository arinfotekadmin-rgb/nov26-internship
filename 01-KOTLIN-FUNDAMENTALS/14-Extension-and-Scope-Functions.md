# 14. Extension Functions and Scope Functions

## Learning objectives
- Declare extension functions.
- Understand that extensions do not modify the original class.
- Use `let`, `run`, `with`, `apply` and `also`.
- Choose scope functions based on their return value and receiver style.

## 1. Extension functions
An extension function adds callable functionality to a type without changing its source code.

```kotlin
fun String.initials(): String {
    return this
        .trim()
        .split(" ")
        .filter { it.isNotBlank() }
        .mapNotNull { it.firstOrNull()?.uppercaseChar() }
        .joinToString("")
}

println("Arun Raj".initials())
```

An extension does not actually insert a member into the class. Extension dispatch is resolved statically.

## 2. Scope functions overview

| Function | Receiver inside block | Returns |
|---|---|---|
| `let` | `it` | Lambda result |
| `run` | `this` | Lambda result |
| `with` | `this` | Lambda result |
| `apply` | `this` | Original receiver |
| `also` | `it` | Original receiver |

## 3. `let`

Useful for operating on a value, often a nullable value:

```kotlin
val email: String? = "arun@example.com"

email?.let {
    println(it.lowercase())
}
```

## 4. `run`

Useful for grouping operations and returning a result:

```kotlin
val message = "AR INFOTEK".run {
    lowercase().replace(" ", "-")
}
```

## 5. `with`

Use `with` when you want to operate on an object without repeatedly qualifying its members:

```kotlin
val summary = with(course) {
    "$title costs ₹$fee"
}
```

Assume `course` has `title` and `fee` properties.

## 6. `apply`

Useful for configuring an object and returning that object:

```kotlin
val numbers = mutableListOf<Int>().apply {
    add(10)
    add(20)
    add(30)
}
```

## 7. `also`

Useful for side actions such as logging while returning the original object:

```kotlin
val courseName = "Kotlin".also {
    println("Selected course: $it")
}
```

## 8. Selection guidance
Do not chain scope functions unnecessarily. Choose the one whose return value and receiver style make the code easiest to understand.

## Exercises
1. Create an extension function that formats a phone number.
2. Create an extension function that checks whether a course title is blank.
3. Use `let` with a nullable email.
4. Use `apply` to configure a mutable list.
5. Use `also` to log a student object.
6. Rewrite a confusing chain into simple statements.

## Assessment
1. Do extension functions modify the original class?
2. Which scope functions use `it`?
3. Which scope functions return the original receiver?
4. What does `apply` return?
5. Why should scope-function chains be kept readable?

## Practical assignment
Create a student profile formatter using extension functions and one or two appropriate scope functions. Explain why you selected each function.
