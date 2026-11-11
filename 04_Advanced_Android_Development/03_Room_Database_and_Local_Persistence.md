# Chapter 3: Room Database and Local Persistence

## 3.1 When to use Room
Room provides a structured SQLite database for data that should remain available on the device. Use it for offline course bookmarks, cached reference data or locally saved drafts. Do not use it as a replacement for the central AR INFOTEK PostgreSQL database.

## 3.2 Entity

```kotlin
@Entity(tableName = "saved_courses")
data class SavedCourseEntity(
    @PrimaryKey val courseId: Long,
    val title: String,
    val savedAt: Long
)
```

## 3.3 DAO

```kotlin
@Dao
interface SavedCourseDao {
    @Query("SELECT * FROM saved_courses ORDER BY savedAt DESC")
    fun observeSavedCourses(): Flow<List<SavedCourseEntity>>

    @Insert(onConflict = OnConflictStrategy.REPLACE)
    suspend fun save(course: SavedCourseEntity)

    @Query("DELETE FROM saved_courses WHERE courseId = :id")
    suspend fun remove(id: Long)
}
```

## 3.4 Database

```kotlin
@Database(
    entities = [SavedCourseEntity::class],
    version = 1,
    exportSchema = true
)
abstract class AppDatabase : RoomDatabase() {
    abstract fun savedCourseDao(): SavedCourseDao
}
```

Create the database using `Room.databaseBuilder()` in an application-level dependency provider. Avoid creating a new database instance every time a screen recomposes.

## 3.5 Database migrations
When the schema changes, increase the database version and provide a migration. Do not use destructive migration in production if user data must be retained.

## Practical task
Add Save and Remove actions to the course list. Display saved courses from Room after closing and reopening the app.

## Check your understanding
1. What is an Entity?
2. What does a DAO do?
3. Why should database creation not happen inside a composable?
4. What is a migration?
