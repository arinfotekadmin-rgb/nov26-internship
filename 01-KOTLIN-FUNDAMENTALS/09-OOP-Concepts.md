# 09. Object-Oriented Programming Concepts

## Learning objectives
- Explain encapsulation, inheritance, polymorphism and abstraction.
- Use open classes and overridden methods.
- Define interfaces.
- Use abstract classes.
- Select composition or inheritance appropriately.

## 1. Encapsulation
Encapsulation controls how an object's internal state is accessed and changed.

```kotlin
class FeeAccount(initialBalance: Double) {
    var balance: Double = initialBalance
        private set

    fun receivePayment(amount: Double) {
        require(amount > 0)
        balance -= amount
    }
}
```

In a real fee system, the backend must validate payments and maintain the authoritative balance. This class demonstrates local object design only.

## 2. Inheritance
Kotlin classes and methods are final by default. Use `open` when inheritance is intended.

```kotlin
open class User(val name: String) {
    open fun dashboardMessage(): String = "Welcome, $name"
}

class StudentUser(name: String, val studentId: Int) : User(name) {
    override fun dashboardMessage(): String =
        "Welcome student $name"
}
```

## 3. Polymorphism
A base type can refer to objects of different subclasses.

```kotlin
val users: List<User> = listOf(
    User("Admin"),
    StudentUser("Arun", 101)
)

users.forEach { println(it.dashboardMessage()) }
```

The overridden implementation is selected based on the actual object.

## 4. Abstraction
Abstract classes define common structure while leaving selected behaviour to subclasses.

```kotlin
abstract class Report {
    abstract fun generate(): String

    fun printReport() {
        println(generate())
    }
}
```

## 5. Interfaces
An interface defines a contract that a class can implement.

```kotlin
interface Payable {
    fun calculateAmount(): Double
}

class CourseFee(private val fee: Double) : Payable {
    override fun calculateAmount(): Double = fee
}
```

A class can implement multiple interfaces.

## 6. Composition
Composition means building a class using other objects rather than relying on a deep inheritance hierarchy.

```kotlin
class AttendanceService {
    fun summary(): String = "Attendance summary"
}

class StudentDashboard(
    private val attendanceService: AttendanceService
) {
    fun load(): String = attendanceService.summary()
}
```

Composition is often a good default because it keeps responsibilities separate.

## Exercises
1. Create a base `User` class and `Student` subclass.
2. Create `Intern` and `Mentor` subclasses.
3. Override a dashboard message.
4. Create a `CertificateEligible` interface.
5. Create an abstract `Report` class.
6. Demonstrate polymorphism using a list of users.
7. Refactor an inheritance example to use composition.

## Assessment
1. Define encapsulation.
2. Why are Kotlin classes final by default?
3. What does `override` do?
4. Difference between an abstract class and an interface?
5. What is composition?

## Practical assignment
Model student, intern and mentor roles. Give each role appropriate behaviour and demonstrate polymorphism. Avoid putting unrelated responsibilities in the base class.
