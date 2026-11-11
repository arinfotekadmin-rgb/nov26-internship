# 03. Operators and Expressions

## Learning objectives
- Use arithmetic, comparison and logical operators.
- Understand assignment and compound assignment.
- Apply operator precedence.
- Build useful business calculations.

## 1. Arithmetic operators

| Operator | Meaning | Example |
|---|---|---|
| `+` | Addition | `10 + 5` |
| `-` | Subtraction | `10 - 5` |
| `*` | Multiplication | `10 * 5` |
| `/` | Division | `10 / 5` |
| `%` | Remainder | `10 % 3` |

Integer division returns an integer:

```kotlin
println(7 / 2)       // 3
println(7.0 / 2.0)   // 3.5
```

## 2. Comparison operators

`==`, `!=`, `>`, `<`, `>=` and `<=` produce Boolean results.

```kotlin
val attendance = 82
println(attendance >= 75) // true
```

## 3. Logical operators

- `&&`: logical AND.
- `||`: logical OR.
- `!`: logical NOT.

```kotlin
val feePaid = true
val attendanceEligible = true

val canReceiveCertificate = feePaid && attendanceEligible
```

Kotlin uses short-circuit evaluation for `&&` and `||`.

## 4. Assignment operators

```kotlin
var total = 100
total += 50
total -= 10
total *= 2
total /= 2
```

## 5. Increment and decrement

```kotlin
var count = 0
count++
count--
```

Prefer clear expressions over complicated combinations of increments.

## 6. Operator precedence

Multiplication and division are evaluated before addition and subtraction unless parentheses change the order.

```kotlin
val result1 = 10 + 5 * 2       // 20
val result2 = (10 + 5) * 2     // 30
```

Use parentheses when they make the intended calculation easier to read.

## 7. Practical fee calculation

```kotlin
fun main() {
    val courseFee = 5000.0
    val registrationFee = 500.0
    val discount = 250.0

    val total = courseFee + registrationFee - discount
    println("Amount payable: ₹$total")
}
```

## Exercises
1. Calculate the total fee for three courses.
2. Calculate the remaining fee after a payment.
3. Check whether attendance is at least 75%.
4. Check whether a student is eligible when both fee and attendance conditions are satisfied.
5. Calculate the remainder when 47 students are divided into groups of 5.
6. Rewrite a calculation using parentheses to make its order clear.

## Assessment
1. What is the result of `9 / 2` when both operands are integers?
2. What does `%` return?
3. Difference between `&&` and `||`?
4. What does `!=` mean?
5. Why should parentheses be used in complex expressions?

## Practical assignment
Build a fee calculator that accepts fixed sample values for course fee, registration fee, discount and amount paid. Display total fee, payable amount and balance.
