# Acquire lock {#app_processsteps_lock_acquire .reference}

This step acquires a lock on a specified string value. You can use locks to prevent concurrent modification of resources.

**Tip:** 

Applications, components, and generic processes share some process steps. This step applies to application processes, component processes, and generic processes. This step applies to application processes that are associated with application templates.

When the process reaches this step, the process attempts to obtain a lock with the specified name. If no other process is using a lock with that name, the current process creates a lock with that name and continues. If another process is using a lock with the specified name, the current process waits until the lock is available.

To release the lock, use the [Release lock](app_processsteps_lock_release.md) step. Also, locks are released automatically when the process finishes. If multiple processes are waiting for the same lock, when the lock is released, the server selects the process that made the earliest request to acquire the lock.

**Note:** You can see the active locks by clicking **Settings** \> **Locks**.

|Field|Description|
|-----|-----------|
|**Lock Name**|A string value that identifies the lock. **Note:** Lock Name character limit is 4000.

|

**Parent topic:** [Process steps: Reference](../topics/app_processSteps.md)

