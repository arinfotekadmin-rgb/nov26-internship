# Chapter 5: WorkManager and Background Tasks

## 5.1 Purpose
WorkManager schedules deferrable background work that should run reliably, even if the app closes or the device restarts. It is suitable for periodic sync, uploading queued records and retryable work.

It is not intended for exact-time alarms or continuous real-time tracking.

## 5.2 Worker example

```kotlin
class RefreshWorker(
    appContext: Context,
    params: WorkerParameters
) : CoroutineWorker(appContext, params) {

    override suspend fun doWork(): Result {
        return try {
            // Call a repository to refresh suitable cached data.
            Result.success()
        } catch (error: IOException) {
            Result.retry()
        } catch (error: Exception) {
            Result.failure()
        }
    }
}
```

## 5.3 Constraints and scheduling

```kotlin
val constraints = Constraints.Builder()
    .setRequiredNetworkType(NetworkType.CONNECTED)
    .build()

val request = PeriodicWorkRequestBuilder<RefreshWorker>(
    12, TimeUnit.HOURS
)
    .setConstraints(constraints)
    .build()

WorkManager.getInstance(context).enqueueUniquePeriodicWork(
    "course-refresh",
    ExistingPeriodicWorkPolicy.UPDATE,
    request
)
```

Periodic work has a minimum interval of 15 minutes. The operating system controls the exact execution time.

## 5.4 Retry strategy
Use retry for temporary failures such as network unavailability. Use failure for permanent errors that will not succeed through retry alone. Make upload operations idempotent so a retry does not create duplicate records.

## Practical task
Schedule a network-constrained refresh operation. Show the last refresh time in the app and test behaviour with Wi-Fi disabled.

## Check your understanding
1. What type of task suits WorkManager?
2. What is the purpose of constraints?
3. Why should retryable uploads be idempotent?
