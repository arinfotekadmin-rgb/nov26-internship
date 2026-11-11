# 08. Classes and Objects

## Learning objectives
- Declare classes and create objects.
- Use primary and secondary constructors.
- Declare properties and methods.
- Understand initialization.
- Use visibility modifiers.

## 1. Class and object
A class defines the properties and behaviour of a type. An object is an instance of that class.

```kotlin
class Student {
    var name: String = ""
    var course: String = ""

    fun displayDetails() {
        println("$name - $course")
    }
}

fun main() {
    val student = Student()
    student.name = "Arun"
    student.course = "Kotlin"
    student.displayDetails()
}
```

## 2. Primary constructor

```kotlin
class Student(
    val id: Int,
    var name: String,
    var course: String
) {
    fun display() {
        println("$id: $name - $course")
    }
}
```

Create an object:

```kotlin
val student = Student(101, "Arun", "Android")
student.display()
```

## 3. Initialization block

```kotlin
class Course(val title: String, val fee: Double) {
    init {
        require(title.isNotBlank()) { "Course title is required" }
        require(fee >= 0) { "Fee cannot be negative" }
    }
}
```

The `init` block runs during object construction.

## 4. Secondary constructors

A class can have secondary constructors when additional construction paths are needed. They must delegate to the primary constructor when one exists.

```kotlin
class Intern(val name: String, val durationWeeks: Int) {
    constructor(name: String) : this(name, 4)
}
```

Do not add constructors when default parameters solve the same problem more simply.

## 5. Properties

Kotlin properties provide a concise way to declare data. They can have custom getters and setters.

```kotlin
class FeeAccount(initialFee: Double) {
    var fee: Double = initialFee
        set(value) {
            require(value >= 0)
            field = value
        }
}
```

`field` refers to the backing field inside a custom accessor.

## 6. Visibility modifiers

- `public`: visible by default.
- `private`: visible within the declaring scope or class as applicable.
- `protected`: visible in the class and subclasses.
- `internal`: visible within the same module.

## Exercises
1. Create a Student class with ID, name and email.
2. Add a function to display student information.
3. Create a Course class with title, duration and fee.
4. Validate that course fee is not negative.
5. Create an Intern class with a default duration.
6. Add a property setter that rejects invalid values.

## Assessment
1. What is a class?
2. What is an object?
3. What is a constructor?
4. What is the purpose of an `init` block?
5. What does `private` mean?

## Practical assignment
Create `Student`, `Course` and `Enrollment` classes. Create sample objects and print an enrolment summary. Keep validation inside the relevant classes.
