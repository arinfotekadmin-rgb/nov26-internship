# 11. Data Classes, Enum Classes and Sealed Classes

## Learning objectives
- Use data classes for value-like records.
- Use enum classes for fixed sets of constants.
- Use sealed classes to represent restricted result states.
- Understand generated data-class functions.

## 1. Data classes
Data classes are useful for storing structured data.

```kotlin
data class Student(
    val id: Int,
    val name: String,
    val course: String
)
```

Kotlin generates useful functions such as `equals`, `hashCode`, `toString`, `componentN` and `copy`.

```kotlin
val original = Student(101, "Arun", "Kotlin")
val updated = original.copy(course = "Android")

println(original)
println(updated)
```

## 2. Destructuring

```kotlin
val (id, name, course) = original
println("$id - $name - $course")
```

Destructuring follows the component order. Avoid it when it makes code less readable.

## 3. Enum classes
Use an enum for a fixed set of named values.

```kotlin
enum class PaymentStatus {
    PENDING,
    PAID,
    FAILED,
    REFUNDED
}
```

```kotlin
fun statusMessage(status: PaymentStatus): String =
    when (status) {
        PaymentStatus.PENDING -> "Awaiting payment"
        PaymentStatus.PAID -> "Payment completed"
        PaymentStatus.FAILED -> "Payment failed"
        PaymentStatus.REFUNDED -> "Payment refunded"
    }
```

## 4. Sealed classes
A sealed class or interface represents a restricted hierarchy. It is useful for modelling states that have different data.

```kotlin
sealed interface ApiResult<out T> {
    data class Success<T>(val data: T) : ApiResult<T>
    data class Error(val message: String) : ApiResult<Nothing>
    data object Loading : ApiResult<Nothing>
}
```

Handle each state:

```kotlin
fun showResult(result: ApiResult<String>) {
    when (result) {
        is ApiResult.Success -> println(result.data)
        is ApiResult.Error -> println(result.message)
        ApiResult.Loading -> println("Loading")
    }
}
```

## 5. Android use
A Compose screen may represent loading, content and error states using a sealed UI state. This makes state handling explicit and reduces ambiguous Boolean combinations.

## Exercises
1. Create a `Course` data class.
2. Use `copy()` to update a course fee.
3. Create an enum for internship status.
4. Create a sealed result type with success, error and loading.
5. Write an exhaustive `when` expression.
6. Model a student dashboard state.

## Assessment
1. What functions are generated for a data class?
2. What is the purpose of `copy()`?
3. When is an enum suitable?
4. What is a sealed hierarchy?
5. Why are sealed states useful in UI code?

## Practical assignment
Model a course enrolment with a data class, an enum status and a sealed result type for loading, success and failure.
