# 07. Arrays and Collections

## Learning objectives
- Create and access arrays.
- Understand read-only and mutable collection interfaces.
- Use List, Set and Map.
- Filter, map and sort collections.
- Choose an appropriate collection for a task.

## 1. Arrays

An array stores a fixed-size sequence of values.

```kotlin
val marks = arrayOf(80, 75, 91)
println(marks[0])
marks[1] = 82
```

Array indices start at zero. Accessing an invalid index causes an exception.

For primitive values, Kotlin provides specialised arrays such as `IntArray`.

## 2. Lists

A read-only list interface:

```kotlin
val courses = listOf("Kotlin", "Android", "Python")
println(courses[1])
```

A mutable list:

```kotlin
val students = mutableListOf("Arun", "Priya")
students.add("Kumar")
students.remove("Priya")
```

A `List` reference does not expose mutation operations. This does not automatically guarantee deep immutability of every object stored inside it.

## 3. Sets

A set stores unique elements.

```kotlin
val courseCodes = setOf("KOT101", "AND201", "KOT101")
println(courseCodes) // Duplicate value is stored once
```

## 4. Maps

A map stores key-value pairs.

```kotlin
val studentFees = mapOf(
    "Arun" to 5000,
    "Priya" to 6000
)

println(studentFees["Arun"])
```

Use `mutableMapOf` when you need to add or update entries.

## 5. Collection operations

```kotlin
val marks = listOf(45, 72, 88, 91, 60)

val passed = marks.filter { it >= 50 }
val bonusMarks = marks.map { it + 5 }
val sortedMarks = marks.sorted()

println(passed)
println(bonusMarks)
println(sortedMarks)
```

`filter` selects elements. `map` transforms elements. `sorted` returns a sorted list.

## 6. Useful operations

Study:
- `firstOrNull()`
- `find()`
- `any()`
- `all()`
- `count()`
- `sum()`
- `average()`
- `distinct()`
- `groupBy()`
- `associateBy()`

## 7. Student example

```kotlin
data class StudentRecord(val id: Int, val name: String, val active: Boolean)

val students = listOf(
    StudentRecord(1, "Arun", true),
    StudentRecord(2, "Priya", false),
    StudentRecord(3, "Kumar", true)
)

val activeStudents = students.filter { it.active }
activeStudents.forEach { println(it.name) }
```

## Exercises
1. Store five course names in a list.
2. Add and remove courses from a mutable list.
3. Store unique student IDs in a set.
4. Store student names and fee balances in a map.
5. Filter students whose attendance is at least 75%.
6. Sort students by name.
7. Find the average of a marks list.
8. Group students by course.

## Assessment
1. What is the difference between an array and a list?
2. What is the difference between `List` and `MutableList`?
3. When should you use a set?
4. What does a map store?
5. Difference between `filter` and `map`?

## Practical assignment
Build a console-based course catalogue. Add courses, search by course name, display unique categories, filter active courses and sort the results.
