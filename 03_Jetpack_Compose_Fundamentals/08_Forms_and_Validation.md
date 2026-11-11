# 8. Forms and Validation

A first AR INFOTEK enquiry form can collect:
- Full name
- Email address
- Mobile number
- Course of interest
- Message

Collect only the information needed. Show a privacy notice and link to the website privacy policy before collecting real student data.

### Controlled text field
```kotlin
var fullName by rememberSaveable { mutableStateOf("") }

OutlinedTextField(
    value = fullName,
    onValueChange = { fullName = it },
    label = { Text("Full name") },
    singleLine = true,
    modifier = Modifier.fillMaxWidth()
)
```

Validate before submitting:
- Name must not be blank.
- Email must use a valid expected format.
- Mobile number must meet the backend's format.
- Course selection must be present.

Client validation improves the form experience. The Node.js backend must validate the submitted data again.

### Exercise
Build a registration form with field-level errors and a success confirmation. Keep submission local at first.
