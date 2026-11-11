# 05. Loops and Ranges

## Learning objectives
- Use `for`, `while` and `do-while`.
- Create ascending and descending ranges.
- Use `break` and `continue`.
- Avoid infinite loops.

## 1. `for` loop

```kotlin
for (day in 1..5) {
    println("Day $day")
}
```

`1..5` includes both 1 and 5.

## 2. `until`, `downTo` and `step`

```kotlin
for (i in 1 until 5) println(i)  // 1, 2, 3, 4
for (i in 5 downTo 1) println(i)
for (i in 0..10 step 2) println(i)
```

## 3. `while` loop

Use `while` when repetition depends on a condition.

```kotlin
var count = 1

while (count <= 5) {
    println(count)
    count++
}
```

Make sure the loop condition eventually becomes false.

## 4. `do-while`

A `do-while` loop executes its body at least once.

```kotlin
var attempts = 0

do {
    println("Attempt: $attempts")
    attempts++
} while (attempts < 3)
```

## 5. `break` and `continue`

- `break` exits the nearest loop.
- `continue` skips the current iteration and moves to the next one.

## 6. Attendance example

```kotlin
val attendance = listOf(20, 22, 18, 25, 24)
var total = 0

for (presentDays in attendance) {
    total += presentDays
}

println("Total present-day records: $total")
```

This example adds values. A real attendance percentage needs both present days and total working days.

## Exercises
1. Print numbers from 1 to 100.
2. Print even numbers from 2 to 50.
3. Print a multiplication table.
4. Calculate the sum of numbers from 1 to 100.
5. Find the factorial of a positive integer.
6. Count the number of digits in an integer.
7. Print a course schedule for six days.
8. Use `break` to stop when a target student ID is found.

## Assessment
1. Which range includes the ending value: `1..5` or `1 until 5`?
2. What does `downTo` do?
3. Which loop always runs at least once?
4. Difference between `break` and `continue`?
5. What causes an infinite loop?

## Practical assignment
Create an attendance summary for a sample batch. Loop through daily attendance records and calculate the total present days and average attendance per student.
