# 15. Coroutines and Flow: Introduction

## Learning objectives
- Explain why asynchronous work is needed.
- Understand suspending functions.
- Use `launch` and `async` at a basic level.
- Understand dispatchers and structured concurrency.
- Explain the purpose of Flow.

## 1. Why asynchronous work?
Android applications must keep the main thread responsive. Network calls, database operations and other long-running tasks should not block UI rendering or user interaction.

Kotlin coroutines provide a structured way to write asynchronous code.

## 2. Suspending functions

```kotlin
suspend fun loadStudentName(): String {
    return "Arun"
}
```

A `suspend` function can suspend without blocking the underlying thread. It must be called from another suspending function or a coroutine.

## 3. `launch`
`launch` starts a coroutine that does not directly return a result.

```kotlin
import kotlinx.coroutines.*

fun main() = runBlocking {
    launch {
        delay(500)
        println("Task completed")
    }

    println("Main coroutine continues")
}
```

This example uses `runBlocking` for a small console demonstration. Do not use `runBlocking` on the Android main thread.

## 4. `async` and `await`
`async` starts a coroutine that returns a `Deferred` result. Call `await()` to obtain that result.

```kotlin
import kotlinx.coroutines.*

fun main() = runBlocking {
    val result = async {
        delay(300)
        100
    }

    println(result.await())
}
```

Use `async` when a result is needed. Do not use it automatically for every coroutine.

## 5. Dispatchers
Common dispatchers include:
- `Dispatchers.Main`: UI-related work.
- `Dispatchers.IO`: blocking I/O operations.
- `Dispatchers.Default`: CPU-intensive work.

Use the dispatcher appropriate to the operation. Well-designed libraries may already manage their own threading.

## 6. Structured concurrency
Coroutines should belong to a well-defined scope. Parent and child coroutine relationships make cancellation and error handling manageable.

In Android, use lifecycle-aware scopes such as `viewModelScope` for ViewModel work. Do not create unmanaged global scopes for screen operations.

## 7. Flow
Flow represents an asynchronous stream of values.

```kotlin
import kotlinx.coroutines.flow.*
import kotlinx.coroutines.runBlocking

fun numbers(): Flow<Int> = flow {
    emit(1)
    emit(2)
    emit(3)
}

fun main() = runBlocking {
    numbers().collect { value ->
        println(value)
    }
}
```

Study:
- `Flow`
- `StateFlow`
- `SharedFlow`
- `collect`
- `map`
- `filter`
- `flowOn`
- cancellation

## 8. Android relevance
A ViewModel can expose a `StateFlow` representing loading, success or error. A Compose screen can collect that state in a lifecycle-aware way and render the current UI.

## Exercises
1. Write a suspending function that waits and returns a message.
2. Launch two child coroutines.
3. Use `async` and `await` to calculate two independent results.
4. Create a Flow that emits five integers.
5. Apply `map` to transform emitted values.
6. Apply `filter` to emit only even values.
7. Explain why network work should not block the main thread.

## Assessment
1. What does `suspend` mean?
2. Does suspension necessarily block a thread?
3. Difference between `launch` and `async`?
4. What is a dispatcher?
5. What is Flow?
6. Why is structured concurrency useful?

## Practical assignment
Create a simulated course-loading operation. Expose loading, success and error states. This is a Kotlin learning exercise; later, implement the same pattern in an Android ViewModel with `StateFlow`.

## Reference
https://kotlinlang.org/docs/coroutines-overview.html
