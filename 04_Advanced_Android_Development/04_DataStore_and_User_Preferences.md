# Chapter 4: DataStore and User Preferences

## 4.1 What belongs in DataStore?
Use Preferences DataStore for small key-value settings such as:
- Theme preference
- Notification preference
- Last selected tab
- Non-sensitive onboarding completion flag

Do not store passwords, access tokens or payment card data in ordinary Preferences DataStore. Use an appropriate secure token-storage design and keep sensitive credentials out of logs.

## 4.2 Example preference flow

```kotlin
val Context.dataStore by preferencesDataStore(name = "settings")
private val DARK_MODE = booleanPreferencesKey("dark_mode")

class SettingsRepository(private val context: Context) {
    val darkMode: Flow<Boolean> = context.dataStore.data
        .map { preferences -> preferences[DARK_MODE] ?: false }

    suspend fun setDarkMode(enabled: Boolean) {
        context.dataStore.edit { preferences ->
            preferences[DARK_MODE] = enabled
        }
    }
}
```

Add the Preferences DataStore dependency using the current stable version from the official Android documentation.

## 4.3 DataStore or Room?
Use DataStore for small settings. Use Room for structured records, relationships, filtering and larger datasets.

## Practical task
Add a Settings screen with Dark Mode and Notifications preferences. Confirm that choices remain after restarting the app.

## Check your understanding
1. When should you use DataStore?
2. When is Room a better choice?
3. Why should you avoid storing a password in a plain preference?
