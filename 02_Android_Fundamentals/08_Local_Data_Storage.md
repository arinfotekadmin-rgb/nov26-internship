# 8. Local Data Storage

Choose storage based on the type of data:
- **DataStore:** small preferences such as theme selection or onboarding completion.
- **Room:** structured relational data built on SQLite.
- **Files:** documents and media using suitable storage APIs.
- **In-memory state:** temporary UI data that does not need persistence.

### Room concepts
- Entity: table representation.
- DAO: database operations.
- Database: Room database holder.
- Repository: interface between data sources and app logic.

### Exercise
Plan a saved-courses feature. Define a `SavedCourse` entity with `courseId`, `title` and `savedAt`. Draw the data flow from UI to ViewModel to repository to Room.

Do not store passwords or payment card data in plain text. Use Android security guidance for sensitive information.
