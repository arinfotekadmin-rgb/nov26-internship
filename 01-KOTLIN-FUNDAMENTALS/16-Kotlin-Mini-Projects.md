# 16. Kotlin Mini-Projects and Fundamentals Assessment

## Purpose
Use the Kotlin concepts from Chapters 1 to 15 to build small programs before moving to Android UI development.

## Project 1: Student Registration Console App

### Requirements
- Store student ID, name, email and selected course.
- Validate required fields.
- Use a `Student` data class.
- Store multiple students in a mutable list.
- Display all students.
- Search for a student by ID.
- Handle a student who is not found.

### Suggested model

```kotlin
data class Student(
    val id: Int,
    val name: String,
    val email: String?,
    val course: String
)
```

### Acceptance criteria
- Reject blank names.
- Do not accept duplicate IDs.
- Handle missing email safely.
- Search returns a useful message when no student exists.

## Project 2: Course Fee Calculator

### Requirements
- Store course name and course fee.
- Add registration fee.
- Apply a discount.
- Record amount paid.
- Calculate outstanding balance.
- Reject negative values.

### Suggested functions

```kotlin
fun calculateTotal(courseFee: Double, registrationFee: Double): Double
fun calculateDiscount(total: Double, discountPercent: Double): Double
fun calculateBalance(payable: Double, paid: Double): Double
```

Validate that discount percentage is between 0 and 100 and that payments are not negative.

## Project 3: Attendance Calculator

### Requirements
- Accept total working days and present days.
- Calculate attendance percentage.
- Check a configurable eligibility threshold.
- Reject impossible values such as present days greater than working days.

Formula:

```text
Attendance percentage = (Present days / Total working days) * 100
```

Use `Double` for the calculation and handle zero working days.

## Project 4: Course Catalogue

### Requirements
- Store courses in a list.
- Search by title.
- Filter by fee range.
- Filter active courses.
- Sort by fee.
- Display course details.

Use a data class and collection operations such as `filter`, `map`, `sortedBy` and `find`.

## Project 5: Role-Based User Model

### Requirements
- Create a common user abstraction.
- Represent student, intern and mentor roles.
- Use inheritance or interfaces where appropriate.
- Demonstrate polymorphism.
- Avoid putting role-specific behaviour in unrelated classes.

## Suggested implementation order

1. Write the data model.
2. Write validation functions.
3. Implement the business calculations.
4. Add collection storage.
5. Implement search and filtering.
6. Add a simple console menu.
7. Test normal, boundary and invalid inputs.
8. Refactor repeated code into functions.

## Fundamentals assessment

### Section A: Short answers
1. Explain `val` and `var`.
2. What is nullable type syntax?
3. Explain the difference between `List` and `MutableList`.
4. What is a data class?
5. Explain the purpose of an interface.
6. What is a lambda?
7. What does a sealed class represent?
8. Explain `filter` and `map`.
9. What is a suspending function?
10. What is the purpose of `StateFlow`?

### Section B: Programming tasks
1. Find the largest of three integers.
2. Check whether a number is prime.
3. Calculate factorial using a loop.
4. Count vowels in a string.
5. Find the average of a list of marks.
6. Filter students whose attendance is at least 75%.
7. Create a `Course` data class and update a value using `copy()`.
8. Create an enum for payment status.
9. Create a safe student lookup function returning a nullable value.
10. Write a higher-order function that accepts a calculation operation.

## Evaluation rubric

| Area | Marks |
|---|---:|
| Correct program output | 30 |
| Appropriate Kotlin syntax | 20 |
| Functions and code organisation | 15 |
| Data structures and OOP | 15 |
| Validation and error handling | 10 |
| Code readability | 10 |
| **Total** | **100** |

Suggested pass target: 80/100. Rework any topic where you cannot explain the code or handle invalid input.

## Final readiness checklist

- [ ] I can declare variables and choose suitable types.
- [ ] I can write conditions and loops.
- [ ] I can create reusable functions.
- [ ] I can use lists, sets and maps.
- [ ] I can create classes and objects.
- [ ] I can explain core OOP concepts.
- [ ] I can handle nullable data safely.
- [ ] I can use data, enum and sealed classes.
- [ ] I can write and pass lambdas.
- [ ] I can handle exceptions.
- [ ] I understand the basic purpose of coroutines and Flow.
- [ ] I have completed at least three mini-projects independently.

When these items are complete, proceed to Android fundamentals and Jetpack Compose.
